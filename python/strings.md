## Strings
Que tal o seu nome? Digite seu primeiro nome entre aspas, desse jeito:
```
>>> "Ola"
'Ola'
```
Você acabou de criar sua primeira string! String é um sequência de caracteres que podem ser processada pelo computador. A string sempre precisa iniciar e terminar com o mesmo caractere. Este pode ser aspas duplas(") ou simples(') - elas dizem ao Python que o que está dentro delas é uma string.

Strings podem ser juntadas. Tente isto:
```
>>> "Oi " + "Ola"
'Oi Ola'
```
Você também pode multiplicar strings por um número:
```
>>> "Ola" * 3
'OlaOlaOla'
```

Se você precisa colocar uma apóstrofe dentro de sua string, existem duas maneiras de fazer.
Usando aspas duplas:
```
>>> "Foi a gota d'água"
"Foi a gota d'água"
```

ou escapando apóstrofo com uma barra invertida (\):
```
>>> "Foi a gota d\'água"
"Foi a gota d'água"
```

Legal, hein? Para ver seu nome em letras maiúsculas, basta digitar:
```
>>> "Ola".upper()
'OLA'
```

Você acabou de usar a **função** ``upper`` na sua string! Uma função (como upper()) é um conjunto de instruções que o Python realiza em um determinado objeto ("Ola"), sempre que você chamar por ele.

Se você quer saber o número de letras do seu nome, existe uma função para isso também!
```
>>> len("Ola")
3
```

Se perguntando porque algumas vezes você chama funções com um ``.`` no fim de uma string (como ``"Ola".upper()``) e algumas vezes você primeiro chama a função colocando a string nos parênteses? Bem, em alguns casos, funções pertencem a objetos, como ``upper()``, que só pode ser utilizada em strings. Nesse caso, nós chamamos a função de **método**. Outras vezes, funções não pertencem a nada específico e podem ser usadas em diferentes tipos de objetos, assim como ``len()``. É por isso que nós estamos fornecendo ``"Ola"`` como um parâmetro para a função ``len``.

### Resumo

OK, chega de strings. Até agora você aprendeu sobre:

- **o prompt** - digitar comandos (códigos) no interpretador Python resulta em respostas em Python
- **números e strings** - no Python, números são usados para matemática e strings para objetos de texto
- **operadores** - como + e *, combinam valores para produzir um novo valor
- **funções** - como upper() e len(), executam ações nos objetos.


Isso é o básico sobre todas as linguagens de programação que você aprende. Pronto(a) para algo mais difícil? Apostamos que sim!
