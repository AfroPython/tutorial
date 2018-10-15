# Arquivos estáticos no Django

Finalmente nós iremos ver mais de perto nessas coisas que chamamos de **arquivos estáticos**. 
Arquivos estáticos são todas as suas imagens e arquivos CSS -- arquivos que não são dinâmicos, então seu conteúdo não depende do contexto da requisição e será o mesmo para todos os usuários.

## Onde colocar os arquivos estáticos para Django

Django já sabe onde encontrar os arquivos estáticos para o built-in "admin" app. Agora só precisamos adicionar alguns arquivos estáticos para nosso próprio app, ```blog```.

Fazemos isso através da criação de uma pasta chamada ```static``` dentro do aplicativo do blog:


  ```djangogirls
├── blog 
│   ├── migrations
│   ├── static
│   └── templates
└── mysite 
```


Django encontrará automaticamente todas as pastas chamadas "static" dentro de qualquer uma das pastas dos seus apps, 
e será capaz de usar seu conteúdo como arquivos estáticos.
