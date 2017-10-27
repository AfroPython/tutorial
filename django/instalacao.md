## Instalando o Django

Você pode instalar Django usando `pip`.

No console, execute:

```
$ sudo pip install django==1.8.5
```

Esse comando vai instalar o django 1.8.5 para nós. Note que usamos um duplo sinal de igual: `==`. Lembra quando estudamos as [comparações](../python/comparando.md) no python?

Algo assim deve aparecer no terminal:
```
$ sudo pip install django==1.8.5
Downloading/unpacking django==1.8.5
Collecting
Installing collected packages: django
Cleaning up…
```

 Após isso, execute:
 ```
 $ pip freeze > requirements.txt
 ```
 Esse comando serve para congelar as versões deles e garantir que no futuro conseguiremos rodar nosso projeto com as versões certas das coisas. Perceba que usamos um sinal de maior: `>`.

 É isso! Agora você está (finalmente) pronta para criar uma aplicação Django! :D
