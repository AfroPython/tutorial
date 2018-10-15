## Template (modelos)

Precisamos criar um arquivo `post_edit.html` na pasta `blog/templates/blog`. Pra fazer o formulário funcionar precisamos de muitas coisas:

- Temos que exibir o formulário. Podemos fazer isso com (por exemplo) um simplesmente {% raw %}`{{ form.as_p }}`{% endraw %}.
- A linha acima precisa estar entre as tags HTML form: `<form method="POST">...</form>`
- Precisamos de um botão `Salvar`. Fazemos isso com um botão HTML: `<button type="submit">Save</button>`
- E finalmente, depois de abrir a tag `<form ...>` precisamos adicionar um {% raw %}`{% csrf_token %}`{% endraw %}. Isso é muito importante, pois faz com que nosso formulário seja seguro! O Django vai reclamar se você esquecer de adicionar isso e tentar salvar o formulário:

![CSFR Página Proibida](images/csrf2.png)

Beleza, então vamos ver como ficou o HTML `post_edit.html`:

blog/templates/blog/post_edit.html
```html
{% extends 'blog/base.html' %}

{% block content %}
    <h1>New post</h1>
    <form method="POST" class="post-form">{% csrf_token %}
        {{ form.as_p }}
        <button type="submit" class="save btn btn-default">Save</button>
    </form>
{% endblock %}
```

Hora de atualizar! Há! Seu formulário apareceu!

![Formulário novo](images/new_form2.png)

Mas, espere um minuto! Quando você digita alguma coisa nos campos `title` e `text` e tenta salvar, o que acontece?

Nada! Estamos novamente na mesma página e nosso texto sumiu... E nenhum post foi adicionado. Então o que deu errado?

A resposta é: nada. Precisamos trabalhar um pouco mais na nossa *view*.
