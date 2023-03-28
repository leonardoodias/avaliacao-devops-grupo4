🔥 

# **Padrões de Projeto** 
<hr>
  - [1. Git](#1-git)
    - [1.1 Algumas regras do Git](#11-algumas-regras-do-git)
    - [1.2 Git workflow](#12-git-workflow)
    - [1.3 Escrevendo boas mensagens de commit](#13-escrevendo-boas-mensagens-de-commit)

    <a name="git"></a>

## **1. Git**

![Git](/images/branching.png)
<a name="some-git-rules"></a>

### **1.1 Algumas regras do Git**

Essas são algumas regras do Git para manter em mente:

- Trabalhe em uma feature branch.

  _Por que?:_

  > Porque desse jeito todo o código é criado isolado em uma branch específica ao invés de poluir a branch principal com trabalho em progresso. Isso vai permitir você abrir vários pull requets sem confusão. Você pode continuar com uma branch em progresso sem correr o risco de quebrar a branch principal com código instável. [Leia mais sobre...](https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow)
- Sempre comece uma nova branch a partir da `develop`

  _Por que?_

  > Desse jeito você pode garantir que o código na master vai estar sempre pronto para fazer build sem problemas e poderá ser usado a qualquer momento para fazer releases (isso pode ser exagero para alguns projetos).
- Nunca dê push direto na `develop` ou `master`. Sempre faça Pull Requests.

  _Por que?_

  > Isso permite outros membros do time saberem que você terminou uma feature. Também possibilita code review e dicussões sobre o código que está prestes a ser introduzido no code base.
- Atualize sua `develop` local e faça rebase interativo antes de subir sua feature e abrir um Pull Request.

  _Por que?_

  > Rebase vai fazer um merge do branch destino do pull request e aplicar os commits que você tem localmente no topo da história sem criar um commit de merge (assumindo que não tem conflitos). Como resultado você tem uma história limpa no seu repositório. [Leia mais sobre ...](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
- Resolva os conflitos enquanto faz o rebase e antes de abrir o Pull Request.
- Delete feature branches, local e remoto, depois de realizar o merge.

  _Por que?_

  > Vai reduzir sua lista de branches removendo branches mortas. Vai garantir que você apenas faça o merge de uma branch uma única vez. Feature branches só devem existir enquanto o código ainda está em progresso.
- Antes de fazer um Pull Request, tenha certeza que sua feature branch está fazendo build corretamente e passando em todos os testes (incluindo os padrões de estilo de código).

  _Por que?_

  > Você está prestes a colocar seu código em uma branch estável. Se sua feature branch faz algum teste falhar, a chance é alta de que você vai quebrar o build na branch destino. Você também precisa conferir o code style antes de fazer um Pull Request. Isso contribui para legibilidade e reduz a chance de algum problema de formatação is para o code base com as outras alterações.
- Faça uso desse [`.gitignore`](./.gitignore).

  _Por que:_

  > É uma lista que já contém arquivos de sistemas que não devem ser enviados para o seu repositório remoto. E também exclui pastas de configuração e os arquivos comumente usado por editores e obviamente, também, pastas de dependência.
- Proteja (Bloqueie) a `develop` e `master`.

  _Por que?_

  > Protege suas branchs que devem, em teoria, estarem prontas para irem para produção de receberem códigos e mudanças irreversíveis. Leia mais sobre... [Github](https://help.github.com/articles/about-protected-branches/), [Bitbucket](https://confluence.atlassian.com/bitbucketserver/using-branch-permissions-776639807.html) e [GitLab](https://docs.gitlab.com/ee/user/project/protected_branches.html)
<a name="git-workflow"></a>


### **1.2 Git workflow**

Devido a maioria dos motivos listados acima, nos usamos [Feature-branch-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow) com [Interactive Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing#the-golden-rule-of-rebasing) e alguns pontos do [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow) (nomeação e ter uma develop branch). Os principais passos são:

- Em um projeto novo, inicialize o git na pasta do projeto. **Para qualquer features/changes ignore esse passo**.

  ```sh
  cd <pasta do projeto>
  git init
  ```

- Checkout para uma nova branch feature/bug-fix.
  ```sh
  git checkout -b <branchname>
  ```
- Faça as alterações.

  ```sh
  git add <arquivo1> <arquivo2> ...
  git commit
  ```

  _Por que?_

  > `git add <arquivo1> <arquivo2> ...` - Você deve add apenas arquivos com mudanças pequenas e concisas.
  > `git commit` Abrirá o editor, o que permite você separar o titulo da mensagem.
  > Leia mais sobre na _seção 1.3_.
  _Dica:_

  > Você poderia usar `git add -p`, o que te daria a chance de revisar todas as mudanças introduzidas, uma a uma, e decidir se inclui ou não naquele commit.
- Sincronize com as ultimas alterações no repositório remoto.
  ```sh
  git checkout develop
  git pull
  ```
  _Por que?_
  > Isso vai permitir que você lide com os conflitos na sua máquina local enquanto você faz o rebase (posteriormente) ao invés de criar um pull request com conflitos.
- Atualize sua feature branch com as ultimas alterações da develop usando rebase iterativo.
  ```sh
  git checkout <branchname>
  git rebase -i --autosquash develop
  ```

  _Por que?_
  > Você pode usar --autosquash para comprimir todos os seus commits em um único commit. Ninguém quer commits de desenvolvimento de uma feature na develop. [Leia mais sobre...](https://robots.thoughtbot.com/autosquashing-git-commits)
- Se você não tem conflitos, pule esse passo. Se você tem conflitos, [resolva-os](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/) e continue onrebase.
  ```sh
  git add <file1> <file2> ...
  git rebase --continue
  ```

- Push sua branch. Rebase vai alterar a história, então você precisa usar `-f` para forçar a mudança no branch remoto. Se tem mais alguém trabalhando na mesma branch, use o comando `--force-with-lease`.
  ```sh
  git push -f
  ```

  _Por que?_
  > Quando você faz rebase, você está mudando a história na sua feature branch. Então o git ira rejeitar seu `git push`. Para passar por isso você precisa usar -f ou --force flag. [Leia mais sobre...](https://developer.atlassian.com/blog/2015/04/force-with-lease/)
- Abra um Pull Request.
- Pull request deve ser aceito, mergiado e fechado por quem estiver revisando.
- Delete seu branch local se tiver terminado.

  ```sh
  git branch -d <nome do branch>
  ```

  Para remover todos os branchs que não existem no repositório remoto:

  ```sh
  git fetch -p && for branch in `git branch -vv --no-color | grep ': gone]' | awk '{print $1}'`; do git branch -D $branch; done
  ```
<a name="writing-good-commit-messages"></a>


### **1.3 Escrevendo boas mensagens de commit**

Ter um bom padrão para criar commits e se atentar a ele faz com que trabalhar com Git e colaborar com outros seja muito mais fácil. Aqui estão algumas boas práticas ([fonte](https://chris.beams.io/posts/git-commit/#seven-rules)):

- Separe o assunto e a mensagem com uma nova linha entre eles.

  _Por que?_

  > Git é inteligente o suficiente para identificar a primeira linha do seu commit como um resumo. Na verdade, se você tentar shortlog, ao invés de git log, você vai ver uma longa lista de mensagens de commits, com apenas o id e o resumo do commit.
- Máximo de 50 caracteres para o assunto e 72 para a mensagem.

  _Por que?_

  > Commits devem ser objetivos e claros, não é o momento para ser verboso. [Leia mais sobre...](https://medium.com/@preslavrachev/what-s-with-the-50-72-rule-8a906f61f09c)
- Capitalize a linha do assunto.
- Não use um ponto para finalizar a linha do assunto.
- Use [imperative mood](https://en.wikipedia.org/wiki/Imperative_mood) na linha do assunto.

  _Por que?_

  > É melhor que o commit diga o que vai acontecer no projeto depois daquele commit do que o que o que aconteceu dentro do commit em si. [Lei mais sobre...](https://news.ycombinator.com/item?id=2079612)
* Use a mensagem para explicar **o que** e **porque** ao invés de **como**.

<a name="documentation"></a>
