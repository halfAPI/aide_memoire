# Les structures de contrôle JS

Voici les différentes notions abordées dans cette section : 

* Les conditions et opérateurs en JS

* Les conditions `if` et `if .. else`

* Les opérateurs logiques, précédence et règle d'associativité des opérateurs

* Utilisation d'opérateur ternaire (`?` et `:`) 

* L'instruction `switch`

* Les boucles `while`, `do ... while`, `for` et `for ... in`

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Les conditions et opérateurs en JS

Dans les boucles de contrôle, on va réaliser des conditions où tel ou tel bloc sera exécuté en fonction de telle ou telles valeurs. En pratique, on utilise ce qu'on appelle des opérateurs de comparaison. 

| Opérateurs | Définition |
|------------|------------|
| `==`       | Permet de tester l'égalité sur les valeurs|
| `===`      | Permet de tester l'égalité en terme de valeurs et de types|
| `!=`       | Permet de tester la différence sur les valeurs|
| `<>`       | Permet de tester la différence sur les valeurs|
| `!==`      | Permet de tester la différence en valeurs ou en types|
| `<`        | Permet de tester si une valeur est strictement inférieure à une autre|
| `>`        | Permet de tester si une valeur est strictement supérieure à une autre|
| `<=`       | Permet de tester si une valeur est inférieure ou égale à une autre|
| `>=`       | Permet de tester si une valeur est supérieure ou égale à une autre|

*Petit exercice utile à faire. Initialiser 9 variables pour tester les différents opérateurs et renvoyer le booléen correspondant à l'opération.*

Exemple : 

```js
let x = 4

let test1 = x == 4;
alert(test1) //true
```

# Les conditions `if` et `if .. else`

## La condition `if` en JS

C'est l'une des conditions les plus utilisées car c'est la plus simple et exécute un bloc de code SSI le résultat d'un test vaut `true`.

```js
let x = 9;
let y = 7; 

if (x > y) {
    alert ("x est supérieur à y")
}
```

## Inverser la valeur logique d'un test

Dans l'exemple ci-dessus, la valeur logique de la boucle if est `true`. On peut changer le comportement de la boucle en demander d'exécuter le bloc de code si l'instruction renvoie `false`. 

```js
let x = 4;
let y = 0;

if ((x == y) == false) {
    alert("x et y ne contiennent pas la même valeur");
}
```

## La condition `if...else` en JS

La boucle `if` est assez restrictive dans le sens où elle ne teste qu'une seule et unique condition! Si on veut tester une condition supplémentaire, on passe par une boucle `if...else`.

```js
let x = 5;

if(x > 2) {
    alert("x est supérieur à 2");
} else {
    alert("x est inférieur à 2"); 
}
```

## La condition `if...else if...else` en JS

Il s'agit d'une autre variante de la boucle `if` qui est encore plus complète. Elle permet de tester d'autres conditions intermédiaires. 

```js
let x = 0.5;

if(x > 1){
    alert('x contient une valeur strictement supérieure à 1');
}else if(x == 1){
    alert('x contient la valeur 1');
}else{
    alert('x contient une valeur strictement inférieure à 1');
}
```

# Les opérateurs logiques, précédence et règles d'associativité des opérateurs

## Les opérateurs logiques 

Il s'agit d'opérateur qui seront utilisés avec des valeurs booléenne et des conditions. JS supporte 3 types d'opérateurs logiques : ET, OU et NON. 

|  Opérateur  |  Symbole  |  Description |
|-------------|-----------|--------------|
|`AND` (ET)   | `&&`      | Renvoie true si toutes les conditions sont égales|
|`OR` (OU)    | `//`      | Renvoie true si au moins une des conditions soit respectées|
|`NO` (NON)   | `!`       | Inverse le résultat logique d'une condition|

## Précédence et règles d'associativité des opérateurs

Il existe un ordre de priorité au sein des différents opérateurs, c'est la précédence. 

De plus, les règles d'associativité vont également s'appliquées. L'associativité détermine l'ordre dans lequel des opérateurs de même précédence sont évalués. Et donc l'ordre dans lequel va s'effectuer la lecture des opérateurs. Une associativité par la gauche signifie qu’on va commencer réaliser les opérations en partant de la gauche et vers la droite tandis qu’une associativité par la droite signifie qu’on va commencer par la droite. 

Voici un tableau récapitulant différents opérateurs ainsi que leur précédence (la plus basse = 0 et la plus haute = 10)

| Précédence | Opérateur | Symbole | Associativité |
|------------|-----------|---------|---------------|
|0           | Groupement| `(...)` |  /            |
|1           | Incrémentation| `...++` |  /        |
|1           | Décrémentation| `...--` |  /        |
|2           | NON| `!...` |  Droite           |
|2           | Pré-incrémentation| `++...` |  Droite   |
|2           | Pré-décrémentation| `--...` |  Droite   |
|3           | Exponentiel| `...**...` |  Droite       |
|3           | Multiplication| `...*...` |  Gauche     |
|3           | Division| `.../...` |  Gauche      |
|3           | Modulo| `...%...` |  Gauche        |
|4           | Addition| `...+...` |  Gauche      |
|4           | Soustraction| `...-...` |  Gauche   |
|5           | Inférieur strict| `...<...` |  Gauche      |
|5           | Inférieur ou égal| `...<=...` |  Gauche        |
|5           | Supérieur strict| `...>...` |  Gauche        |
|5           | Supérieur ou égal| `...>=...` |  Gauche        |
|6           | Egalité| `...==...` |  Gauche        |
|6           | Inégalité| `...!=...` |  Gauche      |
|6           | Egalité| `...===...` |  Gauche       |
|6           | Inégalité| `...!==...` |  Gauche     |
|7           | ET| `&&` |  Gauche            |
|8           | OU| `//` |  Gauche            |
|9           | Ternaire| `...?...:...` |  Droite    |
|10          | Affectation| `... = ...` |  Droite   |

# Utilisation d'opérateur ternaire (`?` et `:`) 

L'opérateur ternaire est un opérateur de comparaison correspondant à une autre facçon d'écrire des conditions. 

La syntaxe est très condensée et permet d'écrire l'instruction en une seule ligne et donc accélérer la vitesse d'exécution du code. 

Cet opérateur est mal aimé car la syntaxe est un peu compliqué de prime abord mais si le code est correctement indenté et commenté, il n'y a aucun soucis dans l'utilisation de cet opérateur. 

```js
x >=10 ? 'x est supérieur à 10' : 'x est strictement inférieur à 10";
```

# L'instruction `switch`

Cette instruction permet d'exécuter un code en fonction de la valeur d'une variable. On peut générer autant de "cas" que l'on souhaite. Cette instruction est une alternative à l'utilisation du `if...else`.

Cependant, ces deux types d’instructions ne sont pas strictement équivalentes puisque dans un `switch` chaque cas va être lié à une valeur précise. En effet, l’instruction `switch` ne supporte pas l’utilisation des opérateurs de supériorité ou d’infériorité. 

```js
let x = 15;

switch(x){
    case 2:
        document.getElementById('p1').innerHTML = 'x stocke la valeur 2';
        break;
    case 5:
        document.getElementById('p1').innerHTML = 'x stocke la valeur 5';
        break;
    case 10:
        document.getElementById('p1').innerHTML = 'x stocke la valeur 10';
        break;
    case 15:
        document.getElementById('p1').innerHTML = 'x stocke la valeur 15';
        break;
    case 20:
        document.getElementById('p1').innerHTML = 'x stocke la valeur 20';
        break;
    default:
        document.getElementById('p1').innerHTML =
        'x ne stocke ni 2, ni 5, ni 10, ni 15 ni 20';
}
```

# Les boucles 

En programmation, une boucle permet d'exécuter plusieurs fois un bloc de code, c'est-à-dire exécuter un code "en boucle". 

Il existe différentes boucles : 

- La boucle `while` (*tant que*)

- La boucle `do...while` (*faire...tant que*)

- La boucle `for` (*pour*)

- La boucle `for...in` (*pour...dans*)

- La boucle `for...of` (*pour...parmi*)

- La boucle `for await...of` (*pour -en attente-...parmi*)

Dans ce genre de boucle, il faut faire comprendre que l'on veut ajouter une valeur. Il s'agit d'incrémenter ou décrémenter (enlever une valeur).

|  Exemple  |  Signification  |
|-----------|-----------------|
| `++x`     | Pré-incrémentation : incrémente la valeur contenue dans la variable x, puis retourne la valeur incrémentée|
| `x++`     | Post-incrémentation : retourne la valeur contenue dans x avant incrémentation, puis incrémente la valeur de $x|
| `--x`     | Pré-décrémentation : décrémente la valeur contenue dans la variable x, puis retourne la valeur décrémentée|
| `x--`     | Pré-décrémentation : décrémente la valeur contenue dans la variable x, puis retourne la valeur décrémentée|

## La boucle `while`

La boucle `while` va nous permettre de répéter une série d’instructions tant qu’une condition donnée est vraie c’est-à-dire tant que la condition de sortie n’est pas vérifiée.

```js
//On initialise une variable let x
let x = 0

//Tant que...
while(x < 10){
    x++;
}
```

## La boucle `do...while`

Lorsqu’on utilise une boucle `do… while`, le code de la boucle va être exécuté avant l’évaluation de la condition de sortie. 

```js
let a = 0;

do{
    a++;
}
while(a < 10);
```

## La boucle `for`

Une boucle for contient trois « phases » à l’intérieur du couple de parenthèses : une phase d’initialisation, une phase de test (condition de sortie) et une phase d’itération (généralement une incrémentation). Chaque phase est séparée des autres par un point-virgule. 

```js
for(let i = 0; i < 10; i++){
    return i;
}
```

## L'instruction `continue`

Pour sauter une itération de boucle et passer directement à la suivante, on peut utiliser une instruction `continue`. Cette instruction va nous permettre de sauter l’itération actuelle et de passer directement à l’itération suivante.

Cette instruction peut s’avérer très utile pour optimiser les performances d’une boucle et économiser les ressources lorsqu’on utilise une boucle pour rechercher spécifiquement certaines valeurs qui répondent à des critères précis.

```js
for(let i = 0; i < 10; i++){
    //Si i / 2 possède un reste, alors i est impair
    if(i % 2 != 0){
        continue;
    }
    document.getElementById('p1').innerHTML +=
    'i stocke la valeur ' + i + ' lors du passage n°'
    + (i + 1) + ' dans la boucle<br>';
}
```

## L'instruction `break`

On va également pouvoir complètement stopper l’exécution d’une boucle et sortir à un moment donné en utilisant une instruction `break` au sein de la boucle.

Utiliser cette instruction peut à nouveau s’avérer très intéressant pour optimiser les performances de notre script lorsqu’on utilise une boucle pour chercher une valeur en particulier en itérant parmi un grand nombre de valeurs.

```js
for(let i = 0; i < 1000; i++){
    //On sort de la boucle dès que la valeur de i atteint 13
    if(i == 13){
        break;
    }
    document.getElementById('p1').innerHTML +=
    'i stocke la valeur ' + i + ' lors du passage n°'
    + (i + 1) + ' dans la boucle<br>';
}
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)