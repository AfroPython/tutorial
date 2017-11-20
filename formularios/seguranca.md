## Segurança

Ser capaz de criar novas postagens apenas clicando em um link é incrível! Mas agora, qualquer um que visitar nosso site será capaz de criar uma nova postagem no blog, e isso, provavelmente não é algo que você quer.
Vamos fazer com que o botão apareça apenas para você e mais ninguém.

Em `blog/templates/blog/base.html`, encontre nossa `div` `cabecalho-pagina` e a tag `<a>` que você colocou lá anteriormente. Deve se parecer com isso:

blog/templates/blog/base.html
```html
<a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
```

Nós vamos adicionar outra tag `{% if %}` aqui, que fará com que o link seja exibido apenas para usuários que estiverem "logados" como admin. Nesse momento, é apenas você! Altere a tag `<a>` para algo como:

blog/templates/blog/base.html
```html
{% if user.is_authenticated %}
    <a href="{% url 'post_new' %}" class="top-menu"><span class="glyphicon glyphicon-plus"></span></a>
{% endif %}
```

Esse `{% if %}` fará com que o link seja enviado para o browser apenas se o usuário que requisitar a página estiver "logado". Isso não protege a criação de novas postagens completamente, mas é um bom primeiro passo.

Lembra do ícone de edição que nós acabamos de adicionar a nossa página de detalhes? Nós também queremos adicionar a mesma alteração lá, para que outras pessoas não sejam capazes de editar postagens existentes.

Abra `blog/templates/blog/post_detail.html` e encontre essa linha:

blog/templates/blog/post_detail.html
```html
<a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
```

Altere ela para isso:

blog/templates/blog/post_detail.html
```html
{% if user.is_authenticated %}
     <a class="btn btn-default" href="{% url 'post_edit' pk=post.pk %}"><span class="glyphicon glyphicon-pencil"></span></a>
{% endif %}
```

Como você deve estar "logado(a)", se você atualizar a página, não verá nada de diferente. Carregue a página em um navegador diferente ou em uma janela anônima, e então, veja que o link não é exibido, assim como o ícone também não é!
