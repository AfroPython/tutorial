# Seu primeiro projeto Django!

> Parte deste capítulo é baseado nos tutoriais do Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).
Parte deste capítulo é baseado no django-marcador tutorial licenciado sobre Creative Commons Attribution-ShareAlike 4.0 International License. O tutorial do django-marcador é protegido por direitos autorais por Markus Zapke-Gründemann et al.

Nós vamos criar um blog simples!

O primeiro passo para criá-lo é começar um novo projeto de Django. Existirá um exemplo de pasta de um projeto em Django criada, porém esse projeto não funcionará do modo como precisamos, então vamos criar um projeto.
Considerando o ambiente criado para nós, precisamos instalar a biblioteca do Django para executar alguns comandos, então execute o seguinte comando para instalar:
```
pip install django --user
```
Observação: Dentro do nosso IDE é necessário autenticar com o usuário do ambiente para poder instalar pacotes não existente, então precisamos informar o comando `--user` no nosso comando de instalação do pacote do Django.

Para iniciar um novo projeto, acesse um terminal do IDE e certifique-se que se encontra na pasta `/projects`. Logo após, execute o seguinte comando:
```
python -m django startproject afropython
```
Após executar a criação do projeto, onde a última instrução `afropython` é o nome escolhido por nós para o nosso projeto Django. Será criada uma pasta com o nome do projeto informado com todo o esqueleto de um projeto Django foi criado para nós: um bando de diretórios e arquivos que usaremos mais tarde.

Entre dentro da pasta do projeto criada usando o comando `cd afropython` e logo após digite `ls` para visualizar seu conteúdo. Observação: Outra forma de consultar o conteúdo do nosso projeto e acessando `View>Explorer`, ou clicando no primeiro ícone do menu lateral esquerdo do IDE ou usando o atalho `CTRL+Shift+e`.

Os nomes de alguns arquivos e diretórios são muito importantes para o Django. Não renomeie os arquivos que estamos prestes a criar. Mover para um lugar diferente também não é uma boa idéia. Django precisa manter uma determinada estrutura para ser capaz de encontrar coisas importantes.

`manage.py` é um script que ajuda com a gestão do site. Com isso seremos capazes de iniciar um servidor de web no nosso computador sem instalar nada, entre outras coisas.

O arquivo `settings.py` contém a configuração do seu site.

Lembra quando falamos sobre um carteiro verificando onde entregar uma carta? arquivo `urls.py` contém uma lista dos padrões usados por `urlresolver`.

Vamos ignorar os outros arquivos por agora - nós não vamos mudá-los. A única coisa a lembrar é não excluí-los por acidente!
