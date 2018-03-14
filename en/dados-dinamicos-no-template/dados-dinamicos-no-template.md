# Dados dinâmicos no template

Nós temos diferentes peças aqui: o model `Post` está definido em `models.py`, nós temos `post_list` no `views.py` e o template adicionado. Mas como nós faremos de fato para fazer com que as nossas postagens apareçam no nosso template em HTML? Porque é isso que nós queremos: pegar algum conteúdo (models salvos no banco de dados) e exibi-lo de uma maneira bacana no nosso template, certo?

E isso é exatamente o que as views devem fazer: conectar models e templates. Na nossa view `post_list` nós vamos precisar pegar os models que queremos exibir e passá-los para o template. Então, basicamente, em uma view nós decidimos o que será exibido no template.

Certo, e como nós faremos isso?

Precisamos abrir o nosso `blog/views.py`. Até agora a view `post_list` se parece com isso:

```
from django.shortcuts import render

def post_list(request):
    return render(request, 'blog/post_list.html', {})
```

Lembra quando falamos sobre a inclusão de código escrito em arquivos diferentes? Agora é o momento em que temos de incluir o model que temos escrito em `models.py`. Vamos adicionar esta linha `from .models import Post` como este:

```
from django.shortcuts import render
from .models import Post
```

O ponto depois de `from` significa o *diretório atual* ou o *aplicativo atual*. Como `views.py` e `models.py` estão no mesmo diretório podemos simplesmente usar `.` e o nome do arquivo (sem `.py`). Então nós importamos o nome do modelo (`Post`).

E o que vem agora? Para pegar os posts reais do model `Post` nós precisamos de uma coisa chamada `QuerySet`.
