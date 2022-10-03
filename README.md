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

- `git log` :  voir l'historique des commits avec toutes les infos.
- `git log --oneline` : voir les commits , les infos de chaque commit tiennent sur une ligne.
- `git log --graph` : voir un graph avec tous les commits.
- `git log --graph --oneline` : voir un graph avec les infos de chaque commit sur une seule ligne.
- `git log --pretty=oneline` : voir le hash et le nom du commit sur une seule ligne.

## Récupère la dernier version du fichier désigné et la colle à la place de la version actuelle
 
- `git restore une_incroyable_histoire.md`

## Les tags

*Un tag est une branche qui ne change pas, il ne possède pas d'historique des commits*

- `git tag` : lister les étiquettes existantes.
- `git tag <tagname>` : créer une étiquette légère ( = sans aucune information à conserver, message ou autre)
- `git tag -a <tagname> -m '<message>'` : créer une étiquette annotée.
- `git show <tagname>` :  voir les données de l'étiquette.
- `git push origin [nom-du-tag]` : pousse le tag sur la branche distante.


## Interagir avec le dépôt distant
 
- `git remote` : répertorie les connexions distantes avec d'autres dépôts. 
- `git remote -v` : répertorie les connexions distantes avec d'autres dépôts et inclut l'URL de chaque connexion.
 
- `git checkout origin/<nomDeLaBranche>`  : détache le HEAD sur la branche distante. La branche sera mise à jour après un `git commit`.
- `git fetch` : télécharge les commits que le dépôt distant possède mais qui ne sont pas dans le nôtre, puis met à jour nos branches distantes. ###Ne change pas l'état local ##. 
Il peut être suivi de `git merge origin/<nomDeLaBrancheDistante>` pour mettre à jour le dépôt local.
- `git remote show origin` : répertorie les connexions distantes avec d'autres dépôts et en affiche les détails.

