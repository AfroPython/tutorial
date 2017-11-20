# Fazendo comparações

Grande parte da programação consiste em comparar coisas. O que é mais fácil de comparar? Números, é claro. Vamos ver como isso funciona:
```
>>> 5 > 2
True
>>> 3 < 1
False
>>> 5 > 2 * 2
True
>>> 1 == 1
True
>>> 5 != 2
True
```

Demos ao Python alguns números para comparar. Como você pode ver, Python pode comparar não só números mas também resultados de métodos. Legal, hein?

Você está se perguntando por que colocamos dois sinais de igual ``==`` lado a lado para comparar se os números são iguais?

Nós usamos um único ``=`` para atribuir valores a variáveis.

Você sempre, sempre precisa colocar dois ``==`` se quiser verificar se as coisas são iguais. Também é possível afirmar que as coisas são diferentes entre si. Para isso, usamos o símbolo ``!=``, conforme mostrado no exemplo acima.

Dê ao Python mais duas tarefas:
```
>>> 6 >= 12 / 2
True
>>> 3 <= 2
False
```

``>`` e ``<`` são fáceis, mas o que ``>=`` e ``<=`` significam?

Leia eles da seguinte forma:
- `x > y` significa: x é maior que y
- `x < y` significa: x é menor que y
- `x <= y` significa: x é menor ou igual a y
- `x >= y` significa: x é maior ou igual a y


Fantástico! Vamos brincar mais um pouco? Tente isto:
```
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
```

Você pode dar ao Python quantos números para comparar quanto você quiser, e ele vai te dar uma resposta! Espertinho, certo?

- `and` - se você usar o operador and, ambas as comparações terão que ser verdadeiras para que todo o comando seja verdadeiro
- `or` - se você usar o operador or, apenas uma das comparações precisa ser verdadeira para que o comando todo seja verdadeiro

Já ouviu a expressão "comparar maçãs com laranjas"? Vamos tentar o equivalente em Python:
```
>>> 1 > 'django'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unorderable types: int() > str()
```

Aqui vemos que assim como na expressão, Python não é capaz de comparar um ``número (int)`` e uma ``string (str)``. Em vez disso, ele mostrou um **TypeError** e nos disse que os dois tipos não podem ser comparados juntos.

Mas como o python entende verdadeiro e falso? Vamos para a próxima parte! :)
