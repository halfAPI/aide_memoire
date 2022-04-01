# Utilisation des expressions régulières (regexp) en JS

Voici les points abordés dans cette section :

* Introduction aux expression régulières/relationnelles

* Utilisation des regexp pour effectuer des recherches et remplacements

* Les classes de caractères et abrégées

* Les métacaractères

* Création de sous masques et d'assertions

* Les options des regexp

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Introduction aux expression régulières/relationnelles

Les expressions régulières (ou regex) sont des schémas (ou motifs, ou patterns) utilisés afin d'effectuer des recherches et des remplacements dans des chaines de caractères. 

Une regex n'est tout simplement qu'une séquence de caractères. 

Il existe deux façon d'écrire une regex: 

- De manière littérale : 

```js
let regex = /expression/;
```

- Avec le constructeur `new RegExp()` :

```js
let regex = new RegExp('expression');
```

Dans ce cas présent, le motif à rechercher se compose d'une succession de lettre bien précise dans un ordre bien précis. La puissance de cette regex n'est dont pas optimale. 

Cependant, on peut créer des expressions plus complexes et qui seront beaucoup plus puissantes. Pour cela, on utilise des caractères spéciaux qui auront une signification dans le contexte des expressions régulières.

# Utilisation des regexp pour effectuer des recherches et remplacements

## La méthode `match()`

Il s'agit d'une méthode de l'objet `String` permettant de rechercher la présence de caractères dans une chaine. 

Il faut noter que la méthode match() ne renvoie par défaut que la première correspondance ! Pour avoir toutes les correspondances, il est nécessaire d'indiquer que l'on fait une rechercher globale au moyen de `/regex/g`.

```js
let chaine = "Les regex c'est trop Cool!";

let regex = /[A-Z]/ ;
let regex1 = /[A-Z]/g ;
let regex2 = /[0-9]/;

console.log(chaine.match(regex)) //L
console.log(chaine.match(regex1)) //L,C
console.log(chaine.match(regex2)) //null
```

## La méthode `search()`

Cette méthode permet d'effectuer une recherche dans une chaine de caractère. La différence avec la méthode `match()` est qu'ici, on va avoir un retour sur la position à laquelle se trouve la première occurence de l'expression. 

```js
let chaine = "Les regex c'est trop Cool!";

let regex = /[A-Z]/ ;
let regex1 = /[A-Z]/g ;
let regex2 = /[0-9]/;

console.log(chaine.search(regex)) //0
console.log(chaine.search(regex1)) //21
console.log(chaine.search(regex2)) //-1
```

## La méthode `replace()`

Il s'agit d'une méthode permettant de rechercher un pattern bien précis et le remplacer par un autre. Cette méthode demande donc 2 arguments: la pattern à modifier et le patter de remplacement. 

Tout comme `match()`, on peut travailler de façon globale sur la méthode `replace()`.

```js
let chaine = "Les regex c'est trop Cool!";

let regex = /[A-Z]/ ;
let regex1 = /[A-Z]/g ;
let regex2 = /Cool/;

console.log(chaine.replace(regex, ' ')) //es regex c'est trop Cool!
console.log(chaine.replace(regex1, '@')) //@es regex c'est trop @ool!
console.log(chaine.replace(regex2, 'formidable')) //Les regex c'est trop formidable!
```

## La méthode `split()`

Il s'agit d'une méthode qui permet de diviser ou casser une chaine de caractères en fonction d'un séparateur défini.

```js
let chaine = "Les regex c'est trop Cool!";

let regex = /[A-Z]/ ;

console.log(chaine.split(regex)) //L,es regex c'est trop C,ool!
```

## La méthode `exec()`

Cette méthode va rechercher des correspondances entre une chaine et une regex. Cette méthode retourne un tableau avec les résultats si au moins une correspondance a été trouvée. 

```js
let chaine = "Les regex c'est trop Cool!";

let regex = /[A-Z]/ ;

let table = regex.exec(chaine)
console.log(table[0]) //L
```

## La méthode `test()`

Cette méthode permet de tester une correspondance mais va renvoyer un booléen. 

```js
let chaine = "Les regex c'est trop Cool!";

let regex = /[A-Z]/ ;

(regex.test(chaine)) ? console.log("Pattern trouvé!") : console.log("Pattern inconnu");
```

# Les classes de caractères et abrégées

## Les classes de caractères 

Une classe de caractères permet de fournir différents choix de correspondances pour un caractère en spécifiant un ensemble de caractères. 

La déclaration d'une classe de caractères se fait au moyen des crochets `[]`

Voici quelques exemples de classes de caractères : 

```js
// Chercher une voyelle
let regex1 = /[aeuioy]/g;

// Chercher un 'j' suivi d'une voyelle (en gros, on recherche toutes les séquences "ja", "je", "ju", "ji", "jo" et "jy")
let regex1 = /j[aeuioy]/g;

// Chercher une voyelle qui suit une autre voyelle
let regex1 = /[aeuioy][aeuioy]/g;
```

## Les métacaractères

On peut retrouver des caractères qui vont posséder une signification bien particulière, ce sont des métacaractères. Les premiers métacaractères que l'on a pu voir sont les `[` et `]`.

Il en existe de très nombreux mais lorsqu'un métacaractère est associé à une classe de caractères, ces premier perdent leur signification spéciale. C'est pourquoi il est toujours important de bien faire attention au sens de ces caractères selon qu'ils se situent dans ou à l'extérieur de la classe de catactères.

| Métacaractère | Description |
|---------------|-------------|
|     `\`       |Caractère d'échappement (on peut s'en servir pour donner un sens spécial à des caractères qui n'en possèdent pas ou tout simplement annuler l'effet d'un métacaractère)|
|     `^`       | S'il est placé en début de classe, il permet de nier la classe|
|    `-`        | Entre deux caractères, il permet de spécifier un intervalle de caractères|

Voyons quelques exemples : 

```js
// Chercher autre chose qu'une voyelle dans la chaine
let regex = /[^aeyuio]/g;

// Chercher ^ ou une voyelle dans la chaine
let regex = /[\^aeyuio]/g;

// Chercher ^ ou une une voyelle dans la chaine
let regex = /[aey^uio]/g;

// Chercher une lettre minuscule suivie d'un o 
let regex = /[a-z]o/g;

// Chercher une lettre suivie d'un o
let regex = /[a-zA-Z]o/g;

// Chercher a, - et z
let regex = /[a\-z]/g;

// Chercher un chiffre, a, z et -
let regex = /[0-9az-]/g;

// Chercher un chiffre, /, [ et ]
let regex = /[0-9\/\[\]]/g;
```

## Les classes de caractères abrégées

On vient de voir que le backslash permet de protéger le sens de certains métacaractères. On va également pour l'utiliser avec des caractères normaux pour leur donner une signification spéciale.

On va donc utiliser ce qu'on appelle des classes abrégées pour indiquer qu'on recherche un certain type de valeurs.

| Classe abrégée | Description | 
|----------------|-------------|
| `\w`           | Représente tout caractère de "mot". Equivaut à [a-zA-Z0-9_]|
| `\W`           | Représente tout ce qui n'est pas caractère de "mot". Equivaut à [^a-zA-Z0-9_]|
| `\d`           | Représente un chiffre. Equivaut à [0-9]|
| `\D`           | Représente tout ce qui n'est pas un chiffre. Equivaut à [^0-9]|
| `\s`           | Représente un caractère blanc (espace, retour à la ligne)|
| `\S`           | Représente tout caractère qui n'est pas un caractère blanc|
| `\t`           | Représente un espace horizontale (tabulation)|
| `\v`           | Représente un espace verticale|
| `\n`           | Représente un saut de ligne|

Voyons quelques exemples : 

```js
// Correspond à un caractère alphanumérique ou "_"
let regex = /\w/g;

// Correspond à tout sauf un caractère alphanumérique ou "_"
let regex = /\W/g;

// Correspond à un chiffre
let regex = /\d/g;

// Correspond à un chiffre ou une lettre minuscule
let regex = /[\da-z]/g;
```

# Les métacaractères

## Le point

Le métacaractère point `.` permet de rechercher n'importe quel caractère à l'exception du caractère pour une nouvelle ligne.

```js
//Un "o" suivi par n'importe quel caractère sauf \n
let regex = /o./g; 

//Un "o" suivi d'un point
let regex = /o\./g; 

//Un "o" suivi d'un point
let regex = /o[.]/g;  

//Un "o" ou un point
let regex = /[o.]/g;
```

## Les alternatives

Le métacaractère `|` permet de proposer des alternatives. Cela correspond +/- à "OU". 

```js
// un "o" ou un "j"
let regex = /o|j/g;
```

## Les ancres 

Les deux caractères `^` et `$` vont permettre d'ancrer les regex. 

L'ancre `^` permet d'exprimer le fait qu'on recherche le caractère en début de la chaine. Alors que l'ancre `$` permet d'exprimer la recherche du caractère en fin de chaine. 

```js
// n'importe quel caractère en début de chaine sauf \n
let regex = /^./g;

// une majuscule en début de chaine
let regex = /^[A-Z]/g;

//n'importe quel caractère en fin de chaine sauf \n
let regex = /.$/g;

// "a^$b" dans la chaine
let regex = /a\^\$b/g;

// "e" ou "$" dans la chaine
let regex = /[e$]/g;

// autre chose qu'une minuscule en début de chaine
let regex = /^[^a-z]/g;

// trois caractères exactement sans retour à la ligne
let regex = /^...$/g;
```

## Les quantificateurs 

Ce sont des métacaractères qui vont représenter une certaine quantité d'un caractère ou d'une séquence de caractères.

| Quantificateur | Description |
|----------------|-------------|
|`a{X}`          | On veut une séquence de X fois 'a'|
|`a{X,Y}`          | On veut une séquence de X à Y fois 'a'|
|`a{X,}`          | On veut une séquence d'au moins X fois 'a' sans limite supérieure|
|`a?`          | On veut 0 ou 1 fois 'a'|
|`a+`          | On veut au moins 1 fois 'a'|
|`a*`          | On veut 0, 1 ou plusieurs fois 'a'|

# Création de sous masques et d'assertions

## Les sous masques

Les métacaractères décrivant les sous masques sont `()`. Un sous masque est une partie d'un pattern. Les parenthèses permettent d'isoler des alternatives ou de définir sur quelle partie du pattern le quantificateur doit s'appliquer. 

Les parenthèses forment ce qu'on appelle des sous masques **capturants**. Cela signifie que lorsqu'un sous masque est trouvé dans la chaine, la correspondance sera gardée en mémoire et pourra être réutilisée par la suite. 

```js
//correspondance : "er" ou "et" + capture r ou t
let regex = /e(r|t)/g;

//correspondance : "bonjour" + capture jour"
let regex = /Bon(jour)/;

//correspondance : "er" ou "et" + pas de capture car option g
let regex = /Bon(jour)/g;
```

## Les assertions

Ce sont des tests qui vont se dérouler sur le ou les caractères suivants ou précédents celui qui est à l'étude actuellement. Par exemple, `$` est une assertion puisque l'idée est de vérifier qu'il n'y a plus rien après le `$`. C'est une assertion simple. 

Il existe également 2 types d'assertions complexes et les assertions arrière. Ces assertions peuvent également être positives ou négatives. 

- assertion avant : teste les caractères suivant celui qui est à l'étude

- assertion arrière : teste les caractères précédents celui qui est à l'étude

- assertion positive : cherche la présence d'un caractère avant ou après le caractère à l'étude

- assertion négative : ne cherche pas la présence d'un caractère avant ou après le caractère à l'étude

Voici les assertions complexes : 

| Assertion | Description |
|-----------|-------------|
|`a(?=b)`   | Cherche 'a' suivi de 'b' (assertion avant positive)|
|`a(?!b)`   | Cherche 'a' non suivi de 'b' (assertion avant négative)|
|`(?<=b)a`   | Cherche 'a' précédé de 'b' (assertion arrière positive)|
|`(?<!b)a`   | Cherche 'a' non précédé de 'b' (assertion arrière négative)|


# Options des regexp

Les options sont des modificateurs permettant d'ajouter des options aux regex. Ce ne sont pas des caractères à chercher à proprement parler. Il va y avoir une action à un niveau plus élevé car on modifie le comportement par défaut de l'expression. 

Voici une liste des options les plus utiles : 

| Option | Description |
|--------|-------------|
| `g`    | Permet d'effectuer une recherche globale|
| `i`    | Rend la recherche insensible à la casse|
| `m`    | Il s'agit d'une option permettant de tenir compte des caractères de retour à la ligne et donc les ancres `^ $` vont pouvoir être utilisées un début et une fin de ligne|
| `s`    | Permet au métacaractère `.` de remplacer n'importe quel caractère, y compris un `\n` |

```js
// Cherche "becode" exactement
let regex = /becode/; 

// Cherche "becode", "BECODE", "BEcoDE", "BeCoDe", "bEcOdE" ,...
let regex = /becode/i;

// Cherche un "e" en fin de chaque ligne
let regex = /e$/gm;

// Cherche tout caractère et effectue une recherche globale
let regex = /./gs;
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)
