# Erros

Vamos tentar algo novo. Podemos obter o tamanho de um número da mesma forma que podemos encontrar o tamanho do nosso nome? Digite ``len(304023)`` e pressione Enter:
```
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

Temos nosso primeiro erro! Ele diz que objetos do tipo "int" (inteiros, apenas números) não têm nenhum comprimento. Então o que podemos fazer agora? Talvez possamos escrever nosso número como uma string? Strings têm um comprimento, certo?

```
>>> len(str(304023))
6
```

Funcionou! Usamos a função ``str`` dentro da função ``len``.

- A **função str** converte as coisas em strings
- A **função int** converte as coisas em números inteiros

**Importante:** podemos converter números em texto, mas nós não podemos, necessariamente, converter texto em números - o que ``int('hello')`` quer dizer?
