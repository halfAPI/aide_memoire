# Les valeurs primitives et les objets globaux en JS

Voici les différentes informations abordées dans cette section : 

* Valeurs primitives et objets prédéfinis 

* L'objet global `String` : Propriétés et méthodes

* L'objet global `Number` : Propriétés et méthodes

* L'objet global `Math` : Propriétés et méthodes

* L'objet global `Array` : Propriétés et méthodes

* L'objet global `Date` : Propriétés et méthodes

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Valeurs primitives et objets prédéfinis 

Il existe 2 catégories de types de données en JS : les valeurs primitives et les objets.

- Les valeurs primitives sotn des valeurs qui ne sont pas des objets et ne peuvent être modifiées. En effet, une fois qu'on a déclarée une valeur, elle n'est plus modifiée (sauf si elle est écrasée par une nouvelle déclaration bien sûr). 

- Un objet, tout est modifiable dans les membres de celui ci. 

```js
let exemple1 = 30 //valeur primitive

let exemple2 = new Number(30) //objet prédéfini
```

En JS, on a différents objets prédéfinis. On les appelle également 'objets globaux'.

# L'objet global `String` : Propriétés et méthodes

On retrouve deux propriétés ainsi qu'une trentaine de méthodes.

## Les propriétés 

Ce constructeur possède deux propriétés : 

- `length` : La propriété permet d'obtenir la longueur de la chaine de caractères. 

- `prototype` : Il s'agit de la propriété de base que possède tout objet.

## Les méthodes 

Rendez-vous [ici](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/string_meth.md) pour la liste de toutes les méthodes utilisables sur les `String`.


# L'objet global `Number` : Propriétés et méthodes

On retrouve une dizaine de propriétés ainsi qu'une dizaine de méthodes.

## Les propriétés 

Ce constructeur possède différentes propriétés : 

- `MIN_VALUE` et `MAX_VALUE` représentent respectivement la plus petite valeur numérique positive et la plus grand valeur numérique.

- `MIN_SAFE_INTEGER` et `MAX_SAFE_INTEGER` représentent respectivement le plus petit et le plus grand entier représentables correctement ou de façon 'sûre' en JS. 

- `NEGATIVE_INFINITY` et `POSITIVE_INFINITY` servent respectivement à représenter l'infini côté négatif et côté positif.

- `NaN` représente une valeur qui n'est pas un nombre (NaN = Not a Number).

## Les méthodes 

Rendez-vous [ici](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/nombre_meth.md) pour la liste de toutes les méthodes utilisables sur les `Number`.

# L'objet global `Math` : Propriétés et méthodes

Il faut préciser que `Math` n'est pas un constructeur. Dès lors, les propriétés et les méthodes de cet objet sont statiques et vont devoir être utilisées directement avec cet objet. 

On retrouve une dizaine de propriétés ainsi qu'une trentaine de méthodes.

## Les propriétés 

`Math` possède différentes propriétés :

- `Math.E` : correspond au nombre d'Euler (base des logs), soit 2,718

- `Math.LN2` : correspond au log2, soit 0,693

- `Math.LN10` : correspond au log10, soit 2,302

- `Math.LOG2E` : correspond au log de e en base 2, soit 1,442

- `Math.LOG10E` : correspond au log de e en base 10, soit 0,434

- `Math.PI` : correspond à pi, soit 3,14159

- `Math.SQRT1_2` : correspond à la racine carrée de 1/2, soit 0,707

- `Math.SQRT2` : correspond à la racine carrée de 2, soit 1,414


## Les méthodes 

Rendez-vous [ici](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/math_meth.md) pour la liste de toutes les méthodes utilisables sur les `Math`.

# L'objet global `Array` : Propriétés et méthodes

Les arrays correspondent aux tableaux. 

```js
/*Déclaration de tableaux*/
let arr = [1,2,3,4,5]

let arr = new Array(1,2,3,4,5)

/*Accéder à une valeur du tableau*/
arr[1] //2
```

On peut également parcourir un tableau via la boucle `for...of`. Ce type de boucle va effectuer son code jusqu'à arriver à la fin du tableau. 

```js
let prenoms = ['Loic', 'Mathilde', 'Florian', 'Camille'];
let ages = [29, 27, 29, 30];
let produits = ['Livre', 20, 'Ordinateur', 5, ['Magnets', 100]];

for(let valeur of prenoms) {
    alert(valeur)
}
//Loic Mathilde Florian Camille
```

Dans d'autre langages comme PHP, on peut avoir des tableaux associatifs. Il s'agit de tableaux auxquels on attribue une clé textuelle à chaque valeur. Malheureusement, cela n'existe pas en JS. 
Ce qui se rapproche le plus de ce type de tableau est un objet littéral. 
Dans ce cas, on utilise une boucle `for...in` qui est l'équivalent de la boucle `for...of` mais pour les objets!

```js
let loic = {
    'prenom' : 'Loic',
    'age' : 29,
    'sport' : 'tennis',
    'cours' : ['HTML', ' CSS', ' JavaScript']
};

for(let propriete in loic){
    alert(propriete)
};

/*
Loic
29
tennis
HTML, CSS, JavaScript
*/
```

On retrouve deux propriétés ainsi qu'une trentaine de méthodes.

## Les propriétés 

Ce constructeur possède deux propriétés : 

- `length` : La propriété permet d'obtenir la longueur de la chaine de caractères. 

- `prototype` : Il s'agit de la propriété de base que possède tout objet.

## Les méthodes 

Rendez-vous [ici](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/array_meth.md) pour la liste de toutes les méthodes utilisables sur les `Array`.

# L'objet global `Date` : Méthodes

Dans les méthodes pour les `Date`, on va retrouver deux types de méthodes : 

- Les méthodes `.get...` : on appelle les méthodes qui permettent d’obtenir / de récupérer quelque chose des « getters »

- Les méthodes `.set...` : on appelle les méthodes qui permettent de définir quelque chose des « setters »

Rendez-vous [ici](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/date_meth.md) pour la liste de toutes les méthodes utilisables sur les `Date`.

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)