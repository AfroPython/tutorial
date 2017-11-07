# Customize seu template

Agora você pode se divertir um pouco tentando customizar o seu template! Aqui estão algumas tags úteis para isso:
- <h1>Um título</h1> - para o título mais importante
- <h2>Um sub-título</h2> para um título um nível abaixo
- <h3>Um sub-sub-título</h3> ... e por aí vai, até <h6>
- <em>texto</em> enfatiza seu texto
- <strong>text</strong> enfatiza fortemente seu texto
- <br /> pula para a próxima linha (você não pode colocar nada dentro de br)
- <a href="https://djangogirls.org">link</a> cria um link
- <ul><li>primeiro item</li><li>segundo item</li></ul> cria uma lista, exatamente como essa!
- <div></div> define uma seção da página

Aqui está um exemplo de um template completo:

```
<html>
    <head>
        <title>Blog do AfroPython</title>
    </head>

    <body>
        <div>
            <h1><a href="">Blog do AfroPython</a></h1>
        </div>

        <div>
            <p>publicado em: 25.11.2017, 12:14</p>
            <h2><a href="">Minha primeira postagem</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
        </div>

        <div>
            <p>publicado em: 25.11.2017, 14:30</p>
            <h2><a href="">Minha segunda postagem</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut f.</p>
        </div>
    </body>
</html>
```

Nós criamos três seções div aqui.
- O primeiro elemento div possui o título do nosso blog - é um título e um link
- Os outros dois elementos div possuem nossas postagens com a data de publicação, h2 com o título da postagem que é clicável e dois ps (parágrafos) de texto, um para a data e outro para o texto da postagem.

Isso nos dá o seguinte efeito:

# Aqui vai a foto de como ficou o post

Yaaay! Mas, até agora, nosso template mostra exatamante **sempre a mesma informação** - sendo que, anteriormente, nós falávamos sobre templates como uma maneira para exibir informações **diferentes** em um **mesmo formato**.

O que nós realmente queremos fazer é exibir postagens reais que foram adicionadas no Django admin - e isso é o que faremos em seguida.
