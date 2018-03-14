# QuerySet

Você já deve estar familiarizado com o modo que os QuerySets funcionam. Nós conversamos sobre isso no capítulo ORM do Django (QuerySets). Agora nós estamos interessados em uma lista de posts que são publicados e classificados por `published_date`, certo? Nós já fizemos isso no capítulo QuerySets!

```
Post.objects.filter(published_date__lte=timezone.now()).order_by('-published_date')
```

Agora nós colocamos este pedaço de código dentro do arquivo `blog/views.py` adicionando-o à função `def post_list(request)`:

```
from django.shortcuts import render
from django.utils import timezone
from .models import Post

def post_list(request):
    posts = Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    return render(request, 'blog/post_list.html', {})
```

Note que criamos uma *variável* para nosso o QuerySet: `posts`. Trate isto como o nome do nosso QuerySet. De agora em diante nós podemos nos referir a ele por este nome.

A última parte que falta é passar o QuerySet `posts` para o template (veremos como exibi-lo em um próximo capítulo).

Na função render já temos o parâmetro `request` (tudo o que recebemos do usuário através da Internet) e um arquivo de template `'blog/post_list.html'`. O último parâmetro, que se parece com isso: `{}` é um lugar em que podemos acrescentar algumas coisas para que o template use. Precisamos nomeá-los (ficaremos com `'posts'` por enquanto :)). Deve ficar assim: `{'posts': posts}`. Observe que a parte antes de `:` está entre aspas `''`.

Então finalmente nosso arquivo `blog/views.py` deve se parecer com isto:

```
from django.shortcuts import render
from django.utils import timezone
from .models import Post

def post_list(request):
    posts = Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    return render(request, 'blog/post_list.html', {'posts': posts})
```

Feito! Hora de voltar para o nosso template e exibir essa QuerySet!

> Se quiser ler mais sobre QuerySets no Django você deve dar uma olhada aqui: https://docs.djangoproject.com/en/1.8/ref/models/querysets/
