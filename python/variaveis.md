# Variáveis

Um conceito importante na programação é o conceito de variáveis. Uma variável não é nada mais do que um nome para alguma coisa, de tal forma que você possa usá-la mais tarde. As pessoas que programam usam essas variáveis para guardar dados, para fazer seus códigos mais legíveis e para não ter que se lembrar sempre o que algumas coisas significam.

Digamos que queremos criar uma nova variável chamada ``nome``:

```
>>> nome = "Ola"
```

Vê? É fácil! É só fazer: nome igual a Ola.

Como você percebeu, seu programa não retornou nada como fez anteriormente. Então como sabemos que a variável realmente existe? Simplesmente digite nome e tecle Enter:

```
>>> nome
'Ola'
```

Yippee! Sua primeira variável! :) Você sempre pode mudar o seu valor:
```
>>> nome = "Sonja"
>>> nome
'Sonja'
```

Você pode usá-la também em funções:
```
>>> len(nome)
5
```

Íncrível não? Claro, variáveis podem ser qualquer coisa, então podem ser números também! Tente isso:
```
>>> a = 4
>>> b = 6
>>> a * b
24
```

Mas, e se digitarmos o nome errado? Você consegue adivinhar o que aconteceria? Vamos tentar!
```
>>> cidade= "Tokyo"
>>> ciade
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ciade' is not defined
```

Um erro! Como você pode ver, Python tem diferentes tipos de erros e este é chamado **NameError**. Python dará este erro se você tentar usar uma variável que não foi definida ainda. Se você encontrar esse erro depois, veja se no seu código se você não digitou o nome de uma variável errado.

Brinque com isso por um tempo e veja o que você consegue fazer!
