# Ordenando objetos
Um QuerySet também nos permite ordenar a lista de objetos. Vamos tentar ordenar as postagens pelo campo `created_date`:

```
>>> Post.objects.order_by('created_date')
<QuerySet [<Post: Exemplo de título>, <Post: Post número 2>, <Post: Meu 3º post!>, <Post: 4º título de post>]>
```

Você também pode inverter a ordem adicionando - no início:

```
>>> Post.objects.order_by('-created_date')
<QuerySet [<Post: 4º título de post>, <Post: Meu 3º post!>, <Post: Post número 2>, <Post: Exemplo de título>]>
```

Legal! Você já está pronta para a próxima parte! Para fechar o terminal digite:

```
>>> exit()
$
```
