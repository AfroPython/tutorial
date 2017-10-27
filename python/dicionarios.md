# Dicionários

Um dicionário é semelhante a uma lista, mas você pode acessar valores através de uma chave em vez de um índice. Uma chave pode ser qualquer string ou número. O comando para definir um dicionário vazio é:
```
>>> {}
{}
```
Isso mostra que você acabou de criar um dicionário vazio. Hurra!

Agora, tente escrever o seguinte comando (tente substituir com as suas próprias informações também):
```
>>> participante = {'nome': 'Ola', 'pais': 'Polonia', 'numeros_favoritos': [7, 42, 92]}
```

Com esse comando, você acabou de criar uma variável chamada participante com três pares de chave-valor:
- A chave `nome` aponta para o valor `'Ola'` (um objeto string)
- `pais` aponta para `'Polonia'` (outra string)
- e `numeros_favoritos` apontam para `[7, 42, 92]` (uma lista com três números nela)

Você pode checar o conteúdo de chaves individuais com esse comando:
```
>>> print(participante['nome'])
Ola
```

Veja, é similar a uma lista. Mas você não precisa lembrar o índice - apenas o nome.

O que acontece se pedirmos ao Python o valor de uma chave que não existe? Você consegue adivinhar? Vamos tentar e descobrir!
```
>>> participante['idade']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'idade'
```

Olha, outro erro! Esse é um `KeyError`. Python é bastante prestativo e te diz que a chave `'idade'` não existe nesse dicionário.

Quando usar um dicionário ou uma lista? Bem, um bom ponto para refletir. Pense em uma solução antes de olhar a resposta na próxima linha.
- Você precisa de uma sequência ordenada de itens? Use uma lista
- Você precisa associar valores com chaves, assim você pode procurá-los eficientemente (pela chave) mais tarde? Use um dicionário

Dicionários, como listas, são _mutáveis_, ou seja, que podem ser mudados depois que são criados. Você pode adicionar novos pares de chave/valor para o dicionário após sua criação, como:
```
>>> participante['linguagem_favorita'] = 'Python'
```

Como as listas, usar o método `len()` em dicionários retorna o número de pares chave-valor no dicionário. Vá em frente e digite o comando:
```

>>> len(participante)
4
```

Espero que agora faça sentido até agora. :) Pronta para mais diversão com dicionários? Pule na próxima linha para coisas incríveis.

Você pode usar o comando `pop()` para deletar um item no dicionário. Digamos, se você quer excluir a entrada correspondente a chave `'numeros_favoritos'`, basta digitar o seguinte comando:
```
>>> participante.pop('numeros_favoritos')
>>> participante
{'pais': 'Polonia', 'linguagem_favorita': 'Python', 'nome': 'Ola'}
```

Como você pode ver no retorno, o par chave-valor correspondente à chave `'numeros_favoritos'` foi excluído.

Além disso você pode mudar o valor associado com uma chave já criada no dicionário. Digite:
```
>>> participante.pop('numeros_favoritos')
>>> participante
>>> participante['pais'] = 'Alemanha'
>>> participante
{'pais': 'Alemanha', 'linguagem_favorita': 'Python', 'nome': 'Ola'}
```
Como você pode ver, o valor da chave `'pais'` foi alterado de `'Polonia'` para `'Alemanha'`. :) Emocionante?

Hurra! Você acabou de aprender outra coisa incrível.
