## Salvando o formulário

Abra `blog/views.py` mais uma vez. Atualmente tudo que temos na visão `post_new` é:

blog/views.py
```python
def post_new(request):
    form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

Quando nós enviamos o formulário, somos trazidos de volta para a mesma visão, mas desta vez temos mais alguns dados no `request`, mais especificamente em `request.POST` (o nome não tem nada com uma "postagem" de blog , tem a ver com o fato de que estamos "postando" dados). Você se lembra que no arquivo HTML nossa definição de ` <form> ` tem a variável `method="POST"`? Todos os campos vindos do "form" estarão disponíveis agora em `request.POST`. Você não deveria renomear `POST` para nada diferente disso (o único outro valor válido para `method` é `GET`, mas nós não temos tempo para explicar qual é a diferença).

Então, na nossa *view*, nós temos duas situações separadas para lidar. A primeira é quanto acessamos a página pela primeira vez e queremos um formulário em branco. E a segunda, é quando nós temos que voltar para a *view* com todos os dados do formulário que nós digitamos. Desse modo, precisamos adicionar uma condição (usaremos `if` para isso).

blog/views.py
```python
if request.method == "POST":
    [...]
else:
    form = PostForm()
```

Está na hora de preencher os pontos`[...]`. Se `method` é `POST` então nós queremos construir o `PostForm` com os dados que vem do formulário, certo? Nós iremos fazer assim:

blog/views.py
```python
form = PostForm(request.POST)
```

Fácil! A próxima coisa é verificar se o formulário está correto(todos os campos requeridos estão definidos e nenhum valor incorreto foi enviado). Fazemos isso com `form.is_valid()`.

Verificamos se o formulário é válido e se estiver tudo certo, podemos salvá-lo!

blog/views.py
```python
if form.is_valid():
    post = form.save(commit=False)
    post.author = request.user
    post.published_date = timezone.now()
    post.save()
```

 Basicamente, temos duas coisas aqui: salvamos o formulário com `form.save` e adicionados um autor(já que não tinha o campo `author` em `PostForm`, e este campo é obrigatório!). `commit=False` significa que não queremos salvar o modelo `Post` ainda - queremos adicionar autor primeiro. Na maioria das vezes você irá usar `form.save()`, sem `commit=False`, mas neste caso, precisamos fazer isso. `post.save()` irá preservar as alterações (adicionando o autor) e será criada uma nova postagem no blog!

Finalmente, seria fantástico se nós pudéssemos imediatamente ir à página `post_detail` da nossa recém-criada postagem no blog, certo? Para fazer isso nós precisamos fazer mais um import:

blog/views.py
```python
from django.shortcuts import redirect
```

Adicione-o logo no início do seu arquivo. E agora podemos dizer: vá para a página `post_detail` da recém-criada postagem.

blog/views.py
```python
return redirect('post_detail', pk=post.pk)
```

`blog.views.post_detail` é o nome da view para qual queremos ir. Lembra que essa *view* exige uma variável `pk`? Para passar ela para `views` usamos `pk=post.pk`, onde post é a recém-criada postagem no blog.

Ok, nós falamos muito, mas provavelmente queremos ver como toda a *view* se parece agora, certo?

blog/views.py
```python
def post_new(request):
    if request.method == "POST":
        form = PostForm(request.POST)
        if form.is_valid():
            post = form.save(commit=False)
            post.author = request.user
            post.published_date = timezone.now()
            post.save()
            return redirect('post_detail', pk=post.pk)
    else:
        form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

Vamos ver se funciona. Vá para o página `http://<<sua_url>>.codeanyapp.com:8080/post/new/`, adicione um `title` e o `text`, salve... e voilà! O novo blog post é adicionado e nós somos redirecionados para a página de `post_detail`!

Isso é incrível!

> Como nós recentemente usamos a interface de administração do Django, o sistema ainda pensa que nós estamos "logados". Existem algumas situações que poderiam nos levar a estar "deslogados" (fechando o browser, reiniciando o banco de dados, etc.). Se, durante a criação de uma postagem, você perceber que está recebendo erros referentes a falta de um usuário "logado", vá para a página de administração http://<<sua_url>>.codeanyapp.com:8080/admin e faça o login novamente. Isso resolverá o problema temporariamente.

![Erro de login](post_create_error.png)
