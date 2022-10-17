# Estudos sobre GIT #

- Logo abaixo terá os principais comandos utilizados para versionamento e gerenciamento de código utilizando GIT.
> _Utilize o Git Bash ou o Terminal para executar os comandos_

<br>

## Configurando Git ##

> `git --version`

##### ^ Mostra a versão do seu Git <br><br><br>

> `git config --local user.name "Seu Nome"`

##### ^ Utilizado determinar o user name do repositório _local_. <br> Para determinar o user name _global_, bastar trocar o ```--local``` para ```--global```.<br><br><br>

> `git config --local user.email "Seu email"`

##### ^ Utilizado determinar o user email do repositório _local_. <br> Para determinar o user email _global_, bastar trocar o ```--local``` para ```--global```. <br><br><br><br>

## Criando repositório e commitando ##

> `git init`

##### ^ Inicializa o repositório local<br><br><br>

> `git init --bare`

##### ^ Inicializa o repositório local puro, o qual irá armazenar apenas as alterações de arquivos <br><br><br>

> `git add nome_arquivo`

##### ^ Adiciona um determinado arquivo ao repositório. <br> Para adicionar todos os arquivos de uma pasta, basta trocar o `nome_arquivo` para `.`<br><br><br>

> `git commit -m "Mensagem de commit"`

##### ^ Cria um _commit_ dos arquivos adicionados, ou seja, captura o estado atual dos arquivos e os guarda em uma espécie de unidade de blocos de construção.<br><br><br>

> `mkdir nome_pasta`

##### ^ Cria um repositório local pelo _Git Bash_ <br><br><br><br>

## Criando uma conexão ##

> `git remote`

##### ^ Lista todas as conexões presentes no repositório <br><br><br>

> `git remote add link_conexão`

##### ^ Adiciona uma conexão, pode ser local ou remota para fazer o envio de arquivos. <br> Essas conexões podem ser links ou o caminho de uma determinada pasta local. <br><br><br>

> `git remote -v`

##### ^ Mostra o link ou caminho da conexão <br><br><br>

> `git remote rm nome_conexao`

##### ^ Remove a conexão `nome_conexao` <br><br><br><br>

## Enviando arquivos do repositório local para o remoto ##

> `git push nome_conexao nome_branch`

##### ^ Envia os arquivos presentes na branch `nome_branch` para o repositório remoto `nome_conexao` <br><br><br>

> `git push -u nome_conexao nome_branch`

##### ^ Toda vez que der um `git push` vai enviar os arquivos presentes na branch `nome_branch` para o repositório remoto `nome_conexao` <br><br><br><br>

## Trazendo arquivos do repositório remoto para o local ##

> `git pull nome_conexao nome_branch`

##### ^ Traz os arquivos do repositório remoto para o local <br><br><br><br>

## Criando e mudando de branchs ##

> `git branch`

##### ^ Lista todas as _branchs_(ramificações) presentes no seu repositório <br><br><br>

> `git branch nome_branch`

##### ^ Cria uma nova branch <br><br><br>

> `git checkout nome_branch`

##### ^ Muda para a branch `nome_branch`  <br><br><br>

> `git checkout -b nome_branch`

##### ^ Atalho para criar uma branch e já mudar para ela <br><br><br>

> `git checkout [hash abrev.]`

##### ^ Navega pela linha do tempo dos commits <br><br><br><br>

## Analisando Logs ##

> `git log`

##### ^ Mostra informações dos commits já realizados no projeto <br><br><br>

> `git log --oneline`

##### ^ Mostra informações dos commits abreviados em uma linha <br><br><br>

> `git log --graph`

##### ^ Mostra gráfico do caminho das branchs <br><br><br>

> `git log -p`

##### ^ Mostra todas as informações detalhadas dos commits já realizados no projeto <br><br><br>

> `git log --pretty="format: %H"`

##### ^ Filtra as informações dos commits mostrando o _hash_ dos commits <br><br><br>

> `git log --pretty="format: %h %s %ae"`

##### ^ Filtra as informações dos commits mostrando o _hash_ abreviado dos commits, o nome dos commits e o email do autor <br><br><br>

> `git diff [hash abrev.]..[hash abrev.]`

##### ^ Mostra as diferenças desde o commit indicado <br><br>

[Para mais informações sobre Git Logs](https://devhints.io/git-log) <br><br><br>

## Juntando arquivos de duas _branchs_ distintas ##

> `git merge nome_branch`

##### ^ Faz a junção da branch `nome_branch` com a sua branch atual. <br> Vale lembrar que se for alterado as mesmas coisas nas duas branchs vai dar erro na hora de mergear. É preciso escolher qual trecho do código você quer deixar <br><br><br>

> `git rebase nome_branch`

##### ^ Commita e aplica os commits da branch `nome_branch` na atual, trazendo todo o histórico da `nome_branch`.  <br><br>

[Para saber mais sobre Git Merge e Rebase](https://www.edureka.co/blog/git-rebase-vs-merge/) <br><br><br>

## Desfazendo alterações(CTRL+Z no GIT) ##

> `git checkout -- <nome_arquivo>`

##### ^ Desfaz as alterações antes do `git add`  <br><br><br>

> `git reset HEAD <nome_arquivo>`

##### ^ Desfaz as alterações mesmo depois de executar o `git add`  <br><br><br>

> `git revert [hash do commit]`

##### ^ Desfaz as alterações mesmo depois de um `git commit`  <br><br><br><br>

## Salvando mudanças temporariamente sem usar `git commit` ##

> `git stash`

##### ^ Salva um arquivo temporariamente antes mesmo do `git add` ou `git commit`  <br><br><br>

> `git stash list`

##### ^ Mostra lista de arquivos salvos temporariamente  <br><br><br>

> `git stash apply [número da posição na stash list]`

##### ^ Aplica as alterações da stash na posição indicada <br><br><br>

> `git stash drop`

##### ^ Tira da stash a alteração aplicada  <br><br><br>

> `git stash pop`

##### ^ Atalho para o `git stash apply` e o `git stash drop` juntos da última alteração da stash  <br><br>

[Para saber mais sobre Git Stashes(opção 1)](https://blog.betrybe.com/git/git-stash/) <br>
[Para saber mais sobre Git Stashes(opção 2)](https://git-scm.com/docs/git-stash) <br><br><br>

## Criandos Tags e Releases ##

> `git tag -a v0.1.0`

##### ^ Cria uma tag como se fosse uma release da aplicação <br><br><br>

> `git push nome_conexão nome_tag`

##### ^ Envia a tag/release para o repositório remoto <br><br><br><br>

## Junção de Commits ##

> `git rebase -i HEAD [hash do commit anterior ao que você quer juntar]`

##### ^ Faz a junção de _commits_ <br><br><br>

> `git rebase -i HEAD~2`

##### ^ Faz a junção dos dois últimos _commits_ <br><br><br>

> `git cherry-pick [hash]`

##### ^ Traz o _commit_ selecionado para a branch que você está <br><br><br><br>

## Encontrando erros e buscando por _Commits_ ##

> `git bisect start`

##### ^ Inicializa a busca por _commits_ <br><br><br>

> `git bisect bad HEAD`

##### ^ Informa para o git onde está o bug <br><br><br>

> `git bisect good [hash]`

##### ^ Informa para o git até onde você quer fazer a busca <br><br><br>

> `git bisect good`

##### ^ Informa para o git que naquele _commit_ está ok <br><br><br>

> `git bisect bad`

##### ^ Informa para o git que naquele _commit_ está o erro <br><br><br>

> `git bisect reset`

##### ^ Encerra a busca <br><br><br>

> `git show [hash]`

##### ^ Mostra as alterações que foram feitas <br><br><br>

[Para saber mais sobre Git Bisect e busca de erros(Opção 1)](https://git-scm.com/docs/git-bisect) <br>
[Para saber mais sobre Git Bisect e busca de erros(Opção 2)](https://brizeno.wordpress.com/2012/11/07/encontrando-erros-com-git-bisect/) <br><br><br>

## Fork ##

  O Fork faz uma cópia do repositório do Github de uma pessoa, para o seu Github.<br><br>

## Pull Request ##

  O Pull Request faz um pedido de envio de modificação a um código de alguém
