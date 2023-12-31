# Git

Git é um sistema de controle de versão criado por Linus Torvalds em 2005.

É usado para monitorar alterações em códigos, além de permitir colaboração de código e gerenciar repositórios.

## Git Workflow

Podemos separar o Git Workflow em três partes:

1. **Diretório de Trabalho**: É aqui que toda a organização do trabalho ocorre, incluindo a criação, edição ou exclusão de arquivos.

1. **Área de Preparação**: Neste estágio, todas as alterações feitas no **Diretório de Trabalho** são listadas para serem preparadas para a próxima confirmação.

1. **Repositório**: O Git armazena permanentemente todas as alterações e versões do projeto neste estágio, representando o histórico completo do desenvolvimento.

## Inicializando

Para inicializar um repositório, é usado o seguinte comando comando:

``` bash
git init
```

Esse comando deve ser usado na pasta do diretório. Ele irá inicializar um repositório vazio.

## Verificar Arquivos

É possível ver todos os arquivos e pastas em um diretório com o comando **`ls`** no terminal.

Para verificar quais arquivos foram adicionados, modificados ou excluídos em no repositório, pode-se usar:

``` bash
git status
```

Arquivos adicionados no diretório são *tracked*, já os arquivos não adicionados são *untracked*.

### Status Compacto

Com o parâmetro `--short`, as alterações são mostradas de maneira mais compacta.

``` bash
git status --short
```

**Os sinalizadores são:**

* **'`??`'**: Arquivos não rastreados.
* **'`A`'**: Arquivos adicionados.
* **'`M`'**: Arquivos modificados.
* **'`D`'**: Arquivos excluídos.

## Adicionar Arquivos

Para adicionar arquivos ao repositório, é usado o comando:

``` bash
git add nome_arquivo
```

Para adicionar todos os arquivos ao mesmo tempo, use **`--all`** ou **`-A`**, ou simplesmente **`.`**:

**Com `--all`:**

``` bash
git add --all
```

**Com `-A`:**

``` bash
git add -A
```

**Com `.`:**

``` bash
git add .
```

## Commit

Um commit é um registro permanente das alterações realizadas. Ao realizar um commit, você está efetivamente confirmando as mudanças que foram adicionadas à Área de Preparação.

Os commits formam um histórico do projeto e permitem rastrear a evolução do código ao longo do tempo. Além disso, commits servem de "save point" nos quais podemos voltar atrás caso necessário.

Ao fazer um commit, é obrigatório incluir uma mensagem.

**Sintaxe:**

``` bash
git commit -m "Mensagem descritiva do commit"
```

A mensagem deve respeitar as seguintes regras:

* Estar entre aspas (duplas ou simples).
* Resumir o que foi feito naquela versão.
* Possui 50 caracteres ou menos.
* Suceder imediatamente o parâmetro `-m`.

O parâmetro `--all` (ou `-a`) adiciona automaticamente todas as alterações já rastreadas (*tracked*) à Área de Preparação antes de fazer o commit.

**Exemplo:**

``` bash
git commit -a -m "Mensagem"
```

## Consultar Versões

### `git log`

O comando **`git log`** permite consultar versões anteriores do projeto. Todos os commits são armazenados em ordem cronológica no repositório, e o comando `git log` permite visualizá-los.

**Sintaxe:**

``` bash
git log
```

Esse comando retornará algumas informações:

* Um texto que possui 40 caracteres chamado *SHA* (*Secure Hash Algorithm*). Esse texto especifica o commit.
* O autor do commit.
* A data e o horário do commit.
* A mensagem do commit.

### `git diff`

O comando **`git diff`** compara um arquivo em sua versão na Área de Trabalho com o mesmo arquivo na Área de Preparação, mostrando suas diferenças.

**Sintaxe:**

``` bash
git diff nome_arquivo
```

## `git help`

Para ver uma lista de todos os comandos, você pode usar o comando de ajuda.

``` bash
git help --all
```

Para ver todas as opções disponíveis para um comando específico, use o parâmetro **`-help`**.

``` bash
git comando -help
```

> OBS.: Use *SHIFT + G* para pular para o final da lista caso você fique preso na visualização da lista.

## Branches

Uma **branch** é uma versão diferente da principal. Elas permitem trabalhar com diferentes partes de um projeto sem impactar a branch original.

Branches permitem que você trabalhe em novos recursos ou correções de bugs sem interferir diretamente na branch principal.

Quando o trabalho está completo, pode ser feito um **merge**, que é mesclar uma branch à branch principal.

**Criar nova branch:**

``` bash
git branch nome_branch
```

**Ver branches:**

Usar apenas `git branch` retorna uma lista com todas as branches.

``` bash
git branch
```

### Alternância entre Branches

O comando **`git checkout`** permite alternar para outra branch.

**Sintaxe:**

``` bash
git checkout nome_branch
```

Para criar uma branch e trocar para ela, use o parâmetro **`-b`**.

``` bash
git checkout -b nome_da_nova_branch
```

### Branch Principal

Ao criar um repositório, as branches principais se chamam **master**, mas o nome **main** hoje é considerado o padrão.

Ao optar por usar "main" em vez de "master", os desenvolvedores buscam promover uma linguagem mais inclusiva e evitar o uso de termos que possam ser considerados ofensivos ou insensíveis.

**Alterar de master para main:**

``` bash
git branch -M main
```

Esse comando converte a branch principal "master" para "main".

### Renomear Branch

Para renomear uma branch, é usado o parâmetro `-m`, seguido do nome atual da branch e um novo nome para ela.

**Sintaxe:**

``` bash
git branch -m nome_atual novo_nome
```

### Excluir Branch

Para excluir uma branch é usado o parâmetro **`-d`**.

``` bash
git branch -d nome_branch
```

Caso haja alterações não registrar (com commit), não será possível excluir essa branch com `-d`, ao invés disso, use **`-D`** que força a exclusão.

``` bash
git branch -D nome_branch
```

### Replicar Branch

O comando **`git rebase`** replica as alterações de uma branch à branch atual.

**Sintaxe:**

``` bash
git rebase branch_a_ser_replicada
```

Ele pegará todos os commits que foram feitos na branch especificada e os aplicará na branch atual, em seguida, aplicará os commits locais feitos na branch atual.

### Merge

O comando **`git merge`** mescla uma branch à branch atual.

**Sintaxe:**

``` bash
git merge nome_da_branch
```
