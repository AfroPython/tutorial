# Modelo de lista de post de exibição

No capítulo anterior, nós fornecemos ao nosso template uma lista de postagens e a variável posts. Agora vamos exibir em nosso HTML.

Para exibir uma variável no Django template, nós usamos colchetes duplos com o nome da variável dentro, exemplo:

```
{{ posts }}
```

Tente fazer isso no seu template `blog/templates/blog/post_list.html` (substituia o segundo e o terceiro par de tags `<div></div>` pela linha `{{ posts }})`, salve o arquivo e atualize a página para ver os resultados:

# Foto aqui

Você pode ver, tudo que temos é:

```
<QuerySet [<Post: My second post>, <Post: My first post>]>
```

Isto significa que o Django a entende como uma lista de objetos. Lembre-se de **introdução ao Python** como podemos exibir listas? Sim, com os loops! Em um template Django, fazemos isso da seguinte maneira:

```
{% for post in posts %}
    {{ post }}
{% endfor %}
```

Tente fazer isso no seu template.

# Foto aqui

Funciona! Mas nós queremos que eles sejam exibidos como os posts estáticos, como os que criamos anteriormente no capítulo de **Introdução a HTML**. Nós podemos misturar HTML com tags de template. O conteúdo da tag body ficará assim:

```
<div>
    <h1><a href="/">Django Girls Blog</a></h1>
</div>

{% for post in posts %}
    <div>
        <p>publicado em: {{ post.published_date }}</p>
        <h1><a href="">{{ post.title }}</a></h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

Tudo que você põe entre `{% for %}` e `{% endfor %}` será repetido para cada objeto na lista. Atualize sua página:

# Foto aqui

Você notou que dessa vez nós usamos uma notação um pouco diferente `{{ post.title }}` ou `{{ post.text }}`? Nós estamos acessando os dados em cada um dos campos que definimos no model do Post. Além disso, `|linebreaksbr` está passando o texto do post por um filtro, convertendo quebras de linha em parágrafos.

Parabéns! Agora vá em frente e tente adicionar um novo post em seu Django admin (Lembre-se de adicionar `published_date`!), em seguida, atualize a página para ver se o post aparece por lá.

Funciona como mágica? Estamos orgulhosos! Afaste-se do seu computador um pouco, você ganhou uma pausa. :)

# Foto de pausa aqui
