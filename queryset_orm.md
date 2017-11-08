# QuerySets e ORM do Django

Neste capítulo você vai aprender como Django se conecta ao banco de dados e como ele armazena dados. Vamos nessa!

# O que é um QuerySet?

Um QuerySet (conjunto de pesquisa), no fundo, é uma lista de objetos de um dado modelo. Um QuerySet permite que você leia os dados do banco, filtre e ordene o mesmo.

É mais fácil aprender por exemplos. Vamos tentar?

# O Shell do Django

Abra seu console local (não no PythonAnywhere) e digite esse comando:

                  command-line
                  (myvenv) ~/djangogirls$ python manage.py shell

O efeito deve se parecer com isso:

                  command-line
                  (InteractiveConsole)
                  >>>
Agora você está no console interativo do Django. Ele é como o prompt do Python, só que com umas mágicas Django adicionais :). Você pode usar todos os comandos do Python aqui também, é claro.

# Todos os objetos

Antes, vamos tentar mostrar todas as nossas postagens. Podemos fazer isso com o seguinte comando:

    command-line
    >>> Post.objects.all()
    Traceback (most recent call last):
          File "<console>", line 1, in <module>
    NameError: name 'Post' is not defined

Oops! Um erro apareceu. Ele nos diz que não existe algo chamado Post. É verdade -- nós esquecemos de importá-lo primeiro!

    command-line
    >>> from blog.models import Post

Isso é simples: importamos o modelo Post de dentro do blog.models. Vamos tentar mostrar todas as postagens novamente:

    command-line
    >>> Post.objects.all()
    <QuerySet [<Post: my post title>, <Post: another post title>]>

É uma lista das postagens que criamos anteriormente! Criamos essas postagens usando a interface de administração do Django. No entanto, agora queremos criar novas postagens utilizando o python, então, como é que fazemos isso?

# Criando um objeto

É assim que você cria um objeto Post no banco de dados:

    command-line
    >>> Post.objects.create(author=me, title='Sample title', text='Test')

Mas aqui temos um ingrediente que está faltando: me. Precisamos passar uma instância do modelo User como autor. Como fazer isso?

Primeiro vamos importar o modelo User:

    command-line
    >>> from django.contrib.auth.models import User

Quais usuários temos no nosso banco de dados? Experimente isso:

    command-line
    >>> User.objects.all()
    <QuerySet [<User: Ana>]>

É o superusuário que criamos anteriormente! Vamos obter uma instância de usuário agora:

    command-line
    me = User.objects.get(username='Ana')

Como você pode ver, nós agora usamos um get para pegar um User com um username igual a 'Ana'. Claro, você tem que adaptar essa linha ao seu nome de usuário.

Agora finalmente podemos criar nossa primeira postagem:

    command-line
    >>> Post.objects.create(author=me, title='Sample title', text='Test')
    
Viva! Quer ver se funcionou?

  command-line
  >>> Post.objects.all()
  <QuerySet [<Post: my post title>, <Post: another post title>, <Post: Sample title>]>
  
  
