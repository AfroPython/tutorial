# Regex

Você quer saber como o Django coincide com URLs para views? Bem, esta parte é complicada. o Django usa o regex -- expressões regulares. Regex tem muito (muito!) de normas que formam um padrão de pesquisa. Como regexes são um tópico avançado, nós veremos em detalhes como elas funcionam.

Se você ainda quiser entender como criamos os padrões, aqui está um exemplo do processo - só precisamos um subconjunto limitado de regras para expressar o padrão que procuramos, ou seja:

```
^ para o início do texto
$ para o final do texto
\d para um dígito
+ para indicar que o item anterior deve ser repetido pelo menos uma vez
() para capturar parte do padrão
```

Qualquer outra coisa na definição de url será levada literalmente.

Agora imagine que você tem um site com o endereço assim: `http://www.mysite.com/post/12345/`, onde `12345` é o número do seu post.

Escrever views separadas para todos os números de post seria muito chato. Com expressões regulares podemos criar um padrão que irá coincidir com a url e extrair o número para nós: `^post/(\d+)/$`. Vamos aos poucos ver o que estamos fazendo aqui:

- ^ post / está dizendo ao Django para pegar tudo que tenha post / no início da url (logo após o ^)
- (\d+) significa que haverá um número (um ou mais dígitos) e que queremos o número capturado e extraído
- / diz para o Django que deve seguir outro /
- $ indica o final da URL significando que apenas sequências terminando com o / irão corresponder a esse padrão
