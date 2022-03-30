# Les fonctions en javascript 

Voici les points abordés dans cette section :

* Présentation des fonctions 

* Portée des variables et valeurs de retour en JS

* Fonctions anonymes

* Fonctions auto-invoquées

* Récursitivé

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Présentation des fonctions 

Les fonctions sont des blocs de codes nommés et réutilisables et dont le but est d'effectuer une tâche précise. 

Il existe 2 grands types de fonctions en JS : les fonctions natives et les fonctions personnalisées. 

Pour exécuter le code d'une fonction, il faut **l'appeler**. Il suffit d'écrire le nom de la fonction avec des **parenthèses**!

On crée une fonction personnalisée grâce au mot clé `function`.

```js
function exemple() {
    //bloc de code
}
```

Si une fonction a besoin de valeurs pour fonctionner, alors on définit ces paramètres lors de la définition de la fonction.

On peut également écrire des fonctions fléchées. Plus d'informations dans la section ["Notions avancées"](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/chapJS/avancee.md)

# Portée des variables et valeurs de retour en JS

La portée d'une variable désigne l'espace du script dans laquelle elle va être accessible. En effet, toutes nos variables ne sont pas automatiquement disponibles à n'importe quel endroit dans un script et on ne va donc pas toujours pouvoir les utiliser. 

En JS, il existe 2 espaces de portées différentes : 

- L'espace global : c'est l'entièreté d'un script à l'exception de l'intérieur des fonctions

- L'espace local : c'est l'espace dans une fonction

Il faut donc bien se rendre compte qu'une variable définie dans l'espace global est accessible dans le script même depuis une fonction! **PAR CONTRE**, une variable définie dans l'espace local n'est accessible **que** dans le corps de la fonction et non dans le script! 

Un autre concept essentiel à comprendre est celui de la valeur de retour! Il s'agit d'une valeur renvoyée par une fonction une fois que celle-ci a terminé son exécution. Une valeur de retour est une valeur unique qui va être renvoyée par la fonction après son exécution et qu’on va pouvoir récupérer pour la manipuler dans notre script. On utilise pour cela l'instruction `return`.

**Attention cependant** : l’instruction `return` met fin à l’exécution d’une fonction, ce qui signifie que toutes les autres opérations qui suivent une instruction `return` dans une fonction seront ignorées

# Fonctions anonymes

Ce sont des fonctions qui ne possèdent pas de nom. Et lorsque l'on crée une fonction anonyme, nous ne sommes pas obligés de lui donner un nom. 

On utilisera ce genre de fonction lorsque l'on n'a pas besoin d'appeler notre fonction par son nom. 

```js
function(){
    alert("Alerte exécutée par une fonction anonyme");
}

OU

let alerte = function(){
    alert("Alerte exécutée par une fonction anonyme");
}
alerte();
```

# Fonctions auto-invoquées

Il s'agit d'une façon d'exécuter d'une fonction anonyme (ou d'une fonction nommée bien sûr). 

Pour créer une fonction auto-invoquée à partir d’une fonction, il va tout simplement falloir rajouter un couple de parenthèses autour de la fonction et un second après le code de la fonction.

```js
//Fonction anonyme
(function(){alert("Coucou!")})

//Fonction nommée
(function bonjour(){alert("bonjour!")})
```

# Récursitivé

Une fonction récursive est une fonction qui va s'appeler elle-même au sein de son code. 

```js
function decompte(t) {
    if (t>0) {
        return decompte(t-1);
    } else {
        return t;
    }
}
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)