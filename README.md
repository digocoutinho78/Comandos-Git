
Lista de Comandos Git
===================================================================

*Uma lista dos meus comandos mais utilizados no Git. Fique à vontade para fazer recomendações.* 
[@digocoutinho](https://instagram.com/digocoutinho) / [digocoutinho78](https://github.com/digocoutinho78)

### Básicos

| Comando | Descrição |
| ------- | --------- |
| **CONFIG INICIAL:** | --------- |
| `git config --global user.name "SeuNome"` | **Configura o usuário** |
| `git config --global user.email "seunome@email.com"` | **Configura o email** |
| `git branch -m master main` | **Muda o nome da branch inicial pra main** |
| **STATUS:** | --------- |
| `git status` | **Checa o status** |
| **ADICIONAR:** |  |
| `git add [nome-arquivo.txt]` | **Adiciona um arquivo para área de stage** |
| `git add -A` | Adiciona todos os arquivos novos ou modificados para a área de stage |
| **COMMIT:** |  |
| `git commit -m "[Mensagem de Commit]"` | **Comita as alterações** |
| **REMOVER:** |  |
| `git rm -r [nome-arquivo.txt]` | Remove um arquivo (ou pasta) |

===================================================================

### Criação de Projeto

| Comando | Descrição |
| ------- | --------- |
| `git init` | Inicializa um repositório Git **local** |
| `git clone ssh://git@github.com/[usuario]/[nome-repositorio].git` | Cria uma **cópia local de um repositório remoto** |

===================================================================

### Stash

O git stash permite que você armazene temporariamente suas modificações locais que ainda não foram commitadas, para que você possa voltar a um estado limpo no seu projeto. Imagine a seguinte situação: você está trabalhando em uma nova funcionalidade, mas precisa interromper para corrigir um bug urgente. Com o git stash, você pode guardar suas alterações e voltar a elas mais tarde sem perder nada e o melhor: sem precisar criar um commit para isso.

📚 Como usar o git stash?
- Salvar suas alterações: Use **git stash save "Descrição opcional"** para salvar suas mudanças com uma descrição.
- Verificar o que está stashed: Execute **git stash list** para ver todas as alterações stashed.
- Retornar às suas alterações: Use **git stash apply** para reaplicar as últimas alterações ou **git stash pop** para reaplicar e então remover do stash.

💡 Uso avançado do comando:
- Stash específico: Use git stash apply stash@{n} para aplicar um stash específico. Conforme você for fazendo uso do git stash, as stashes vão ir sendo numeradas... 1, 2, 3 e assim por diante, esse comando permite que você aplique um stash específico, dentre a listagem, passando o número do stash que você quer aplicar.
- Criar branches a partir de um stash: Utilize **git stash branch [nome-do-branch]** para criar um novo branch com suas alterações "stasheadas".



### Branch e Merge

| Comando | Descrição |
| ------- | --------- |
| **BRANCH:** | --------- |
| `git branch` | **Lista as branches** (o asterisco denota a branch atual) |
| `git branch -a` | Lista todas as branches (local e remoto) |
| `git branch [nome da branch]` | Cria uma nova branch |
| `git branch -d [nome da branch]` | Deleta uma branch |
| `git branch -v ` | mostra o ultimo commit de cada branch |
| `git push origin --delete [nome da branch]` | Deleta uma branch remota |
| `git checkout -b [nome da branch]` | Cria uma nova branch e muda para ela |
| `git checkout -b [nome da branch] origin/[nome da branch]` | **Clona uma branch remota** e muda para ela |
| `git checkout [nome da branch]` | **Seleciona uma branch** |
| `git checkout -` | Muda para a última branch |
| `git checkout -- [nome-arquivo.txt]` | Descarta modificações de um arquivo |
|`git config init.defaultBranch` | Mostra a branch configurada como padrão |
| **MERGE:** | --------- |
| `git merge [nome da branch]` | Faz um merge de uma branch na branch atual |
| `git merge [source branch] [branch alvo]` | Faz um merge de uma branch em outra branch |
| **STASH:** | --------- |
| `git stash` | Tirar o estado sujo do seu diretório de trabalho |
| `git stash clear` | Remove todas as entradas 'stash' |

===================================================================

### Compartilhamento e Atualização de Projeto

| Comando | Descrição |
| ------- | --------- |
| `git push origin [nome da branch]` | **Enviar uma branch** para seu repositório remoto |
| `git push -u origin [nome da branch]` | **Envia as alterações da branch informada para um repositório remoto** (e selecionar a branch) |
| `git push` | **Envia as alterações para o repositório remoto (branch atual)** |
| `git push origin --delete [nome da branch]` | Deletar uma branch remota |
| `git pull` | **Atualiza o repositório local** para o último commit |
| `git pull origin [nome da branch]` | **Recebe alterações do repositório remoto** |
| `git fetch origin main` | baixa as alterações na branch main do repositorio remoto. |
| `git remote add origin ssh://git@github.com/[usuario]/[nome-repositorio].git` | Adicionar um repositório remoto |
| `git remote set-url origin ssh://git@github.com/[usuario]/[nome-repositorio].git` | Seta um repositório da origin branch para o SSH |

===================================================================

### Desfazendo Alterações

| Comando | Descrição |
| ------- | --------- |
| `git reset --hard HEAD` | Desfaz todas as alterações locais e redefine o branch para o último commit local |
| `git reset exemplo.txt` | Remove as alterações no arquivo especificado do índice (staging area), mantendo as alterações no diretório de trabalho |
| `git checkout -- exemplo.txt` | Desfaz as alterações no arquivo, revertendo para o estado no último commit |
| `git revert commitExemplo` | Cria um novo commit que desfaz as alterações introduzidas por um commit especificado |

===================================================================

### Inspeção & Comparação

| Comando | Descrição |
| ------- | --------- |
| `git log` | Ver modificações |
| `git log --summary` | **Ver modificações** (detalhadas) |
| `git diff [branch original] [branch alvo]` | Visualizar alterações antes de mesclar |


### Erros conhecidos:

Se você receber o seguinte erro:

`To https://github.com/...`

 `! [rejected]    main -> main (non-fast-forward)`

`error: failed to push some refs to 'https://github.com...'`

`hint: Updates were rejected because the tip of your current branch is behind`   <==

`hint: its remote counterpart. Integrate the remote changes (e.g.`

`hint: 'git pull ...') before pushing again.`

`hint: See the 'Note about fast-forwards' in 'git push --help' for details.`


Pode significar que o repositório remoto avançou além do seu repositório local. Para resolver sincronize seu repositório local com o repositório remoto antes do push.
Utilize o seguinte comando:

`git pull --allow-unrelated-histories`

depois é só realizar o push.

baseado no arquivo de joshnh 09/23.
