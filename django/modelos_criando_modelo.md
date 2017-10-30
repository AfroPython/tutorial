# Criando o modelo `Post` do nosso blog

No arquivo `blog/models.py` definimos todos os objetos chamados `Modelos` - este é um lugar em que vamos definir nossa postagem do blog.

Vamos abrir `blog/models.py`, remova tudo dele e escreva o código como este:

```
from django.db import models
from django.utils import timezone

class Post(models.Model):
    author = models.ForeignKey('auth.User')
    title = models.CharField(max_length=200)
    text = models.TextField()
    created_date = models.DateTimeField(
            default=timezone.now)
    published_date = models.DateTimeField(
            blank=True, null=True)

    def publish(self):
        self.published_date = timezone.now()
        self.save()

    def __str__(self):
        return self.title
```
> Certifique-se de ter usado dois caracteres `(_)` em cada lado do str. Aqueles caracteres são usados freqüentemente em Python e às vezes os chamamos de `"dunder"` (abreviação de "double-underscore" ou "duplo sublinhado").
>


É assustador, não? Mas não se preocupe, vamos explicar o que estas linhas significam!

- Todas as linhas começando com `from` ou `import` são linhas que adicionam alguns pedaços de outros arquivos. Então em vez de copiar e colar as mesmas coisas em cada arquivo, podemos incluir algumas partes com `from... import ....`
- `class Post(models.Model)`: esta linha define o nosso modelo (é um objeto)
    - `class`: é uma palavra-chave especial que indica que estamos definindo um objeto
    - `Post`: é o nome do nosso modelo, podemos lhe dar um nome diferente (mas é preciso evitar os espaços em branco e caracteres especiais). Sempre comece um nome de classe com uma letra maiúscula
    - `models.Model`: significa que o Post é um modelo de Django, então o Django sabe ele que deve ser salvo no banco de dados

Agora podemos definir as propriedades que discutimos: `titulo`, `texto`, `data_criacao`, `data_publicacao` e `autor`. Para isso precisamos definir um tipo de campo (é um texto? É um número? Uma data? Uma relação com outro objeto, por exemplo, um usuário?):
- `models.CharField`: assim é como você define um texto com um número limitado de caracteres
- `models.TextField`: este é para textos longos sem um limite. Será ideal para um conteúdo de post de blog, certo?
- `models.DateTimeField`: este é uma data e hora
- `models.ForeignKey`: este é um link para outro modelo

Para explicar cada pedaço do código precisaríamos de muito tempo, caso você esteja curiosa(o) para saber mais sobre campos do Model e como definir coisas além destas descritas acima, você pode olhar a documentação do Django aqui:  https://docs.djangoproject.com/en/1.8/ref/models/fields/#field-types.

Voltando ao código... Que tal `def publish(self):`? É exatamente o nosso método de publish que falávamos antes.
- `def`: significa que se trata de um função/método
- `publish`: é o nome do método

Você pode alterar, se quiser. A regra é que usamos letras minúsculas e sublinhados em vez de espaços em branco (ou seja, se você quer ter um método que calcula o preço médio, você poderia chamá-lo `calculate_average_price`).

Métodos muitas vezes retornam algo, para isso usamos `return`. Um exemplo é método `__str__`. Nesse cenário, quando chamamos `__str__()` teremos um texto (**string**), com um título do Post.

Se algo ainda não está claro sobre modelos, sinta-se livre para pedir ajuda a sua treinadora! Sabemos que é muito complicado, especialmente quando você aprender o que são objetos e funções ao mesmo tempo. Mas espero que está parte pareça menos mágica para você agora!
