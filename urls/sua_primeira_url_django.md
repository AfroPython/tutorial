# Sua primeira url Django!

É hora de criar nossa primeira URL! Queremos [http://0.0.0.0:8000/] (http://0.0.0.0:8000/)para ser uma página inicial do nosso blog e exibir uma lista de posts.

Também queremos manter o arquivo de `mysite/urls.py` limpo, aí nós importaremos urls da nossa aplicação blog para o arquivo principal `mysite/urls.py`.

Vá em frente, apague as linhas comentadas (as linhas que começam com `#`) e adicione uma linha que vai importar `blog.urls` para a url principal (`''`).

O seu arquivo `mysite/urls.py` deve agora se parecer com isto:
```
from django.conf.urls import include, url
from django.contrib import admin

urlpatterns = [
    url(r'^admin/', include(admin.site.urls)),
    url(r'', include('blog.urls')),
]
```

O Django agora irá redirecionar tudo o que entra em `http://<<sua_url>>.codeanyapp.com:8000/` para `blog.urls` e procurar por novas instruções lá.

Ao escrever as expressões regulares em Python é sempre feito com `r` na frente da sequência - isso é só uma dica útil para Python que a seqüência pode conter caracteres especiais que não são destinadas para Python em si, mas em vez disso são parte da expressão regular.
