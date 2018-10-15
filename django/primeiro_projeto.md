# Seu primeiro projeto Django!

> Parte deste capítulo é baseado nos tutoriais do Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).
Parte deste capítulo é baseado no django-marcador tutorial licenciado sobre Creative Commons Attribution-ShareAlike 4.0 International License. O tutorial do django-marcador é protegido por direitos autorais por Markus Zapke-Gründemann et al.

Nós vamos criar um blog simples!

O primeiro passo para criá-lo é começar um novo projeto de Django. Basicamente, isto significa que vamos executar alguns scripts fornecidos pelo Django que irá criar o esqueleto de um projeto Django para nós: um bando de diretórios e arquivos que usaremos mais tarde.

Os nomes de alguns arquivos e diretórios são muito importantes para o Django. Não renomeie os arquivos que estamos prestes a criar. Mover para um lugar diferente também não é uma boa idéia. Django precisa manter uma determinada estrutura para ser capaz de encontrar coisas importantes.

> **Nota:** Verifique que você incluiu o ponto (.) no final do comando, é importante porque diz ao script para instalar o Django em seu diretório atual.

No console, você deve executar (lembre-se de não digitar ``~/afropython$``  , OK?):

```
~/afropython$ django-admin startproject mysite .
```

`Django-admin` é um script que irá criar os diretórios e arquivos para você. Agora, você deve ter um diretório estrutura que se parece com isso:

```
afropython
├───manage.py
└───mysite
        settings.py
        urls.py
        wsgi.py
        __init__.py
```

`manage.py` é um script que ajuda com a gestão do site. Com isso seremos capazes de iniciar um servidor de web no nosso computador sem instalar nada, entre outras coisas.

O arquivo `settings.py` contém a configuração do seu site.

Lembra quando falamos sobre um carteiro verificando onde entregar uma carta? arquivo `urls.py` contém uma lista dos padrões usados por `urlresolver`.

Vamos ignorar os outros arquivos por agora - nós não vamos mudá-los. A única coisa a lembrar é não excluí-los por acidente!
