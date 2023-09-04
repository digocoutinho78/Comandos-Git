
Lista de Comandos Git
===================================================================

### Básicos

| Comando | Descrição |
| ------- | --------- |
| **CONFIG INICIAL:** | --------- |
| `git config --global user.name "SeuNome"` | **Configura o usuário** |
| `git config --global user.email "seunome@email.com"` | **Configura o email** |
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
| ------- | --------- |
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

### Inspeção & Comparação

| Comando | Descrição |
| ------- | --------- |
| `git log` | Ver modificações |
| `git log --summary` | **Ver modificações** (detalhadas) |
| `git diff [branch original] [branch alvo]` | Visualizar alterações antes de mesclar |
