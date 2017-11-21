# Filtrar objetos

Uma grande parte de QuerySets é a habilidade de filtrá-los. Digamos que queremos encontrar todos as postagens escritas pelo usuário `ola`. Nós usaremos o `filter` em vez de all em `Post.objects.all()`. Entre parênteses indicamos que as condições precisam ser atendidas por um postagem de blog para acabar em nosso queryset. Em nosso caso é `author` que é igual a `eu`. A maneira de escrever isso no Django é: `author=eu`. Agora o nosso trecho de código parece com este:

```
>>> Post.objects.filter(author=eu)
<QuerySet [<Post: Exemplo de título>, <Post: Post número 2>, <Post: Meu 3º post!>, <Post: 4º título de post>]>
`]>
```

Ou talvez nós queremos ver todos os posts que contenham a palavra 'titulo' no campo de `title`?

```
>>> Post.objects.filter(title__contains='titulo')
<QuerySet [<Post: Exemplo de título>, <Post: 4º t[itulo de post]>]>
```

> Nota: Existem dois caracteres de sublinhado `(_)` entre o `title` e `contains`. Django ORM usa esta sintaxe para separar nomes de campo ("title") e operações ou filtros ("contains"). Se você usar apenas um sublinhado, você obterá um erro como "FieldError: Cannot resolve keyword title_contains".

Você também pode obter uma lista de todos os posts publicados. Fazemos isso filtrando todos os posts com `published_date` definido no passado:

```
>>> from django.utils import timezone
>>> Post.objects.filter(published_date__lte=timezone.now())
[]
```

Infelizmente, nenhum dos nossos posts estão publicados ainda. Nós podemos mudar isso! Primeiro obtenha uma instância de um post que queremos publicar:

```
>>> post = Post.objects.get(id=1)
```

E então publicamos com o nosso método de publish!

```
>>> post.publish()
```

Agora tente obter a lista de posts publicados novamente (pressione a seta para cima botão 3 vezes e tecle Enter):

```
>>> Post.objects.filter(published_date__lte=timezone.now())
<QuerySet [<Post: Título de exemplo>]>
```
