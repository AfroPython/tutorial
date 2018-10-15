## Editando o formulário

Agora já sabemos como adicionar um novo formulário. Mas e se quisermos editar um já existente? É muito semelhante ao que fizemos. Vamos criar algumas coisas importantes rapidamente (se você não entender alguma coisa - você deve perguntar a seu treinador ou veja os capítulos anteriores, já cobrimos todas essas etapas anteriormente).

Abra `blog/templates/blog/post_detail.html` e adicione a linha:

blog/templates/blog/post_detail.html
```html
<a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
```

Agora o template (modelo) estará parecido com:

blog/templates/blog/post_detail.html
```html
{% extends 'blog/base.html' %}

{% block content %}
    <div class="post">
        {% if post.published_date %}
            <div class="date">
                {{ post.published_date }}
            </div>
        {% endif %}
        <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
        <h1>{{ post.title }}</h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endblock %}
```

Em `blog/urls.py` adicionamos esta linha:

blog/urls.py
```python
    url(r'^post/(?P<pk>\d+)/edit/$', views.post_edit, name='post_edit'),
```

Nós reutilizaremos o modelo `blog/templates/blog/post_edit.html`, então a última coisa que falta é uma *view*.

Vamos abrir `blog/views.py` e adicionar no final do arquivo:

blog/views.py
```python
def post_edit(request, pk):
    post = get_object_or_404(Post, pk=pk)
    if request.method == "POST":
        form = PostForm(request.POST, instance=post)
        if form.is_valid():
            post = form.save(commit=False)
            post.author = request.user
            post.published_date = timezone.now()
            post.save()
            return redirect('post_detail', pk=post.pk)
    else:
        form = PostForm(instance=post)
    return render(request, 'blog/post_edit.html', {'form': form})
```

Isso é quase exatamente igual a nossa view de `post_new`, certo? Mas não totalmente. Primeira coisa: passamos um parâmetro extra `pk` de urls . Em seguida: pegamos o modelo `Post` que queremos editar com `get_object_or_404 (Post, pk=pk)` e então, enquanto criamos um formulário, passamos esta postagem como uma `instância`, ambos quando salvamos o formulário...

blog/views.py
```python
form = PostForm(request.POST, instance=post)
```

…e quando nós acabamos de abrir um formulário com essa postagem para editar:

blog/views.py
```python
form = PostForm(instance=post)
```

Ok, vamos testar se funciona! Vamos para a página `post_detail`. Deve haver um botão editar no canto superior direito:

![Botão editar](edit_button2.png)

Quando você clicar nele você verá o formulário com a nossa postagem:

![Editando o formulário](edit_form2.png)

Sinta-se livre para mudar o título ou o texto e salvar as mudanças!

Parabéns! Sua aplicação está ficando cada vez mais completa!

Se você precisar de mais informações sobre formulários do Django você deve ler a documentação: https://docs.djangoproject.com/en/1.9/topics/forms/