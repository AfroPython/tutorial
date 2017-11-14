## Suas próprias funções!

Se lembra de funções como len() que você pode executar no Python? Bem, boas notícias, agora você vai aprender a escrever suas próprias funções!

Uma função é uma sequência de instruções que o Python deve executar. Cada função em Python começa com a palavra-chave def, seguido de um nome para a função e opcionalmente uma lista de parâmetros. Vamos começar com uma função simples. Substitua o código no python_intro.py com o seguinte:

```
def oi():
    print('Olá!')
    print('Como vai você?')

hi()
```

Ok, nossa primeira função está pronta!

Você pode se perguntar por que escrevemos o nome da função na parte inferior do arquivo. Isto é porque Python lê o arquivo e executa de cima para baixo. Então, para usar a nossa função, temos de escrevê-lo na parte inferior.

Vamos executa-lo agora e ver o que acontece:

```
$ python3 python_intro.py
Olá!
Como vai você?
```

Isso foi fácil! Vamos construir nossa primeira função com parâmetros. Usaremos o exemplo anterior - uma função que diz 'hi' para quem o executa - com um name:

```
def oi(nome):
```

Como você pode ver, agora demos um parâmetro chamado nome para nossa função:

```
def oi(nome):
    if nome == 'Ola':
        print('Oi Ola!')
    elif nome == 'Sonja':
        print('Oi Sonja!')
    else:
        print('Oi anonimo!')

oi()
```

Como você pode ver, nós precisamos colocar dois espaços antes da função print, porque if precisa saber o que deve acontecer quando a condição for atendida. Vamos ver como isso funciona agora:
```
$ python3 python_intro.py
Traceback (most recent call last):
File "python_intro.py", line 10, in <module>
  oi()
TypeError: oi() missing 1 required positional argument: 'nome'
```

Oops, um erro. Felizmente, Python nos fornece uma mensagem de erro bastante útil. Ela diz que a função oi() (aquela que declaramos) tem um argumento obrigatório (chamado nome) e que nós esquecemos de passá-lo ao chamar a função. Vamos corrigi-lo na parte inferior do arquivo:

```
oi("Ola")
```

e execute novamente:

```
$ python3 python_intro.py
Oi Ola!
```

E se mudarmos o nome?

```
oi("Sonja")
```

e executá-lo:
```
$ python3 python_intro.py
Oi Sonja!
```

Agora, o que acha que vai acontecer se você escrever outro nome lá? (Sem ser Ola ou Sonja). Experimente e veja se você está certo. Ele deve imprimir isto:

```
Oi anonimo!
```

Isto é incrível, não? Dessa maneira você não precisa se repetir (DRY - don't repeat yourself, ou em português, não se repita) cada vez que for mudar o nome da pessoa que a função pretende cumprimentar. E é exatamente por isso que precisamos de funções - você nunca quer repetir seu código!


Vamos fazer algo mais inteligente..--existem mais que dois nomes, e escrever uma condição para cada um seria difícil, certo?

```
def oi(nome):
    print('Oi ' + nome + '!')

oi("Rachel")
```

Vamos chamar o código agora:

```
$ python3 python_intro.py
Oi Rachel!
```
Parabéns! Você acabou de aprender a criar funções :)!
