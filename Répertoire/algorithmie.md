# Les concepts de l'algorithmie et Javascript

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

Différents points en algorithmie sont abordés : 

- Les variables

- Les structures de contrôle

- Les arrays

- Les fonctions 

- Les objets 

- Les classes 

# Les variables

La commande `console.log` permet de visionner un éléments dans la console. 

Pour déclarer une variable, on attribue une valeur à la variable. 

```js
let phrase = "Coding is fun!";
```

# Les structures de contrôle

Ce sont des éléments de programmation ayant une influence sur le comportement du programme.

## Les opérateurs de comparaison 

| Opérateur  | Signification         |
| :--------------- |:---------------:| 
| `==`  |   est exactement pareil      |  
| `!=`  | est différent de             |   
| `>`   | est supérieur à          |   
| `>=`   | est supérieur ou égal à          |   
| `<`   | est inférieur à         |   
| `<=`   | est inférieur ou égal à    |   

## Les opérateurs logiques 

| Opérateur  | Signification         |
| :--------------- |:---------------:| 
| `&&`  |   'et'      |  
| `||`  | 'ou'             |   
| `!`   | inverse la valeur de l'opérateur          |   

## Les combinaisons d'opérateurs 

| Opérateur  | Signification         |
| :--------------- |:---------------:| 
| `(a>2)&&(b<4)`  |   a est plus grand que a ET b est plus petit que 4     |  
| `!(a<2)`  | a n'est pas plus petit que 2|   

## Les boucles

### La boucle if .. else

Il s'agit d'une boucle qui teste une condition. Si elle n'est pas respectée, la boucle continue.

```js
let size = 185;
let weight = 80;

if ((size >= 150) || (weight >= 45)) {
  console.log("You probably are an adult");
} else {
  console.log("You probably are a child");
}
```

L'opérateur `?` permet de remplacer l'écriture d'une boucle if :

```js
let size = 185;
let weight = 80;

(size >= 150) || (weight >= 45) ? console.log("You probably are an adult") : console.log("You probably are a child");
```

### La boucle if .. else if .. else

Il s'agit d'une boucle qui teste une condition de départ. Si elle n'est pas respectée, la boucle continue vers les conditions intermédiaires.

```js
let size = 185;
let weight = 80;

if ((size >= 150) || (weight >= 45)) {
  console.log("You probably are an adult");
} else if ((size >= 50) || (weight >= 10)) { {
  console.log("You probably are a child");
} else {
  console.log("You probably are a baby");
}
```

### La boucle while

Il s'agit d'une boucle qui va répéter le code TANT QU'il n'est pas vrai.

```js
let i = 1;

while (i <= 100) {
  console.log(i);
  i += 1;
}
// Ce code imprime tout les chiffres entre 1 et 100
```

### La boucle for

La boucle for est une version spécilisée de while prenant 3 paramètres : 

*  le premier paramètre est la commande de départ de la boucle

* le deuxième paramètre est la commande spéficiant à la boucle à partir de quel moment elle doit s'arrêter

* le troisième paramètre est la commande qui est exécutée à chaque tour (incrémenter par exemple)

```js
for (let i = 1; i <= 100; i += 1) {
  console.log(i);
}
// Ce code imprime tout les chiffres entre 1 et 100
```

### La boucle do ... while

Il s'agit d'une boucle qui exécute une instruction jusqu'à ce que la condition de test ne soit plus vérifiée. 

```js
let result = '';
let i = 0;

do {
  i = i + 1;
  result = result + i;
} while (i < 5);
```

### La boucle switch

L'instruction switch évalue une expression et, selon le résultat obtenu et le cas associé, exécute les instructions correspondantes.

```js
const expr = 'Papayas';
switch (expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Mangoes':
  case 'Papayas':
    console.log('Mangoes and papayas are $2.79 a pound.');
    // expected output: "Mangoes and papayas are $2.79 a pound."
    break;
  default:
    console.log(`Sorry, we are out of ${expr}.`);
}
```

### Break et continue

L'instruction break permet de terminer la boucle en cours ou l'instruction switch ou label en cours et de passer le contrôle du programme à l'instruction suivant l'instruction terminée.

```js
let i = 0;

while (i < 6) {
  if (i === 3) {
    break;
  }
  i = i + 1;
}

console.log(i);
// expected output: 3
```

L'instruction continue arrête l'exécution des instructions pour l'itération de la boucle courante ou de la boucle étiquetée. L'exécution est reprise à l'itération suivante.

```js
let text = '';

for (let i = 0; i < 10; i++) {
  if (i === 3) {
    continue;
  }
  text = text + i;
}

console.log(text);
// expected output: "012456789"
```

# Les arrays

Il s'agit de structure assez simple en programmation consistant au stockage d'éléments dans un ordre précis.

## Déclaration 

On peut déclarer un array vide ou un array avec des éléments définis à l'intérieur. Ces éléments peuvent être des nombres, des booléens, des chaines de caractères, etc...

```js
let arrVide = [];

let arrNombre = [1,2,3];

let arrString = ["pomme", "arbre", "abeille"];
```

## Accès à un élément de l'array

On peut accéder à un élément d'un array grâce à sa position que l'on nomme index. **ATTENTION**, la première position dans un array est la position 0 et non 1.

```js
let array = ["pomme", "cerise", "abricot"];
console.log(array[1]); //cerise
```

On peut également modifier un array en accédent à l'index d'un élément. 

```js
let array = [1,2,3];
array[0] = 24;

console.log(array); // [24,2,3]
```

## Obtenir la longueur d'un array

La méthode `.length` permet d'indiquer la taille d'un array :

```js
let arr = ["pomme", "cerise", "ananas"];
console.log(arr.lenght); //3
```

## Modification d'un array

Diverses méthodes existent pour modifier un array : 

- `push()` : ajoute un élément à la fin de l'array

- `pop()` : supprime un élément à la fin de l'array

- `shift()` : supprime un élément au début de l'array

- `unshift()` : ajoute un élément au début de l'array

```js
let arr = ["pomme", "cerise", "ananas"];

arr.push("kiwi"); // ["pomme", "cerise", "ananas", "kiwi"]

arr.pop(); //["pomme", "cerise"]

arr.shift() ; //["cerise", "ananas"]

arr.unshift("abricot"); ["abricot", "pomme", "cerise", "ananas"]
```

## Itération d'un array

Lorsque l'on veut itérer sur un array, on peut utiliser une boucle ``for`` : 

```js
let arr = [1,2,3,4];

for (let i = 0, i < arr.length, i++) {
  arr[i] = arr[i]*3
}

console.log(arr) ; //[3,6,9,12]
```

Une autre façon d'écrire cette boucle est d'utiliser une boucle ``for..of`` :

```js
let arr = [1,2,3,4];

for (let element of arr) {
  element*3
}

console.log(arr); //[3,6,9,12]
```

Une méthode existe également afin d'itérer sur un array, il s'agit de la méthode `.map`: 

```js
let arr = [1,2,3,4];

let arr1 = arr.map(x => x*3);

console.log(arr1); //[3,6,9,12]
```

# Les fonctions

Les fonctions sont des pièces de code réutilisable (un peu comme les mixins en SASS). L'intérêt des fonctions est multiple : 

- Les fonctions permettent de réutiliser plusieurs fois le même code.

- Les fonctions permettent de diminuer le risque d'erreur lorsque l'on recopier plusieurs fois les mêmes instructions. 

- Il est conseillé d'utiliser une fonction lorsque l'on répète au moins 2 fois la même instruction.

## Ecriture d'une fonction 

L'écriture de base d'une fonction fait appel à 3 éléments : 

```js
function nomDeLaFonction(argument(s)) {
  //bloc d'instruction
}
```

Prenons l'exemple d'un calcul d'une somme qui doit être réalisé plusieurs fois dans un script. On peut faire une fonction ainsi, il n'y aura qu'à appeler la fonction au moment d'effectuer la somme :

```js
function somme(a, b) {
  return a + b;
}

somme(3,4); // 7
```

## Les fonctions fléchées 

Les fonctions fléchées sont une autre forme de syntaxe d'écriture de fonctions :

```js
nomDeLaFonction = (argument(s)) => {
  //bloc d'instruction
}
```

Si on reprend notre fonction somme, la nouvelle syntaxe devient: 

```js
somme = (a, b) => {
  return a + b;
}
```

## La récursivité 

Le principe de la récursivité dans la programmation est le fait d'appeler la fonction elle-même dans l'instruction

```js
function count(i) {
  if (i <= 100) {
    count(i + 1)
    console.log(i);
  }
}
```

## L'aide des fonctions

Lorsque l'on utilise des fonctions dans un script, il faut le nom de la fonction soit assez parlant pour aider un autre dev à comprendre le code. On peut également ajouter de la JSdoc permettant de faire de la documentation de fonction. 

Si on reprend notre fonction somme : 

```js
/*
* @function somme()
* Fonction permettant de faire la somme entre deux valeurs numériques
*
* @param {number} a  - un nombre
* @param {number} b  - un nombre
* @returns {number} - la somme des deux nombres
*
* @example somme(2,1) // return 3
*/

function somme(a, b) {
  return a + b;
}
```

# Les objets 

Les objets sont des structures de programmation assez simple comme les arrays. Dans le cas des objets, l'accès ne se fait pas via les index mais via un système de clé:valeur. 

```js
let objet = {
  prenom : "Loïc",
  nom : "Calcagno",
  age : 29
}
```

Si je veux accéder à un élément de l'objet, il suffit d'appeler la clé pour avoir accès à la valeur. Si je veux voir l'âge, je fais : 

```js
console.log(objet.age)
```

On peut même imaginer combiner les objets et les arrays pour avoir accès à des structures plus complexes. 

```js
let presentation = {
  prenom : "Loïc",
  nom : "Calcagno",
  age : 29, 
  skills : [
    {
      skillname : "HTML",
      level : "advanced"
    } , 
    {
      skillname : "Javascript",
      level : "basic"
    }
  ],
  "address" : {
    localite : "La Hestre", 
    codePostal : 7170
  }
}
```

# Les classes 

Les classes sont des outils en programmation qui sont plus compliquées que le reste. On utilise d'ailleurs ces classes dans la POO (*P*rogrammation *O*rienté *O*bjet).

Une classe est composée d'un constructeur, de méthodes, de méthodes getter et setter. 

Notons également qu'un héritage peut avoir lieu entre différentes classes.

## Les constructeurs 

Un constructeur est la fonctionne qui sera appelée lorsque l'objet est créé. 

```js
class Presentation {
  constructor(prenom, nom) {
    this.prenom = prenom;
    this.nom = nom
  }
}
```

Lors de la création d'un objet à partir d'une classe, on appelle l'objet créé une *instance*. Ce procédé de création à partir d'une classe se nomme l'*instanciation*. 

```js
let x = new Presentation("Loïc", "Calcagno");
```

X est l'instance de la classe Presentation possédant 2 arguments -prénom et nom- définit par le constructeur de la classe.

## Les méthodes et `this`

Une classe possède diverses méthodes. Il s'agit juste d'une fonction mais dans un contexte de classe. Les méthodes sont donc des fonctions qui exécute un bloc d'instruction.

Le mot-clé `this` est d'ailleurs une méthode qui permet d'accéder à l'objet en question.

```js
class Presentation {
  constructor(prenom, nom) {
    this.prenom = prenom,
    this.nom = nom
  }
  salutation(other) {
    console.log("Hey, je m'appelle" + this.prenom + " et je te souhaite la bienvenue sur ce " + other);
  }
}

let x = new Presentation("Loïc", "Calcagno").salutation("dépôt GitHub");

console.log(x);
// "Hey, je m'appelle Loïc et je te souhaite la bienvenue sur ce dépôt GitHub"
```

## Setter et getter 

La syntaxe de la méthode get permet de lier une propriété d'un objet à une fonction qui sera appelée lorsque l'on accédera à la propriété. 

Tout ça pour dire, que grâce à la méthode get, j'appelle un élément via la propriété sans le modifier. 

```js
class Presentation {
  constructor(prenon) {
    this.prenom = prenom;
  }
  get afficherPrenom() {
    return thisPrenom
  }
}

let x = new Presentation("Loïc"); //J'instancie x 

console.log(x.afficherPrenom) //"Loïc"
```

La syntaxe de la méthode set permet de lier une propriété d'un objet à une fonction qui sera appelée à chaque tentative de modification de cette propriété. 

Tout ça pour dire, que je peux venir modifier une propriété de ma classe via une valeur que j'attribue à ma méthode set. 

```js
class Presentation {
  constructor(prenon) {
    this.prenom = prenom;
  }
  set changerPrenom (val) {
    this.prenom = val
  }
}

let x = new Presentation("Loïc"); //J'instancie x 
x.changerPrenom = "Nathan"; //Je change la valeur de l'élément présent dans l'instance via la méthode set

console.log(x) // "Nathan"
```

## Les accesseurs 

L'opérateur `.` permet d'accéder à n'importe quel attribut d'un objet. 

Une classe permet de faire un *faux attribut* permettant de déclencher une fonction.

```js
class Presentation {
  constructor(prenom) {
    this.prenom = prenom;
  }
  get changementPrenom() {
    return this.prenom[0]; //Signifie que je récupère le premier élément d'un array
  }
  set changementPrenom(val) {
    this.prenom[0] = val; //Signifie que je remplace l'élément 0 de l'array par la valeur de la méthode set
  }
}

let x = new Presentation(["Loïc", "Wickham"]);
// J'utilise la méthode get 
console.log(x.changementPrenom); // Loïc

// J'utilise la méthode set 
x.changementPrenom = "Marc";
console.log(x.changementPrenom); // Marc
```

## L'héritage de classe 

Lorsque l'on utilise des classes, il est possible de réutiliser des méthodes définies dans d'autres classes. C'est ce que l'on appelle l'héritage des classes. 

```js
class Presentation {
  constructor(prenom) {
    this.prenom = prenom;
  }
  get afficherPrenom(){
    return this.prenom
  }
  set afficherPrenom (val) {
    this.prenom = val
  }
}

class Stage extends Presentation {
  constructor(nom) {
    this.nom = nom
  }
  salutation() {
    return super.afficherPrenom + this.nom
  }
}

let x = new Presentation("Loïc");
console.log(x.Stage("Calcagno").salutation());
// "Loïc Calcagno" 
``` 

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)