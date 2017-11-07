# Como funcionam as URLs em Django?

Vamos abrir o arquivo `mysite/urls.py` e ver com que ele se parece:

```
from django.conf.urls import include, url
from django.contrib import admin

urlpatterns = [
    # Examples:
    # url(r'^$', 'mysite.views.home', name='home'),
    # url(r'^blog/', include('blog.urls')),

    url(r'^admin/', include(admin.site.urls)),
]
```

Como você pode ver, o Django já colocou alguma coisa lá pra nós.

As linhas que começam com `#` são comentários - isso significa que essas linhas não serão executadas pelo Python. Muito útil, não?

A URL do admin, que você visitou no capítulo anterior já está aqui:

```
 url(r'^admin/', include(admin.site.urls)),
```

Isso significa que para cada URL que começa com `admin/` o Django irá encontrar um correspondente modo de exibição. Neste caso nós estamos incluindo um monte de admin URLs para que isso não fique tudo embalado neste pequeno arquivo é também mais legível e mais limpo.
