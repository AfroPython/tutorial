# blog.urls

Crie um novo arquivo vazio `blog/urls.py`. Tudo bem! Adicione estas duas primeiras linhas:

```
from django.conf.urls import include, url
from . import views
```

Aqui nós estamos apenas importando métodos do Django e todos os nossos views do aplicativo blog (ainda não temos nenhuma, mas teremos em um minuto!)

Depois disso nós podemos adicionar nosso primeira URL padrão:

```
urlpatterns = [
    url(r'^$', views.post_list),
]
```

Como você pode ver, estamos agora atribuindo uma `view` chamada `post_list` para `^$` URL. Essa expressão regular corresponderá a `^` (um começo) seguido por `$` (fim) - então somente uma seqüência vazia irá corresponder. E isso é correto, porque em resolvedores de Django url, `http://<<sua_url>>.codeanyapp.com:8000/` não é uma parte da URL. Este padrão irá mostrar o Django que `views.post_list` é o lugar certo para ir, se alguém entra em seu site no endereço `http://<<sua_url>>.codeanyapp.com:8000 /`.

Tudo certo? Abra sua página no seu navegador pra ver o resultado.

# Foto aqui

Não tem mais "It Works!' mais ein? Não se preocupe, é só uma página de erro, nada a temer! Elas são na verdade muito úteis:

Você pode ler que não há **no attribute `post_list`**. O *post_list* te lembra alguma coisa? Isto é como chamamos o nosso view! Isso significa que está tudo no lugar, só não criamos nossa view ainda. Não se preocupe, nós chegaremos lá.

> Se você quer saber mais sobre Django URLconfs, veja a documentação oficial: https://docs.djangoproject.com/en/1.8/topics/http/urls/
