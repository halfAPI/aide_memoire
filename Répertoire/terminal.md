# Les commandes utilisées dans un terminal (*pour Windows*)

Une cheatsheet sur le terminale est disponible [ICI](https://github.com/CalcagnoLoic/aide_memoire/blob/main/Fichiers%20utiles/cmd.pdf)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

Voici une liste non exhaustive des commandes que l'on utilise dans un terminal ou dans git bash. 

- `exit` : cette commande permet de fermer le terminal

- `--help` : permet d'obtenir de l'aide sur une commande. Par exemple, l'aide de la commande `ls`:
```
$ ls --help
```

- `ls`: permet de lister tout les fichiers présents dans un dossier. Par exemple, voir le contenu du dossier documents :
```
~ C://Users/Documents
$ ls
.exercice/  .img/   texte.txt
```

- `cp`: cette commande permet de faire une copie d'un fichier
```
~ C://Users/Documents
$ ls
.exercice/  .img/   texte.txt

~ C://Users/Documents
$ cp texte.txt  test.txt

~ C://Users/Documents
$ ls
.exercice/  .img/   texte.txt   test.txt
```

- `pwd`: permet d'afficher le chemin d'accès d'un fichier
```
~ exercice.txt
$ pwd
users/documents/exercice/exercice.txt
```

- `cd` : permet de se déplacer d'un dossier à l'autre. A noter que la commande `cd ..` permet de revenir d'un pas en arrière
```
~ 
$ cd users

~ C://users
$ cd documents

~ C://users/documents
$ cd ..

~ C://users
```

- `cat` : la commande cat permet d'afficher le contenu d'un fichier
```
~
$ cat README.md
Voici l'exemple de l'utilisation de la comande
```

- `touch` : cette commande permet de créer un nouveau fichier dans un dossier
```
~ C://Users/Documents
$ ls
.exercice/  .img/

~ C://Users/Documents
$ touch fichier.ppt

~ C://Users/Documents
$ ls
.exercice/   .img/   fichier.ppt
```

- `mkdir`(**make directory**) : permet la création d'un nouveau dossier
```
~ C://Users/Documents
$ ls
.exercice/   .img/

~ C://Users/Documents
$ mkdir newDossier

~ C://Users/Documents
$ ls
.exercice/   .img/   .newDossier/
```

- `mv` : permet le déplacement d'un fichier ou d'un dossier
```
$ mv ~/Downloads/MyFile.txt ~/Documents/Work/MyFile.txt
```

- `rm`: permet la suppression de fichier. **ATTENTION**, la commande `rm -rf` supprime **TOUT** les fichiers présents dans le dossier dans lequel on se trouve. La commande ne demande pas de confirmation, à utiliser avec précaution. 
```
~ C://Users/Documents
$ ls
.exercice   .img/   .newDossier/

~ C://Users/Documents
$ rm newDossier

~ C://Users/Documents
$ ls 
.exercice/   .img/
```

- `rmdir`: permet la suppression de dossiers.


- `chmod`: commande permettant de configurer l'accès aux fichiers et aux dossiers


- `chown`: permet de changer le propriétaire d'un fichier ou dossier


- `chgrp` : permet de change le groupe d'utilisateur d'un fichier ou d'un document


- `sudo` : **COMMANDE LINUX**, elle permet de donner des droits à un autre utilisateur

Une cheatsheet sur le terminale est disponible [ICI](https://github.com/CalcagnoLoic/aide_memoire/blob/main/Fichiers%20utiles/cmd.pdf)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)
