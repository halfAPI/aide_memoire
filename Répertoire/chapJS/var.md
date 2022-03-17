# Les variables et types de valeurs en Javascript

Voici les différents points abordés dans cette section : 

* Présentation des variables JS

* Les types de données JS

* Présentation des opérateurs arithmétiques et d'affectation 

* La concaténation 

* Les constantes 

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Présentation des variables JS

Une variable correspond à un conteneur dans lequel on peut placer différentes choses. 

Quand on veut déclarer une variable, on utilisera le mot-clé `let` suivi du nom de la variable. 

Pour initialiser une variable, on utilise l'opérateur `=`. **Attention**, celui ne signifie pas une égalité mais bien une affectation! 

# Les types de données JS

En Javascript, il existe 7 types de variables : 

## 1. *Les string / Chaines de caractères*

Toutes les valeurs `string` sont déclarées via des apostrophes. **ATTENTION**, un chiffre déclarer avec des apostrophes correspondra à un `string` et non un nombre!

```
let prenom = "Je m'appelle Loïc";
let age = "29";
```

## 2. *Les number / Nombres*

Contrairement aux autres langages comme R ou Python où il existe différents types en fonction que le nombre soit entier, décimal etc (`integer`, `double` et `float`), en javascript il n'en existe qu'un seul => `number`

```
let x = 10;
let y = -1;
let z = 3.14;
```

## 3. *Les booléens*

Un booléen est une valeur binaire qui correspondra à `true` et `false` en informatique. 

## 4. *Les Null*

Ce type correspond à l'absence de valeur ou du moins à l'absence de valeur connue. Pour qu'une variable contienne `null`, il faut lui stocker cette valeur qui représente donc l'absence de valeur! 

## 5. *Undefined*

La valeur `undefined` correspond à une variable "non définie", c'est-à-dire une variable à laquelle on n'a pas affecté de valeur. 

## 6. *Symbol et Object*

Les objets sont des structures complexes qui peuvent stocker plusieurs valeurs en même temps. Les tableaux en JS sont des objets et sont surtout des valeurs de type `Object`. 

Le type de donnée `Symbol` est lié à `Object`. 

# Présentation des opérateurs arithmétiques et d'affectation 

Un opérateur est un symbole qui permet d'effectuer des actions sur les variables et leurs valeurs. Il existe tout un tas d'opérateur : 

- Les opérateurs arithmétiques ;

- Les opérateurs d'affectation/d'assignation ; 

- Les opérateurs de comparaison ; 

- Les opéreurs d'incrémentation et de décrémentation ;

- Les opérateurs logiques ; 

- L'opérateur de concaténation ; 

- L'opérateur ternaire ; 

- L'opérateur virgule ; 

## 1. *Les opérateurs arithmétiques* 

Ce sont des opérateurs permettant d'effectuer des opérations mathématiques : 

|Opérateur|Nom de l'opération associée|
|---------|---------------------------|
|   `+`   | Addition                  |
|   `-`   | Soustraction              |
|   `*`   | Multiplication            |
|   `/`   | Division                  |
|   `%`   | Modulo (reste d'une division euclidienne)                          |
|   `**`  | Exponentielle             |

Attention, les propriétés mathématiques s'appliquent bien évidemment! Règles des parenthèses bonjour =D

## 2. *Les opérateurs d'affectation*

Ce sont des opérateurs permettant d'affecter des valeurs à une variable. Il y a bien évidemment l'opérateur `=` mais on peut également avoir des opérateurs combinés. 

|Opérateur|Définition                 |
|---------|---------------------------|
|  `+=`   | Additionne puis affecte le résultat|
|  `-=`   | Soustrait puis affecte le résultat|
|  `*=`   | Multiplie puis affecte le résultat|
|  `/=`   | Divise puis affecte le résultat|
|  `%=`   | Calcule le modulo puis affecte le résultat|

# La concaténation 

La concaténation correspond au fait de mettre bout à bout des chaines de caractères pour en former une nouvelle : 

```
let x = "Le javascript ";
let y = "c'est trop cool!";

console.log(x + y); //Le javascript c'est trop cool!
```

ou bien encore : 

```
let x = " le javascript ";
let y = "c'est trop cool!";

alert("Hey toi qui lit cet aide-mémoire," + x + y); //Hey toi qui lit cet aide-mémoire, le javascript c'est trop cool!
```

## Les littéraux de gabarits

Pour faire une chaine de caractère, on peut utiliser `"` et `'`.

Cependant, il existe une troisième manière, le `. La grande différence entre l’utilisation d’accents graves ou l’utilisation d’apostrophes ou de guillemets est que toute expression placée entre les accents graves va être interprétée en JavaScript. Pour le dire simplement : tout ce qui renvoie une valeur va être remplacé par sa valeur.

On va pouvoir insérer des valeurs en utilisant cette manière. Mais pour cela, il faut utiliser une syntaxe particulière : `$ { }`. 

```
let x = 5; 
let y = 10;

alert(`x contient ${x}
       y contient ${y}
       Leur somme vaut ${x+y}`);

// x contient 5
   y contient 10
   Leur somme vaut 15

```

# Les constantes

Une constante est similaire à une variable au sens où c’est également un conteneur pour une valeur. Cependant, à la différence des variables, on ne va pas pouvoir modifier la valeur d’une constante.

En effet, une fois qu’une valeur est attribuée à une constante, celle-ci est attribuée de façon définitive et ne va pas pouvoir être modifiée.. d'où le nom de constante!

La déclaration se fait via le mot clé `const` 

```
const prenom = "Loïc";
const age = 29;
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)