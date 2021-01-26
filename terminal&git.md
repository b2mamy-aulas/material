### Noções de Terminal
O terminal nada mais é que outra forma de interagir com o computador. Estamos habituados a utilizar uma interface gráfica composta de janelas e ícones para realizar as tarefas que necessitamos no dia-a-dia, como abrir um editor de texto, salvar um arquivo ou acessar uma página da internet.

Essas mesmas atividades podem ser realizadas unicamente através de comandos no terminal. Ainda que esse método possua uma maior curva de aprendizado, ele possibilita uma flexibilidade e agilidade muito grande, de forma que ele se torna uma ferramenta de trabalho diário da maioria dos programadores.

```
windows: procure por *cmd* no menu iniciar  
macos: procure por *terminal* no Spotlight
```

| Comando | Descrição |
|---------|-----------|
| cd | muda de diretório |
| dir (windows) | lista os arquivos do diretório atual |
| ls (mac/linux) | lista os arquivos do diretório atual |
| pwd | vê diretório |
| cd nome-da-pasta | vai para a pasta escolhida |
| mkdir nome-da-pasta | cria uma pasta |
| touch nome-do-arquivo | cria arquivo |


### Versionamento

Em projetos de desenvolvimento existe um processo constante no qual os arquivos referentes a cada entrega devem ser revisados e publicados. Isso é chamado de versionamento, pois cada etapa fechada representa uma nova versão do código. 
A importância deste processo é ter o histórico de todo projeto, quem foram os autores, a data de modificação e quais alterações feitas. 

Outros benefícios que existem em ter este processo vigente em um projeto de desenvolvimento são:
- inclusão de funcionalidades;
- mudanças ou melhorias de código;
- pequenas correções e ajustes;
- proteção do código do projeto, pois é mantido salvo todas as versões do seu código.
Isso auxilia no caso de uma nova funcionalidade apresentar erros, possibilitando usar o histórico para reverter o código para uma versão anterior, na qual os erros não existem.

## O que é Git

É uma das ferramentas utilizada para versionamento. Um sistema de controle de versão criado por [Linus Torvards](https://pt.wikipedia.org/wiki/Linus_Torvalds), também criador do sistema Linux, e lançado em 2005. Foi uma solução criada para que o processo fosse mais ágil, eficiente, simples e pudesse ser algo ramificado a fim de facilitar a divisão de projetos grandes, que antes a prerrogativa de lidar com projetos era através de arquivos compactados, ou seja, cada alteração era dividido entre a equipe por meio de arquivos em formato ZIP.
A premissa é que, dentro de um projeto, seja possível criar atualizações em um código base e ter cada mudança documentada, permitindo fácil acesso e flexibilidade.
E um de seus diferenciais é que, além de que cada diretório (chamado de repositório) possuir um histórico completo das alterações realizadas, ele é capaz de sincronizar um repositório local a um remoto, possibilitando que também seja acessado em outro computador e na nuvem (internet).

> **Repositório**: armazena pacotes com softwares, códigos, documentos, imagens de modo versionado e que pode ser acessado a qualquer momento. 

#### Para instalar:

##### *Windows*
 Para acessar é preciso baixar neste [link](https://gitforwindows.org/) e seguir com os passos de instalação.
 Após instalado, use o programa Git Bash (terminal de Linux para Windows) para executar os comandos do Git.


##### *Mac*
 Em alguns computadores Mac já está instalado o Git, para verificar digite o comando:
```
git --version
```

Se não aparecer a versão, significa que é necessário instalar através deste [link](https://sourceforge.net/projects/git-osx-installer/files/) e como citado acima, seguir o passo a passo. Para usar, não é preciso do Git Bash, o terminal do Mac já tem as caracteríticas de um terminal Linux.


##### *Linux*
Para instalar siga os comandos abaixo de acordo com a sua distribuição no seu terminal. 
Em distribuições Ubuntu e Debian:
```
apt-get install git
```
Em distribuições Fedora, CentOS:
```
dnf install git 
```

### Começando com Git

Esta parte será um guia de configuração inicial do Git até realizar seu primeiro commit. Veja os comandos abaixo:

Se você estiver iniciando um repositório ou um projeto e quer que o Git comece a gerenciar as alterações, é necessário usar o comando abaixo. Esse comando vai inicializar um repositório na sua máquina para aqueles arquivos dentro do diretório ou projeto.

```
git init
```

Se é a primeira vez que vai usar o Git, é preciso realizar a configuração de suas credenciais (nome e email):

```
git config --global user.name "Seu Nome"
git config --global user.email "seu_email@gmail.com"
```

Estes comandos são considerados como globais, ou seja, eles afetam todos os repositórios que não tenham uma configuração específica e, estas mesmas credenciais são usadas na assinatura de commits. Se estiver usando um computador que não seja seu, o ideal é não usar este comando como global (só retirar a palavra 'global').

No caso de trabalhar em um projeto já existente, e precisar acessá-lo, o comando a ser usado é o **git clone** junto com o endereço do repositório.

Exemplo:

```
git clone https://github.com/mastertech/site-mastertech.git
```
Será solicitado o login e senha do seu Github, e logo após será criado uma pasta com uma cópia deste código na sua máquina. 

```
git status
```
Se quiser verificar quais arquivos estão sendo modificados, basta digitar o comando **git status** que listará todos estes arquivos.
Se não tiver nenhuma alteração, a mensagem padrão que aparecerá é esta:

```
On branch master
Your branch is up to date with 'origin/master'.
nothing to commit, working tree clean
```
Se tiver algum arquivo modificado, aparecerá listado os nomes dos arquivos em vermelho, e ele será considerado como *Unstaged*, ou seja, modificações não mapeadas, e que no caso podem ser perdidas.
Uma boa prática é sempre manter atualizado tanto a versão local da sua máquina quanto a versão remota que encontra-se no Github.
Para isso, é preciso adicionar estes arquivos com [git add](https://git-scm.com/docs/git-add/pt_BR) para que seu projeto sempre esteja atualizado. O primeiro passo é digitar:
```
git add *nome do arquivo*
```
Se quiser adicionar todos os arquivos listados:
```
git add .
```
Com isso, estes arquivos serão adicionados como *Staged* para incluir com os demais arquivos. Este estado de *Staged* significa que itens foram adicionados mas o git permite a edição.
```
git add index.html
git add menu.html
```
Após este comando, 2 arquivos serão adicionados,aparecerão em verde, e se for necessário mudar algo no arquivo index.html, basta realizar a alteração e dar o mesmo comando de git add, que o arquivo já será atualizado, sem criar uma versão duplicada.

Para continuar, é necessário registrar estas alterações, semelhante a uma etiqueta colocada para enviar uma encomenda para o correio. Esta denominação é feita através do comando abaixo junto com uma mensagem que explica o que foi feito:
```
git commit -m "sua mensagem"
```
Há um limite de 72 caracteres para a mensagem do commit. O ideal é cada mudança, adicionar e fazer um commit para a mesma, assim fica mais claro o que foi feito e em qual parte do código teve alteração.
Neste momento, os arquivos vão de *Staged* para *Committed*, onde estas alterações serão gravadas em seu repositório local e estão prontas para subir para um repositório remoto.

![imagem demonstrando como funciona o processo entre o git add e git commit](https://miro.medium.com/max/1372/0*IAKT0NlYhgkieeml.png)

Para finalizar este processo, só utilizar o comando abaixo para incluir estas alterações para a versão remota:
```
git push origin *nome da branch*
```
Esse comando irá solicitar seu login e senha do Github. Ao entrar com eles,o seu commit será enviado ao seu repositório e, uma mensagem semelhante deve aparecer:

```
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (5/5), 449 bytes | 224.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/mastertech/mastertech
c12334f..65ebf90  master -> master
```
Um commit, além da mensagem que é escrita, possui os arquivos alterados, metadados, como autor, data, identificador do commit (hash) e etc...
Se você quiser verificar todos os commits que já foram feitos, como uma linha do tempo, só digitar:
```
git log
```

#### Guia rápido de comandos

A lista abaixo consta os comandos mais comuns usados no dia a dia do desenvolvimento. Para saber mais, acesse este [link](https://comandosgit.github.io/).


Comando  | Função
-------- | ---
git init | Inicializa o repositório
git clone | Clona um repositório já existente
git add   | Adiciona os arquivos 
git commit |  Para gravar as alterações junto com uma mensagem
git push   | Envia os arquivos e a mensagem criada para um repositório remoto
git pull   | Atualiza seu repositório local com base no remoto
git diff   | Mostra no terminal o seu código e o que foi atualizado
git log   | Aparece uma lista do histórico de commits/alterações do projeto
git status | Checar os status dos arquivos que foram modificados no seu repositório local

## O que é Github 

[GitHub](https://github.com/) é um sistema de hospedagem para versionamento de projetos e de códigos para desenvolvedores. É possível trabalhar em projetos colaborativos com desenvolvedores de todo o mundo, e ter todas as versões do seu código disponíveis online. 
Há outras plataformas semelhantes como o [GitLab](gitlab.com) e o [Bitbucket](bitbucket.org), sendo que a diferença entre eles é a quantidade de repositórios privados, funcionalidades extras e o custo. Porém, independente de qual for a escolha, com um plano gratuito é possível ter a opção de armazenar um repositório.

O Github como ferramenta nos auxilia para monitorar todas as alterações, do local que for, e ainda é possível dividir em etapas um mesmo projeto, e separar tarefas entre uma equipe. Essas linhas de desenvolvimento são chamadas de branches (ramos, em português). A criação de mais de uma branch permite uma separação das alterações necessárias e de entregas sobre um mesmo projeto.

#### Conceito de Branch

Todo repositório possui uma branch padrão: a master. Nela que criamos o primeiro commit e o enviamos para o Github. Ela detém a versão base do código, e a partir dela podemos criar uma nova branch para cada funcionalidade/etapa nova, como no exemplo abaixo, que a chamamos de feature. 

![Imagem da branch master com a criação de uma branch derivada da master chamada feature](https://dkrn4sk0rn31v.cloudfront.net/2019/02/20143045/exemplo-3.png)

Após criar uma nova branch para uma etapa específica do trabalho, como um formulário de cadastro, tudo que for alterado estará nesta nova branch.  Quando terminado, o passo seguinte é abrir um *Pull Request*, um pedido para incluir o que consta nesta branch nova para outra, como a branch feature com a master. 

Para saber em qual branch você está trabalhando, digite **git branch**. 

Se quiser criar uma nova branch, só digitar:

```
git checkout -b *nome da nova branch*
```
Para se movimentar entre as branches do seu projeto, como por exemplo, mudar para a master:

```
git checkout master
```
Avaliar a quantidade de branches necessárias depende muito de como foi dividido o projeto. É possível trabalhar paralelamente com mais de uma branch, e ter para cada uma seu responsável e a etapa de projeto, por exemplo. 

Para verificar se há alguma atualização e incorporar as mudanças de um repositório remoto para a branch local, digite o comando **git pull**. 

```
git pull origin *nome da branch*
```




