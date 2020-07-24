# Relação dos comandos que foram utilizados atualmente em data 24-07-2020.

## Verificar Conta do GitHub
		$ git config user.name
		$ git config user.email

## Iniciando um Repositório
		$ git init
		
## Apagando um Repositório
		$ rm -rf .git
		
## Listando Arquivos Modificados
		$ git status
		
## Arquivos não Monitorados
		$ git checkout .
		
## Apagar Novos Arquivos que Ainda não foram Adicionados ao Stage
		$ git clean -df
		
## Removendo arquivos do Stage
		$ git reset
		
## Desfazendo o Último Commit
		$ git revert HEAD
		
## Renomear Commit
		$ git commit --amend
		
## Branches - Listando Branches
		$ git branch
		$ git branch -a

## Branches - Indo para outra branch
		$ git checkout minha-branch
		* Se você adicionar -b, uma nova branch será criada.
		$ git checkout -b minha-nova-branch

## Branches - Excluindo branches
		$ git branch -d nome-da-branch
		$ git branch -D nome-da-branch
		
## Branches - Renomeando branches
		$ git branch -m novo-nome-da-branch
		$ git branch -m nome-atual novo-nome
		
## Branches - Branch Órfã
		$ git checkout --orphan minha-branch-orfa

## Visualizando o Histórico de Commits
		$ git log
		
## Visualizando - Histórico de um ou mais arquivos
		$ git log -p meus-arquivos

## Visualizando - Histórico de um autor
		$ git log --autor=nome-autor

## Visualizando - Histórico por Data
		$ git log --after="MMM DD YYYY"
		$ git log --before="MMM DD YYYY"

## Visualizando - Histórico Baseado em uma Mensagem
		$ git log --grep produtos
		
		// procurar por "produtos" OU "usuarios"
		$ git log --grep produtos --grep usuarios

		// procurar por "produtos" E "usuarios"
		$ git log --grep produtos --and --grep usuarios
		
## Exibir branches em um modo mais legível
		git log --all --decorate --oneline --graph
		
		//Para decorar tudo o que devemos escrever depois de log, lembre-se de A DOG
		– —all
		– —decorate
		– —oneline
		– —graph
		
## Atalhos Personalizados - Criando atalhos personalizados
		//deixar o comando disponível apenas no repositório atual
		git config alias.dog "log --all --decorate --oneline --graph"
		//deixar o comando global em sua máquina, ficando disponível para qualquer repositório
		git config --global alias.dog "log --all --decorate --oneline --graph"
		
		//Para remover os atalhos basta executar:
		//atalhos locais
		git config --unset alias.dog
		//atalhos globais
		git config --global --unset alias.dog
		
## Atalhos Personalizados - Listando atalhos personalizados
		$ git config -l | grep ^alias\. | cut -c 7- | sort
		$ git config alias.alias "! git config -l | grep ^alias\. | cut -c 7- | sort"

## Trabalhando em mais de uma coisa sem fazer commit
### Salvando modificações em um Stash
		$ git stash
		$ git stash push -m meu-novo-stash
### Listando Stashes
		//Simplesmente execute o comando stash
		$ git stash
		//Você ainda pode colocar um nome nesse stash:
		$ git stash push -m meu-novo-stash
### Recuperando modificações
		$ git stash apply
		$ git stash apply stash@{2}
### Removendo Stashes
		$ git stash drop stash@{5}

## Juntando alguns pedaços do trabalho
		$ git cherry-pick id-do-commit
