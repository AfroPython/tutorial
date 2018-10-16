# Configurando

Vamos fazer algumas alterações no `AfroPython/settings.py`. Abra o arquivo usando o editor de código que usamos anteriormente.

Seria bom ter a hora correta no nosso site. Vá para a [wikipedia timezones list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) e copie seu fuso horário. (no nosso caso, `America/Sao_Paulo`)

No arquivo `settings.py`, localize a linha que contém `TIME_ZONE` e modifique para escolher seu próprio fuso horário:
```
TIME_ZONE = 'America/Sao_Paulo'
```

No mesmo arquivo, precisamos permitir o nosso acesso ao site. Para isso, localize a linha `ALLOWED_HOST` e modifique para:
```
ALLOWED_HOSTS = ['*']
```

Nós também precisaremos adicionar um caminho para arquivos estáticos (nós vamos descobrir tudo sobre arquivos estáticos e CSS mais tarde no tutorial). Desça até o final do arquivo e logo abaixo da entrada `STATIC_URL`, adicione um novo um chamado `STATIC_ROOT`:
```
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
```

Lembre-se de clicar em "Save File" após incluir o conteúdo acima.

Por enquanto isso, vamos para a próxima parte?
