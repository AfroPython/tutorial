# Head & body

Cada página HTML também é dividida em dois elementos: **head** (cabeça) e **body** (corpo).

- **head** é um elemento que contém informações sobre o documento que não são mostradas na tela.
- **body** é um elemento que contém tudo o que é exibido como parte de uma página de um site.

Nós usamos a tag `<head>` para dizer ao navegador sobre as configurações da página.
Por sua vez, a tag `<body>` diz ao navegador o que há de verdade na página.

Por exemplo, você pode por o elemento título de uma página web dentro da tag `<head>`. Veja:

```
<html>
    <head>
        <title>Blog da Ola</title>
    </head>
    <body>
        <p>Olá, pessoal!</p>
        <p>Funciona!</p>
    </body>
</html>
```

Salve o arquivo e atualize sua página.

# Foto do novo template aqui

Viu como o navegador entendeu que "Blog da Ola" é o título da página? Ele interpretou `<title>Blog da Ola</title>` e colocou o texto na barra de título do seu navegador (e também será usado para os favoritos e outras coisas mais).

Provavelmente você já deve ter notado que cada tag de abertura casa com uma tag de fechamento, com uma `/`, e que os elementos estão aninhados (ex.: você não pode fechar um tag em particular antes que todas as outras tags que estiverem dentro dela já estejam fechadas).

É como colocar coisas dentro de caixas. Você tem uma grande caixa, `<html></html>`; dentro dela há `<body></body>`, sendo que esta ainda contém caixas menores: `<p></p>`.

Você precisa seguir essas regras de fechamento de tags, e de aninhamento de elementos - se você não fizer isso, o navegador poderá não estar apto para interpretar seu código de maneira correta e sua página será exibida de maneira incorreta.
