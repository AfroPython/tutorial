# if...elif...else
Muitas coisas no código só podem ser executadas se determinadas condições forem atendidas. É por isso que o Python tem alguma coisa chamada declaração **if**.

Substitua o código no arquivo **python_intro.py** para isto:
```
if 3 > 2:
```

Se salvou este e ele foi executado, nós veríamos um erro como este:
```
$ python3 python_intro.py
File "python_intro.py", line 2
         ^
SyntaxError: unexpected EOF while parsing
```

Python espera que nós forneçamos mais instruções que serão supostamente executadas caso a condição `3 > 2` venha a ser verdadeira (ou `True` nesse caso). Vamos tentar fazer o Python imprimir "It works!". Altere o seu código no seu arquivo **python_intro.py** para isto:
```
if 3 > 2:
    print('Isso funciona!')
```

Você percebeu que identamos ([O que é identação?](https://pt.wikipedia.org/wiki/Indenta%C3%A7%C3%A3o)) a próxima linha com 4 espaços? Precisamos fazer isso para que o Python saiba qual código será executado se o resultado for True. Você pode fazer com 1 espaço, mas quase todos as pessoas que programam em Python fazem com 4 para deixar as coisas arrumadas. Um único tab também vai contar como 4 espaços.

Salve-o e execute novamente:
```
$ python3 python_intro.py
Isso funciona!
```
