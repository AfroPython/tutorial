## Limpando

Não queremos deixar uma bagunça, então vamos remover tudo o que fizemos até agora.

Primeiro precisamos voltar para nosso workspace (área de trabalho):

```
$ cd ..
```

Fazendo cd para .. nós mudaremos do diretório atual para o diretório pai (que significa o diretório que contém o diretório atual).

Veja onde você está:

```
$ pwd
/home/cabox/workspace
```

Agora é hora de excluir o diretório **minhapasta**.

**Atenção:** A exclusão de arquivos usando del, rmdir ou rm é irrecuperável, significando _Arquivos excluídos vão embora para sempre!_

Então, tenha cuidado com este comando.

```
$ rm -r minhapasta
```

Pronto! Para ter certeza que a pasta foi excluída, vamos checar:

```
$ ls
```

Por enquanto é isso!
