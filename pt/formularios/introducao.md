# Formulários do Django

Por último, queremos uma forma legal de adicionar e editar as postagens do nosso blog. A `ferramenta de administração` do Django é legal, mas ela é um pouco difícil de customizar e de deixar mais bonita. Se usarmos `formulários` teremos controle absoluto sobre nossa interface - podemos fazer qualquer coisa que imaginarmos!

Uma coisa legal do Django é que nós podemos tanto criar um formulário do zero como podemos criar um `ModelForm` que salva o resultado do formulário para um determinado modelo.

Isso é exatamente o que nós queremos fazer: criaremos um formulário para o nosso modelo `Post`.

Assim como toda parte importante do Django, os formulários tem seu próprio arquivo: `forms.py`.

Precisamos criar um arquivo com este nome dentro da pasta `blog`.

    blog
       └── forms.py


Ok, vamos abri-lo e escrever nele o seguinte:

blog/forms.py
```python
from django import forms

from .models import Post

class PostForm(forms.ModelForm):

    class Meta:
        model = Post
        fields = ('title', 'text')
```

Primeiro precisamos importar o módulo de formulários do Django (`from django import forms`) e, obviamente, nosso modelo `Post` (`from .models import Post`).

`PostForm`, como você já deve suspeitar, é o nome do nosso formulário. Precisamos dizer ao Django que este formulário é um `ModelForm` (assim o Django pode fazer a mágica pra gente) - o `forms.ModelForm` é o responsável por isso.

Segundo, nós temos a classe `Meta` onde dizemos ao Django qual modelo deveria ser usado para criar este formulário (`model = Post`).

Finalmente, nós podemos dizer qual(is) campo(s) deveriam entrar em nosso formulário. Nesse cenário nós queremos apenas o `title` e `text` para ser exposto - `author` deveria ser a pessoa que está logada no sistema (nesse caso, você!) e `created_date` deveria ser setado automaticamente quando nós criamos um post (no código), correto?

E é isso aí! Tudo o que precisamos fazer agora é usar o formulário em uma *view* e mostrá-lo em um template.

Então, mais uma vez, nós iremos criar: um link para a página, uma URL, uma view e um template.

## Link para a página com o formulário

É hora de abrir `blog/templates/blog/base.html`. Nós iremos adicionar um link na `div` de nome `cabecalho-pagina`:

blog/templates/blog/base.html
```html
<a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
```

Note que nós queremos chamar nossa nova view de `post_new`.

Depois de adicionar a linha, seu html deve se parecer com isso:

blog/templates/blog/base.html
```html
{% load staticfiles %}
<html>
    <head>
        <title>Blog do AfroPython</title>
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
        <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
        <link href="https://fonts.googleapis.com/css?family=Roboto:400,700" rel="stylesheet">
        <link rel="stylesheet" href="{% static 'css/blog.css' %}">
    </head>
    <body>
        <div class="cabecalho-pagina">
            <a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
            <h1><a href="/">Blog do AfroPython</a></h1>
        </div>
        <div class="content container">
            <div class="row">
                <div class="col-md-8">
                    {% block content %}
                    {% endblock %}
                </div>
            </div>
        </div>
    </body>
</html>
```

Depois de salvar e recarregar a página `http://<<sua_url>>.codeanyapp.com:8080/` você verá, obviamente, um erro familiar: `NoReverseMatch`, certo?
