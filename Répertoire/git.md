# Les commandes utilisées dans Git

Une cheatsheet sur git est disponible [ICI](https://github.com/CalcagnoLoic/aide_memoire/blob/main/Fichiers%20utiles/git.pdf)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

Quand on travaille avec un terminal et git, 3 commandes sont primordiales : `le commit, le push et le pull`. Voici un diagramme représentant le cheminement des données via ces 3 commandes : ![Commit, push et pull](https://qavalidation.com/wp-content/uploads/2018/07/Git-PUSH-pULL-1280x640.png)

Voici les autres commandes que l'on peut utiliser :

- `git init` : permet d'initialiser un repo depuis le terminal

- `git clone` : permet de cloner un repository venant de GitHub via la clé SSH ou HTTPS

- `git branch` : permet de créer une nouvelle branche dans le projet

- `git branch -f main HEAD` : exemple d'utilisation de la commande `branch` afin de forcer le déplacement 

- `git checkout` : cette commande permet de se positionner sur une branche

- `git merge` : cette commande permet de fusionner deux branches ensemble. **/!\ aux conflits lors de l'utilisation de merge**

- `git rebase` : cette commande ressemble à `git merge` sauf que `rebase` permet de repositionner une série de commit à un autre endroit

- `git rebase -i` : cette commande permet d'ouvrir la console interactive de `rebase`

- `git log` : permet de connaitre l'identifiant des commits qui ont été réalisés

- `^` : cette commande permet de revenir en arrière d'un commit. Par exemple, `git checkout main^`, permet de revenir à un commit en arrière dans la branche main

- `git reset` : permet d'annuler des changement en faisant un bond en arrière

- `git revert` : permet de pusher une annulation de changement

- `git cherry pick` : cette commande permet de copier des commits d'une branche à une autre

- `git commit` : commande permettant de 'commiter' les changements apportés aux fichiers/dossiers. L'itilisation de la commande telle quelle mène à une fenêtre d'édition du commit. Si on veut écrire directement le message, on utilise `git commit -m "message"`

- `git commit --amend` : permet la modification d'un commit

- `git tag` : permet d'ajouter un tag sur un commit. Par exemple, `git tag V1 C1`, ajoute le tag V1 sur le commit C1

- `git describe` cette commande permeet de décrire la différence entre le commit et le tag le plus récent

- `git fetch` : permet de récupérer les commits non présents en local et fait une mise à jour des branches. Il faut considérer `fetch` comme un téléchargement, il prend uniquement les données nécessaire au `pull`

- `git pull` : ramène les fichiers distants vers l'espace de travail local

- `git push` : envoie les fichiers locaux vers l'esapace de travail distant

Une cheatsheet sur git est disponible [ICI](https://github.com/CalcagnoLoic/aide_memoire/blob/main/Fichiers%20utiles/git.pdf)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)
