## O que acontece quando alguém solicita um site do seu servidor?

Quando chega uma requisição para o servidor web ela é passada para o Django que tenta descobrir do que ela se trata.

Primeiro ele pega um endereço web e tenta descobrir o que fazer. Essa parte é feita pelo **urlresolver** do Django.

> Note que o endereço de um site se chama URL - Uniform Resource Locator, em português Localizador de Recursos Uniforme, dessa forma o nome urlresolver, ou resolvedor de urls, faz sentido

 Isso não é muito inteligente - leva à uma lista de padrões e tenta corresponder a URL. O Django verifica padrões de cima para baixo e se algo é correspondido, passa a solicitação para a função associada (que é chamada view, vamos falar sobre ela mais tarde :) ).

Imagine um carteiro com uma carta. Ela está andando pela rua e verifica cada número de casa com a que está na carta. Se ele corresponder, ela coloca a carta lá. É assim que funciona o urlresolver!

Todas as coisas interessantes são feitas dentro da view: podemos dar uma olhada no banco de dados para procurar algumas informações. Talvez o usuário queira mudar algo nos dados? Como uma carta dizendo: "Por favor mude a descrição do meu emprego." - a view checa se você tem permissão para fazer isso e então atualiza a descrição do emprego pra você, enviando em seguida uma mensagem: "Feito!". Então a view gera uma resposta e o Django pode enviá-la para o navegador do cliente.

Claro, a descrição acima é muito simplificada, mas você não precisa saber detalhes técnicos ainda. Ter uma ideia geral já é suficiente.

Então, em vez de mergulhar em muitos detalhes, nós simplesmente vamos começar criando algo com o Django e aprenderemos todas as partes importantes ao longo do caminho!
