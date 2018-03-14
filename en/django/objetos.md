# Objetos

Existe um conceito na programação chamado `Programação Orientada à Objetos (POO)`. A ideia é que em vez de escrever tudo como uma chata sequência de instruções de programação, podermos modelar as coisas e definir como elas interagem umas com as outras.

Então o que é um objeto? É uma coleção de propriedades e ações. Isto pode parecer estranho, mas vamos lhe dar um exemplo.

Se queremos modelar um gato nós criaremos um objeto `Gato` que possui algumas propriedades, por exemplo `cor`, `idade`, `humor` (bom, mau, sonolento ;)), `dono` (que é um objeto da classe `Pessoa` ou, caso seja um gato de rua, essa propriedade é vazia).

E então o `Gato` tem algumas ações: `ronronar`, `arranhar` e `comer` (no qual vamos dar ao gato alguma `ComidaDeGato`, que poderia ser um objeto separado com propriedades, como `sabor`).

```
Gato
--------
cor
idade
humor
dono
ronronar()
arranhar()
comer(comida_de_gato)


ComidaDeGato
--------
sabor
```

Então, basicamente, a ideia é descrever coisas do mundo real no código, usando propriedades (chamadas de `propriedades do objeto`) e ações (chamadas de `métodos`).

Como nós iremos modelar as postagens do blog então? Queremos construir um blog, certo?

Precisamos responder à pergunta: o que é uma postagem de blog? Que propriedades deve ter?

Bem, com certeza nosso blog precisa de alguma postagem com o seu conteúdo e um título, certo? Também seria bom saber quem a escreveu - então precisamos de um autor. Finalmente, queremos saber quando a postagem foi criada e publicada.

```
Post
--------
title
text
author
created_date
published_date
```

Que tipo de coisa pode ser feita com uma postagem? Seria legal ter algum método que publique a postagem, não é mesmo?

Então precisamos de um método chamado `publicar`.

Como já sabemos o que queremos alcançar, podemos começar a modelagem em Django!
