## E se não?
Nos exemplos anteriores, o código foi executado somente quando as condições eram verdade. Mas o Python também tem instruções `elif` e `else`:
```

if 5 > 2:
    print('5 é realmente maior que 2')
else:
    print('5 não é maior que 2')
```

Quando for executado irá imprimir:
```
$ python3 python_intro.py
5 é realmente maior que 2
```

Se 2 for um número maior do que 5, então o segundo comando será executado. Fácil, né? Vamos ver como funciona o `elif`:
```

name = 'Sonja'
if name == 'Ola':
    print('Hey Ola!')
elif name == 'Sonja':
    print('Hey Sonja!')
else:
    print('Hey anonymous!')
```

e executado:
```
$ python3 python_intro.py
Hey Sonja!
```
Viu o que aconteceu? O python comparou o valor da variável `name` e caiu na condição do `elif` onde compara `name == 'Sonja'` e assim imprimiu `Hey Sonja!` :D
