# L'orienté objet en javascript 

Voici les différents points abordés dans cette section :

* Introduction à l'orienté objet

* Création d'un objet et manipulation de ses membres

* Création d'un constructeur

* Constructeur, prototype et héritage

* Les classes

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)


# Introduction à l'orienté objet

Un « paradigme » de programmation est une façon d’approcher la programmation informatique, c’est-à-dire une façon de voir (ou de construire) son code et ses différents éléments.

Il existe trois paradigmes de programmation particulièrement populaires, c’est-à-dire trois grandes façons de penser son code :

- La programmation procédurale : c'est le type de programmation le plus commun et le plus populaire. C'est une façon d'envisager son code sous forme d'enchainement de procédures. C'est une approche verticale du code.

- La programmation fonctionnelle : c'est une façon de programmer qui considère le calcul en tant qu'évaluation de fonctions mathématiques et interdit le changement d'état et la mutation des données.  C'est une façon de concevoir un code en utilisant un enchainement de fonction pures.

- La programmation orientée objet : c'est une façon de concevoir du code autour de concept d'objets. Un objet est une entité qui peut être vue comme indépendante et qui va contenir un ensemble de variables (qu’on va appeler propriétés) et de fonctions (qu’on appellera méthodes).

Le Javascript est un langage qui possède un fort potention pour la programmation orientée objet. Voici un exemple d'objet :

```js
// utilisateur est un objet
let utilisateur = {
    // nom, age et mail sont des propriétés de l'objet. 
    nom : ['Loïc', 'Calcagno']
    age : 29
    mail : 'loic.calcagno@hotmail.com'

    //bonjour est une méthode de l'objet
    bonjour function(){
        alert ("Bonjour, je suis " + this.nom[0] + ", j'ai " + this.age + "ans.")
    }
}
```

Les intérêts supposés principaux de développer en orienté objet plutôt qu’en procédural par exemple sont de permettre une plus grande modularité ou flexibilité du code ainsi qu’une meilleure lisibilité et une meilleure maintenabilité de celui-ci.

Dans tous les cas, les objets font partie du langage JavaScript natif et il est donc obligatoire de savoir les utiliser pour déverrouiller tout le potentiel du JavaScript.

En effet, vous devez bien comprendre ici que certains langages ne proposent pas de composants objets c’est-à-dire ne nous permettent pas de créer des objets et donc de créer du code orienté objet. Certains autres langages supportent l’utilisation d’objets et possèdent quelques objets natifs (objets prédéfinis et immédiatement utilisables).

Le langage JavaScript, pour sa part, possède une très grande composante objet et la plupart des éléments qu’on va manipuler en JavaScript proviennent d’objets natifs du langage. Il est donc indispensable de comprendre comment la programmation orientée objet fonctionne et de connaitre ces objets natifs pour utiliser pleinement le JavaScript. 

# Création d'un objet et manipulation de ses membres

Il existe 4 façons de créer un objet en JS : 
- Créer un objet littéral 
- Utiliser le constructeur `Object()`
- Utiliser une fonction constructeur personnalisée
- Utiliser la méthode `create()`

Dans cette sous-section, on va utiliser la première façon. 

## Création d'un objet littéral

Il s'agit de la façon "classique" de crée un objet. On parle de littéral car on a littérallement constuit les propriétés et méthodes à la construction de l'objet. 

```js
// utilisateur est un objet
let utilisateur = {
    // nom, age et mail sont des propriétés de l'objet. 
    nom : ['Loïc', 'Calcagno']
    age : 29
    mail : 'loic.calcagno@hotmail.com'

    //bonjour est une méthode de l'objet
    bonjour function(){
        alert ("Bonjour, je suis " + this.nom[0] + ", j'ai " + this.age + "ans.")
    }
}
```

## Utiliser le point pour accéder aux membres d'un objet, les modifier ou en définir de nouveaux

Le `.` est ce que l'on appelle un accesseur. Cet accesseur nous permet d'aller chercher la valeur d'un membre mais également de modifier cette valeur.

```js
// utilisateur est un objet
let utilisateur = {
    nom : ['Loïc', 'Calcagno']
    age : 29
    mail : 'loic.calcagno@hotmail.com'
    bonjour function(){
        alert ("Bonjour, je suis " + this.nom[0] + ", j'ai " + this.age + "ans.")
    }
}

//J'utilise l'accesseur pour afficher les propriétés :
console.log(utilisateur.nom)

//J'utilise l'accesseur pour appeler la méthode :
utilisateur.bonjour()

//J'utilise l'accesseur pour modifier une valeur
utilisateur.age = 30

//Je peux également utiliser l'accesseur afin de créer de nouveaux membres 
utilisateur.taille = 170
```

## Utiliser les crochets pour accéder aux membres d'un objet, les modifier ou en définir de nouveaux

On va pouvoir utiliser les crochets pour accéder aux valeurs. Attention! Les méthodes ne sont pas accessibles via les crochets. 

```js
// utilisateur est un objet
let utilisateur = {
    nom : ['Loïc', 'Calcagno']
    age : 29
    mail : 'loic.calcagno@hotmail.com'
    bonjour function(){
        alert ("Bonjour, je suis " + this.nom[0] + ", j'ai " + this.age + "ans.")
    }
}

//J'utilise les crochets pour afficher les propriétés :
console.log(utilisateur['nom'])

//J'utilise les crochets pour modifier une valeur
utilisateur.['age'] = 30
```

## Utilisation du mot clé `this`

Il s'agit d'un mot qui apparait souvent dans la POO. Ici, il sert à faire référence à l'objet qui est couramment manipulé. 

En gros, c'est un prête nom qui va être remplacé par le nom de l’objet actuellement utilisé lorsqu’on souhaite accéder à des membres de cet objet. 

# Création d'un constructeur d'objets

Un constructeur d'objets est une fonction qui va permettre de créer des objets semblables. Il suffit de suivre 2 étapes : 1°/ définir la fonction constructeur et 2°/ appeler ce constructeur.

```js
//1ère étape : 
function Utilisateur(n, a, m) {
    this.nom = n;
    this.age = a;
    this.mail = m;

    this.bonjour = function() {
        alert("Bonjour, je suis " + this.nom[0] + ", j'ai " + this.age + " ans"); 
    }
}

//2ème étape :
let loic = new Utilisateur(["Loïc", "Calcagno"], 29, "loic.calcagno@hotmail.com");
```

Comme on peut le voir, vu que notre constructeur est une fonction, on peut le rappeler autant de fois que l'on veut.

```js
let pierre = new Utilisateur(['Pierre', 'Giraud'], 29, 'pierre.giraud@edhec.com');
let mathilde = new Utilisateur(['Math', 'Ml'], 27, 'math@edhec.com');
let florian = new Utilisateur(['Flo', 'Dchd'], 29, 'flo.dchd@gmail.com');
```

Il est important de préciser que cette fonction de constructeur est un plan de base de l'objet. On pourra modifier le contenu des objets créés à tout moment via les accesseurs. 

# Constructeur, prototype et héritage

On a pu voir que grâce à une fonction constructeur, on peut créer autant d'objets que nécessaire. L'équivalent de cette méthode est l'écriture d'un objet littéral un nombre x de fois. 

Le fait d'écrire un certain nombre de fois l'objet littéral pose un problème de performance car la méthode `bonjour()` est à chaque fois un copier/coller. L'idéal serait de définir une seule fois cette méthode et que chaque objet puisse l'utiliser. Pour cela, on va utiliser des prototypes. 

## Le prototype en JS orienté objet

Il existe 2 grands types de langages orientés objets : ceux basés sur les classes et ceux  sur les prototypes. En JS, on est basé sur la notion de prototype. 

Le contenu de la propriété `prototype` d'un constructeur va être partagé par tout les objets créés à partir de ce constructeur. Comme cette propriété est un objet, on va pouvoir lui ajouter des propriétés et des méthodes que tous les objets créés à partir du constructeur vont partager.

Cela permet l’héritage en orienté objet JavaScript. On dit qu’un objet « hérite » des membres d’un autre objet lorsqu’il peut accéder à ces membres définis dans l’autre objet. 

```js
function Utilisateur(n, a, m) {
    this.nom = n;
    this.age = a;
    this.mail = m;  
}

//J'ajoute des propriétés et des méthodes au prototype de Utilisateur
Utilisateur.prototype.taille = 170;
Utilisateur.prototype.bonjour = function() {
        alert("Bonjour, je suis " + this.nom[0] + ", j'ai " + this.age + " ans"); 
};

let loic = new Utilisateur(["Loïc", "Calcagno"], 29, "loic.calcagno@hotmail.com");
```

## Mise en place d'une hiérarchie d'hobjets avec héritage en JS

Parfois, nous voudrons créer des types d’objets relativement proches. Plutôt que de redéfinir un constructeur entièrement à chaque fois, il va être plus judicieux de créer un constructeur de base qui va contenir les propriétés et méthodes communes à tous nos objets puis des constructeurs plus spécialisés qui vont hériter de ce premier constructeur. 

Pour mettre en place un héritage, on utilise toujours 3 étapes :

- On crée un constructeur qui sera le constructeur parent

- On crée ensuite un constructeur enfant qui appele le parent

- On modifie la `__proto__` de la propriété `prototype` de l'enfant pour qu'elle soit égale au parent

```js
function Ligne(longueur) {
    this.longueur = longueur;
}
//Ajout d'une méthode au constructeur Ligne
Ligne.prototype.taille = function() {
    alert(this.longueur);
}

// call() permet d'appeler le constructeur Ligne() dans Rectangle()
function Rectangle(longueur, largeur){
    Ligne.call(this, longueur);
    this.largeur = largeur;
}
Rectangle.prototype = Object.create(Ligne.prototype);
Rectangle.prototype.constructor = Rectangle;
Rectangle.prototype.aire = function(){
    alert("Aire : " + this.longueur*this.largeur);
}

function Parallelipipede(longeur, largeur, hauteur){
    Rectangle.call(this, longueur, largeur);
    this.hauteur = hauteur;
}
Parallelipipede.prototype = Object.create(Rectangle.prototype);
Parallelipipede.prototype.constructor = Parralelipipede;
Parallelipipede.prototype.surface = function() {
    alert("Surface : " + this.longueur * this.largeur * this.hauteur);
}

let geo = new Parallelipipede(5,4,3);
geo.surface();
geo.aire();
geo.taille();
```

# Les classes

Une classe est un plan général qui va servir à créer des objets similaires. Le code d’une classe va généralement être composé de propriétés et de méthodes dont vont hériter les objets qui vont être créés à partir de la classe. 

Il existe de grandes différences conceptuelles entre les langages orientés objet basés sur les classes et ceux bases sur les prototypes. On peut notamment noter les suivantes :

- Dans les langages basés sur les classes, tous les objets sont créés en instanciant les classes

- Une classe contient toutes les définitions des propriétés et méthodes dont dispose un objet. On ne peux pas ensuite rajouter ou supprimer des membres à un objet dans les langages basés sur les classes.

- L'héritage se fait en définissant des classes mères et des classes étendues.

Même si JS est un langage basé sur les prototypes, il est possible de travailler avec des classes. C'est une nouvelle syntaxe JS pour les devs qui sont habitués à travailler avec les langages orientés classes. 

## Création d'une classe et d'objets en JS

```js
class Ligne{
    constructor(nom, longueur) {
        this.nom = nom;
        this.longueur = longueur;
    }
    taille() {
        alert("Longueur de " + this.nom + " : " + this.longueur);
    }
}

let geo1 = new Ligne('geo1', 10);
geo1.taille();
```

## Classes étendues et héritage

```js
class Ligne{
    constructor(nom, longueur) {
        this.nom = nom;
        this.longueur = longueur;
    }
    taille() {
        alert("Longueur de " + this.nom + " : " + this.longueur);
    }
}

let geo1 = new Ligne('geo1', 10);
geo1.taille();

//Héritage
class Rectangle extends Ligne {
    constructor (nom, longueur, largeur) {
        super(nom, longueur);
        this.largeur = largeur;
    }
    aire() {
        alert("aire de " + this.nom + " : " + this.longueur+ " : " + this.largeur) ;
    }
}

let geo2 = new Rectangle('geo2', 7,5);
geo2.aire();
geo2.taille();
```

# Conclusion sur l'orienté objet et les classes

Le JavaScript est un langage qui possède un fort potentiel objet. En effet, ce langage utilise les objets dans sa syntaxe même et la grande partie des éléments que nous manipulons en JavaScript sont en fait des objets ou vont pouvoir être convertis en objets et traités en tant que tel.

Le JavaScript est un langage objet basé sur les prototypes. Cela signifie que le JavaScript ne possède qu’un type d’élément : les objets et que tout objet va pouvoir partager ses propriétés avec un autre, c’est-à-dire servir de prototype pour de nouveaux objets. L’héritage en JavaScript se fait en remontant la chaine de prototypage.

Récemment, le JavaScript a introduit une syntaxe utilisant les classes pour son modèle objet. Cette syntaxe est copiée sur les langages orientés objets basés sur les classes et nous permet concrètement de mettre en place l’héritage en JavaScript plus simplement.

Attention cependant : cette syntaxe n’introduit pas un nouveau modèle d’héritage dans JavaScript ! En arrière-plan, le JavaScript va convertir les classes selon le modèle prototypé. Il reste donc essentiel de comprendre le prototypage en JavaScript.

En plus de la possibilité d’utiliser l’orienté objet pour créer nos propres objets et nos propres chaines de prototypage, le JavaScript possède des objets (constructeurs) prédéfinis ou natifs comme `Object()`, `Array()`, `Function()`, `String()`, `Number()`, etc. dont nous allons pouvoir utiliser les méthodes et les propriétés. 

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)