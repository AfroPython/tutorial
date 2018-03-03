## Laços

Já é a última parte. Foi rápido, não? :)

Como mencionamos, as pessoas que programam são preguiçosas, não gostam de repetir as mesmas coisas. Programação fala sobre como automatizar as coisas, então não queremos cumprimentar cada pessoa pelo seu nome manualmente, certo? É aí onde os laços vem a calhar.

Ainda se lembra das listas? Vamos fazer uma lista de garotas:

```
garotas = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
```

Queremos cumprimentar todas elas pelos seus nomes. Temos a função oi para fazer isso, então vamos usá-la em um loop:

```
for nome in garotas:
```

O `for` se comporta da mesma forma que o `if`, o código abaixo esses dois precisam ser recuados quatro espaços.

Aqui está o código completo que será salvo no arquivo:
```
def oi(nome):
    print('Oi ' + nome + '!')

garotas = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'You']
for nome in garotas:
    oi(nome)
    print('Proxima!')
```

e quando executá-lo:

```
$ python3 python_intro.py
Oi Rachel!
Proxima!
Oi Monica!
Proxima!
Oi Phoebe!
Proxima!
Oi Ola!
Proxima!
Oi You!
Proxima!
```

Como você pode ver, tudo o que você vai colocar dentro de uma instrução `for` com espaço será repetido para cada elemento da lista `garotas`.

Você também pode usar o `for` em números usando a função `range`:

```
for i in range(1, 6):
    print(i)
```

Que iria imprimir:

```
1
2
3
4
5
```

`range` é uma função que cria uma lista de números que se seguem um após o outro (esses números são dados por você como parâmetros).

Note que o segundo desses dois números não está incluído na lista que o Python mostrou (em `range(1, 6)`, conta de 1 a 5, mas o 6 não é incluído).
