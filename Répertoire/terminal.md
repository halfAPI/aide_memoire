# Les commandes utilisées dans un terminal (*pour Windows*)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

Voici une liste non exhaustive des commandes que l'on utilise dans un terminal ou dans git bash. 

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
C://Users/Documents
$ ls
.exercice/  .img/
```

- `cat` : la commande cat permet d'afficher le contenu d'un fichier
```
~
C://Users/Documents
$ ls
.exercice/  .img/
```

- `touch` : cette commande permet de créer un nouveau fichier dans un dossier
```
C://Users/Documents
$ ls
.exercice/  .img/
```

- `mkdir`(**make directory**) : permet la création d'un nouveau dossier
```

```

- `mv` : permet le déplacement d'un fichier ou d'un dossier
```
$ mv ~/Downloads/MyFile.txt ~/Documents/Work/MyFile.txt
```

- `rm`: permet la suppression de fichier. **ATTENTION**, la commande `rm -rf` supprime **TOUT** les fichiers présents dans le dossier dans lequel on se trouve. La commande ne demande pas de confirmation, à utiliser avec précaution. 
```
~
C://Users/Documents
$ ls
.exercice/  .img/
```

- `rmdir`: permet la suppression de dossiers.


- `chmod`: commande permettant de configurer l'accès aux fichiers et aux dossiers


- `chown`: permet de changer le propriétaire d'un fichier ou dossier


- `chgrp` : permet de change le groupe d'utilisateur d'un fichier ou d'un document


- `sudo` : **COMMANDE LINUX**, elle permet de donner des droits à un autre utilisateur


[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)
