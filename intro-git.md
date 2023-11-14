<h1 align="center">Introdução ao Git</h1>

> *Git é um sistema de controle de versão que permite a criação de repositórios para a guarda e controle de atualizações de um projeto para a organização de equipe.*
> 

# 💿 O que é controle de versão?

Controle de versão é um sistema que grava alterações para um arquivo ou conjunto de arquivos ao longo de um tempo necessário para recuperação dessas versões. Ele te permite reverter alterações de um arquivo selecionado ou de um projeto todo, comparar mudanças ao longo do tempo, observar o responsável pelas alterações e etc.

# 🔰 Como funciona o Git?

<div align="center"><img src="https://git-scm.com/book/en/v2/images/snapshots.png"></div>

Todas as vezes que você commita ou salva o estado do seu projeto, o Git tira uma foto de como o seu arquivo se parece nesse momento e guarda uma referência daquela foto. Caso o arquivo não foi alterado naquela versão, o Git não rearmazena aquele arquivo, apenas guarda um link para o arquivo idêntico que já foi guardado (File B na imagem).

Com esse raciocínio, o Git pensa nos dados como um fio de imagens e se transforma em um pequeno sistema de arquivos que funciona do topo e se atualiza sobre ele.

## Os três estados do Git

Existem três estados principais no qual o seu arquivo pode ficar:

- **Modified**
    
    Significa que houve uma mudança no arquivo mas não foi commitado ainda.
    

- **Staged**
    
    Significa que o arquivo modificado foi marcado na versão atual e vai entrar no próximo commit.
    

- **Committed**
    
    Significa que as informações do arquivo está seguramente armazenada no repositório local.
    

<div align="center"><img src="https://git-scm.com/book/en/v2/images/areas.png"></div>

O fluxo de trabalho do Git funciona da seguinte forma:

1. Um arquivo é modificado na área de trabalho (Working Directory);
2. Preparamos apenas as mudanças que queremos que façam parte do próximo commit e as adicionamos (Stage Fixes) apenas elas na área de preparação (Staging Area);
3. Commitamos (Commit), o que faz com que os arquivos que estão na área de preparação e armazenam uma foto que ficará permanentemente guardado no repositório (.git directory);
4. A versão mais atualizada do projeto agora está na área de trabalho (Checkout the project).

# ⚙️ Instalação e configuração

No Windows é necessário baixar o programa por esse site [**neste link**](https://git-scm.com/).

Depois de instalação é preciso abrir o Git Bash e configurar o seu espaço de trabalho.

```bash
git config --global user.name "nome"
git config --global user.email "e-mail"
```

No terminal é preciso configurar o nome do usuário e o endereço de e-mail de quem está responsável por aquele repositório local para então termos a responsabilidade no momento da distribuição de tarefas.

Com o comando `--global` só é preciso fazer esse comando uma única vez ao instalarmos o programa.

Para conferir as credenciais do seu cadastro e outras configurações padrões do Git é preciso dar o seguinte comando:

```bash
git config --list
```

É recomendado que se cadastre o mesmo endereço de e-mail utilizado no cadastro do GitHub, caso for utilizá-lo como repositório remoto padrão.

# 🧭 Navegando pelos diretórios e criando um repositório

O terminal é sempre aberto na raiz do computador, ou seja, no (C:), dessa forma precisamos navegar pelos diretórios até chegar no arquivo em que queremos criar o nosso repositório e o nosso projeto. Dentro do Git, pastas são chamadas de diretórios, que são onde armazenamos os nossos arquivos.

```bash
mkdir nome-do-diretorio
touch index.html
```

Para criar um diretório novo é preciso dar o comando `mkdir` e, para criar um novo arquivo, é preciso dar o comando `touch` indicando o nome do diretório ou do arquivo (sempre com a extensão do mesmo).

O comando `ls` lista todo o conteúdo existente dentro de um diretório, seja eles arquivos ou outros diretórios.

```bash
ls
```

```bash
cd nome-do-diretorio
cd nome-do-diretorio-maior/diretorio-do-projeto
```

O comando `cd` faz com que o termina entre no diretório informado. Podemos informar diretório por diretório ou então passamos todo o caminho de uma vez. Caso o nome do diretório tiver espaço, no terminal é preciso informar com aspas simples, por exemplo, `‘Meus Documentos’`.

Dentro do diretório que queremos manipular e onde está o nosso projeto damos o comando `init`. É sempre importante observar o diretório em que estamos dando esse comando, pois muitos projetos precisam ser iniciados dentro da pasta criada pelo framework ou biblioteca uma vez em que os arquivos na raiz são essenciais para momentos como o deploy do projeto.

```bash
git init
```

## Manipulando pastas pelo terminal

Da mesma forma que criamos, deletamos, movemos e renomeando pastas pelo Explorador de Arquivos do nosso computador, conseguimos realizar essas operações pelo terminal.

```bash
rm nome-do-arquivo
rm -rf nome-do-diretorio
```

O mesmo comando é usada para deletar um arquivo e um diretório, no entanto para o diretório precisamos informar `-rf` e então passar o nome do arquivo ou do diretório.

```bash
mv nome-do-arquivo caminho-ate-diretorio-desejado
```

Conseguimos também mover um arquivo até outro diretório pelo terminar usando o comando `mv` e passando o nome do arquivo e o caminho de onde ele está até o lugar desejado.

Para alterar o nome de um arquivo podemos usar o mesmo comando porém passamos o nome atual do arquivo e logo em seguido o nome que desejamos que tenha agora.

```bash
mv nome-atual nome-desejado
```

## Clonando um repositório

Caso já exista um repositório que é desejado estar na nossa máquina local é possível clonar esse repositório, que é nada mais nada menos do que uma cópia completa do repositório em sua versão mais atual no momento do comando.

```bash
git clone endereco-do-repositorio
```

O `clone` é muito usado com equipes no momento em que cada membro deve ter o projeto em sua máquina local e compartilham um repositório remoto. Ou então quando temos uma máquina corrompida, podemos recuperar o nosso projeto do remoto através desse comando.

# 💾 Gravando alterações no repositório

Os arquivos de um repositório podem ter dois estados:

- **Tracked**
    
    São arquivos que estavam presentes na última foto ou arquivos recém-adicionados na área de preparação. Eles podem ser arquivos `unmodified`, `modified` ou `staged`. Um repositório clonado já possui arquivos rastreados.
    

- **Untracked**
    
    São arquivos que ainda não foram alterados, então não estão sendo rastreado pelo Git, ou seja, não estavam na última foto e nem foram adicionados na área de preparação. Podem ser arquivos recém-criados.
    

<div align="center"><img src="https://git-scm.com/book/en/v2/images/lifecycle.png"></div>

O estado do arquivo se altera conforme atualizamos as informações e damos os comandos. Por exemplo, ao ser criado o arquivo está como `untracked` e então se transforma em `staged` uma vez que o adicionamos na área de preparação.

Quando o arquivo já foi comitado ele se está `unmodified` e quando é editado se transfoma em `modified`. Todas as vezes em que um arquivo for adicionado para a área de preparação ele fica como `staged`. E ao removermos o arquivo ele volta a ser `untracked`.

A gravação de uma alteração acontece com um conjunto de comandos, mas que chamamos este momento de comitar. O primeiro passo é entender qual é o momento atual do nosso repositório.

```bash
git status
```

O `status` mostra o que está em nossa árvore no momento. Se ele não mostrar nada quer dizer que não temos nada para comitar. Caso contrário, ele nos mostra os arquivos `untracked` e `modified`, que são aqueles que devemos adicionar na área de preparação.

O `add` adiciona os arquivos para a área de preparação. Todos os arquivos adicionados se transformam em `staged` e no `status` ficam da cor verde, informando que podem ser comitados. Ao dar o comando com `.` estamos informando que queremos adicionar todos os arquivos alterados, ou podemos adicionar um arquivo específico por vez.

```bash
git add .
git add nome-do-arquivo.html
```

```bash
git commit -m "mensagem especificando o que está sendo modificado"
```

O `commit` grava as alterações no diretório .git e guarda uma mensagem que específica o que foi modificado, dessa forma conseguimos recuperar com mais facilidade um momento do nosso projeto quando necessário.

O `log` mostra um histórico de commits criados dentro do projeto. Ele informa a pessoa que enviou a alteração, quando e a mensagem de commit, tudo em ordem cronológica.

```bash
git log
```

## Revertendo mudanças em commits

Imaginamos que comitando uma alteração no projeto, porém depois percebemos que o código está com erro e precisamos voltar ao momento anterior ao commit.

```bash
git reset --soft numero-do-head
git reset --mixed numero-do-head
git reset --hard numero-do-head
```

Com o `reset` conseguimos retornar para o commit indicado no head. Há três formas que fazer esse comando: o `soft`, que vai retornar para o momento `staged` mas sem comitar; o `mixed` volta para o momento antes de adicionar os arquivos para a área de preparação; e o `hard` que apaga tudo do commit resetado e retorna todos os arquivos para o momento antes do commit.

Com o `revert` conseguimos reverter o commit indicado voltando ao estado anterior dele, porém não perdemos o seu commit, o que nos possibilidade de voltar para o commit que revertemos para comparar e analisar possíveis erros.

```bash
git revert --no-edit numero-do-head
```

## Entendendo o que foi modificado

Caso quisermos ver o que foi modificado no nosso código desde o último commit, podemos dar o seguinte comando:

```bash
git diff
git diff --name-only
git diff nome-do-arquivo
```

O `diff` nos informa cada linha que foi alterada desde o último commit, mostrando como está registrado no `log` e como está agora no `unmodified` e `untracked` dentro do terminal mesmo.

O segundo comando mostra apenas os nomes dos arquivos que foram alterados e o terceiro mostra as mudanças apenas no arquivo indicado.

Caso queremos desfazer as alterações feitas em um arquivo ainda não comitado, podemos passar o comando de `checkout HEAD` passando o nome do arquivo para desfazer as alterações:

```bash
git checkout HEAD -- nome-do-arquivo
```

# 🔛 Atualizando o repositório remoto e local

Os repositórios remotos são versões dos nossos projetos hospedados na Internet ou em alguma rede em algum lugar (servidor). Esses espaços são úteis quando estamos trabalhando em colaboração com outras pessoas, pois conseguimos subir e baixar informações dos projetos atualizados de forma síncrona.

Conseguimos conectar o nosso repositório local com algum repositório remoto, dessa forma todas as vezes que comitamos alguma alteração no nosso projeto podemos subi-la e compartilhar as versões mais atualizadas com a nossa equipe.

```bash
git remote add origin url-do-repositorio
```

O `remote add origin` informa o endereço do repositório remoto, criando essa conexão entre os dois. É preciso adicionar o endereço apenas uma vez no início do projeto, em sua criação.

Caso algum repositório local já estiver conectado com um remoto mas não sabemos qual, é possível dar o seguinte comando para conferir onde estão indo as nossas alterações:

```bash
git remote -v
```

```bash
git push origin main
git push -u origin main
git push
```

O `push` é o processo de enviar as alterações comitadas localmente para o repositório remoto. Na primeira vez de cada projeto precisamos informar a `origin` e a branch que queremos subir as alterações, no caso a `main`. Caso sempre use em um projeto uma única branch, o primeiro comando deve ser feito com o `-u` para que então das próximas vezes o comando seja apenas `git push`. Caso use diversas branches, é recomendado sempre dar o `git push origin` e o nome da branch.

O `pull` é o processo inverso ao `push`, ou seja, puxa as alterações remotas para o repositório local. Isso acontece quando alguém da nossa equipe atualiza o repositório e precisamos colocar essas atualizações no nosso projeto local.

```bash
git pull
```

# 🌿 Trabalhando com *branches*

Branch significa que você diverge da linha principal de desenvolvimento e continua a trabalhar sem bagunçar a linha principal, ou seja, imaginando que o nosso fluxo é uma árvore, sendo a main o nosso tronco, conseguimos criar galhos ramificando nosso projeto e trabalhando em pontos distintos de nosso projeto sem afetar o trabalho principal.

Ao criarmos um repositório temos a branch principal (atualmente chamada de `main` e não master) que armazena alguns commits. Conseguimos então criar uma nova `branch` chamada `iss53` e ao trabalharmos nela conseguimos criar novas versões do projeto sem afetar o desenvolvimento na `main`. Na branch principal estamos na atualização C2, enquando na outra branch estamos na C3.

<div align="center"><img src="https://git-scm.com/book/en/v2/images/basic-branching-3.png"></div>

```bash
git branch
```

Ao darmos este comando recebemos uma lista das branches existentes no nosso projeto. Todo projeto possui uma `master` ou uma `main`, que se refere a branch principal. Ao lado do nome da branch fica um asterisco que indica a branch onde estamos trabalhando no momento.

Para criar uma nova `branch` é preciso passar o nome que queremos dar para a nossa ramificação. O nome escolhido deve ser coerente com as boas práticas da equipe e do projeto.

```bash
git branch nome-branch-nova
```

As alterações feitas em uma branch não são passadas automaticamente para as outras branches, por isso devemos sempre prestar atenção no lugar onde estamos realizando o nosso trabalho e os commits para não atrapalharmos o desenvolvimento dos outros integrantes da nossa equipe.

```bash
git checkout branch-desejada
```

Para mudarmos de branch precisamos passar o `checkout` com o nome da branch que queremos ir, então se queremos ir para a main passamos o seu nome ou se estamos na branch v02 passamos o seu nome.

## Manipulando as *branches*

Conseguimos manipular não apenas as informações e arquivos de diversas *branches*, mas também as próprias *branches*.

```bash
git push origin nome-da-branch
```

Podemos deletar uma branch remota passando o comando `push origin` com o dois pontos. Dessa forma excluímos a branch de nosso repositório remoto, principalmente se ele estiver vazio ou não estiver sendo utilizado.

Para deletar uma branch localmente utilizamos o comando `branch -D` informando o nome da branch. Lembrando que para o comando funcionar é preciso sair da branch que deseja apagar.

```bash
git branch -D nome-da-branch
```

Dentro do fluxo de trabalho do Git, sempre que finalizamos o trabalho dentro de uma branch (por exemplo, uma funcionalidade que já foi implementada e testada) é necessário subi-la para a branch principal, a `main`. Para isso, o primeiro comando que precisamos dar é um `checkout` para a branch principal e então damos o seguinte comando:

```bash
git merge branch-mergeada
```

O `merge` une a branch informada no comando com a branch que estamos posicionados no terminal. Ou seja, se estamos na `main`, todas as alterações feitas na branch serão implementadas nela.

<div align="center"><img src="https://git-scm.com/book/en/v2/images/basic-merging-1.png"></div>

No fluxo de trabalho, as branches trabalham de forma paralela, onde possuem um ancestral comum (na imagem, C2). No momento do `merge`, as alterações da branch que queremos mergear (na imagem, a iss53 com o C5) são atualizadas dentro da branch que queremos (no exemplo a master). Dessa forma, temos que ser cuidadosos com as alterações e possíveis conflitos entres as versões dentro de cada branch.

# 🚫 Ignorando arquivos

O arquivo `.gitignore` reune uma lista de diretórios e arquivos que desejamos não adicionar automaticamente no nosso diretório .git, mas que de alguma forma são necessários para o desenvolvimento do nosso projeto.

# 🤝 Contribuições de repositórios terceiros

Dentro do Github conseguimos fazer colaborações com repositórios de outras pessoas. Isso é possível por causa de dois conceitos: o `fork` e o `pull request`.

Imaginamos que estamos trabalhando em equipe e temos um repositório criado por um membro onde estamos colaborando com o desenvolvimento do projeto. O primeiro passo é, dentro deste repositório da equipe, clicamos em `fork`, que vai criar uma versão deste projeto no nosso repositório remoto e então damos um clone para termos esse projeto localmente. O fork é usado tanto para realizar alterações no repositório de alguém ou para usar um repositório de terceiros como base para o nosso próprio projeto.

Após realizarmos as alterações, realizarmos todo o processo de commit e subirmos a versão atualizada para o nosso repositório remoto, utilizaremos o `pull request` para enviarmos uma solicitação de alteração para o repositório remoto original. O pull request é uma requisição de um pull, é o pedido que fazemos para o colaborador principal daquele repositório sugerindo uma alteração em alguma parte do projeto e conseguimos informar o porquê que achamos aquela alteração que fizemos pertinente para o projeto como um todo. A pessoa dona do repositório então tem a chance de aceitar o nosso commit ou não.
