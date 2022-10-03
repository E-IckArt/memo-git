# Commandes GIT


## Faire un commit
- `git commit -m` : commiter des changements

## Les branches

- `git branch` : voir les branches locales
- `git branch <nomDeLaBranche>` : créer une nouvelle branche
- `git branch -d <nomDeLaBranche> ` : supprimer une branche locale
- `git branch -vv `: voir les branches configurées 

- `git checkout <nomDeLaBranche>` : changer de branche
- `git checkout -b <nomDeLaBranche> `: créer une nouvelle branche et passer dessus  

- `git merge <nomDeLaBranche> `: merger une branche dans la branche courante
- `git rebase <nomDeLaBranche sur laquelle coller la branche courante> && git rebase <nomDeLaBrancheCourante> ` : déplacer un commit 

## Se déplacer dans l'historique

- git checkout <hash du commit> : déplace le head sur un commit
- `^ `	: revenir d’un commit en arrière,  
ex: `git checkout main^`  
ou `git checkout HEAD^` pour utiliser la référence relative)  

- `^^ `	: revenir de deux commits en arrière,  
ex: `git checkout main^^`  
ou `git checkout HEAD^`
- `~<num> ` : revenir de plusieurs commits en arrière,  
ex: `git checkout main~5`  
ou `git checkout HEAD~5`  

- `git branch -f main HEAD~3` : réassigner les branches à un commit avec l’option -f (= force)


## Annuler des changements avec Git :

- `git reset` : annule le dernier commit sur le dépôt local.
- `git revert` : annuler des changements sur la branche courante et le dépôt distant.
- `git commit --amend` : annule le dernier commit.
- `git clean` :  annule les changements non commités. Commande complémentaire à `git reset` et `git revert`.
- 'git add' : modifier le staging index.
- `git rm --cached <file>...` : retire le fichier de la zone de staging (annule un git add).

## Voir tous les commits

- `git log`
- `git log --oneline`
- `git log --graph`
- `git log --graph --oneline`


## Récupère la dernier version du fichier désigné et la colle à la place de la version actuelle

- `git restore une_incroyable_histoire.md`
