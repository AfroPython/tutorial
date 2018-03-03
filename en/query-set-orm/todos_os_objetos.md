# Todos os objetos

Antes, vamos tentar mostrar todas as nossas postagens. Podemos fazer isso com o seguinte comando:

````
>>> Post.objects.all()
Traceback (most recent call last):
      File "<console>", line 1, in <module>
NameError: name 'Post' is not defined
```

Oops! Um erro apareceu. Ele nos diz que não existe algo chamado Post. É verdade -- nós esquecemos de importá-lo primeiro!

```
>>> from blog.models import Post
```

Isso é simples: importamos o modelo Post de dentro do blog.models. Vamos tentar mostrar todas as postagens novamente:

```
>>> Post.objects.all()
<QuerySet [<Post: meu título do post>, <Post: meu outro título do post>]>
```

É uma lista dos posts que criamos anteriormente! Criamos esses posts usando a interface de administração do Django. No entanto, agora queremos criar novas mensagens utilizando o python, então como é que fazemos isso?
