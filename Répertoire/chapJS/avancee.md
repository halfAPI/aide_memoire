# Notions avancées en javascript

Voici les points abordées dans cette section : 

* Paramètres du reste

* Opérateur de décomposition

* Les fonctions fléchées

* Les closures 

* Gestion du délai avec `setTimeout()` et `setInterval()`

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Paramètres du reste

En JS, les fonctions prédéfinies acceptent un certains nombre défini d'arguments. Mais parfois, on aimerait accepter un nombre variable d'arguments. Pour cela, on utilise la notation `...` dans la déclaration du paramètre. On parle de "paramètres du reste".

```js
let a = 1, b = 2, c = 3, d = 4;

function somme(...nombres){
    let s = 0;
    for(let nombre of nombres) {
        s += nombre;
    }
    return s;
}
```

Notons tout de même que cette notation ne fonctionnera QUE si le paramètre de reste est placé toujours en dernier argument de fonction.

```js
let nom = "Calcagno", prenom = "Loic";

function profil(nom, prenom, ...hobbies){
    let h = '',
    for(hobbie of hobbies){
        h += hobbie + ',';
    }
}
```

# L'opérateur de décomposition

Cet opérateur fait l'inverse du paramètre de reste. Il transforme un tableau en une liste d'arguments que l'on peut passer à une fonction. On utilise la même syntaxe `...`.

```js
let tb1 = [3,5,1,32];
let tb2 = [64,-5,17];

/*
alert('Plus grand nombre de tb1 : ' + Math.max(...tb1));
alert('Plus grand nombre de tb1 et tb2 : ' + Math.max(...tb1, ...tb2));
*/
```

# Les fonctions fléchées

Les fonctions fléchées sont des fonctions ([Rappel sur les fonctions](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/chapJS/fonction.md)) dont la syntaxe est très compacte. 

```js
/*Ecriture d'une fonction avec le mot clé 'function()*/
let somme = function(a,b){
    return a + b;
}

/*Ecriture en fonction fléchée*/ 
let somme = (a,b) => a + b;

/*Ecriture d'une autre fonction fléchée*/
let double = n => n * 2;
```

Les fonctions fléchées n'ont pas besoin du couple d'accolades pour fonctionner et n'ont pas besoin du `return` car cette syntaxe évalue automatiquement l'expression à droite du `=>` en retournant son résultat.

## Les fonctions fléchées et le mot clé `this`

Le mot clé `this` permet d'accéder à des informations stockées dans un objet. Ici, le mot clé va être substitué par l'objet utilisant la méthode lors de son appel. 

```js
let loic = {
    nom: 'Calcagno',
    prenom: 'Loic',
    hobbies: ['tennis', 'natation', 'codage']

    disBonjour({
        let bonjour = () => alert('Bonjour' + this.prenom);
        bonjour();
    })
}
```

## Les fonctions fléchées et l'objet `arguments`

L’objet arguments est un objet qui recense les différents arguments passés à une fonction. Cet objet est une propriété disponible dans toutes les fonctions à l’exception des fonctions fléchées. 

Aujourd’hui, on préfèrera cependant manipuler les arguments en utilisant les paramètres du reste plutôt que cet objet tant que possible. 

# Les closures 

## Portée et durée de vie des variables 

Pour rappel, en JS, toutes les variables ne possèdent pas le même environnement, il y a le contexte global et local. 

```js
let x = 5; //variable globale

function portee1(){
    let y = 10; //variable locale
    alert(x+y);
}

function portee2() {
    let x = 100;
    alert(x);
}

portee1(); //5 + 10 = 15
x = 20
portee1(); //20 + 10 = 30
portee2(); //100
```

De plus, il est possible d'imbriquer des fonctions. On parle de fonctions externes pour la fonction conteneur et de fonctions internes pour la fonction contenue.

**Attention**! La fonction externe n'a aucun moyen d'accéder aux variables de la fonction interne. Mais la fonction interne peut accéder aux variables de la fonction externe. 

```js
let prenom = 'Loic';

//bio() a accès à let prenom (et à let age) mais pas à let hobbie
function bio(){
    let age = 29;
    //hobbies() a accès à let prenom et à let age (et à let hobbie)
    function hobbies(){
        let hobbie =  'Tennis';
        return prenom + ', ' + age + ' ans. Je fais du ' + hobbie;
    }
    return hobbies();
}
```

En plus de tout ça, il faut savoir que les variables ont une durée de vie. 

- La variable globale existe durant la durée d'exécution du scrip et est ensuite écrasée. 

- La variable locale n'existe que durant l'exécution de la fonction... **Sauf si on étend sa durée de vie avec une closure**.

## Les closures en pratique

Une closure est une fonction interne qui se souvient et peut continuer à accéder à des variables définies dans sa fonction parente même après la fin de l'exécution de celle-ci. 

Prenons l'exemple d'un compteur. On crée une fonction qui initialise `count` à 0 et définit une fonction anonyme interne qui retourne `count`. 

```js
function compteur(){
    let count = 0; 

    return function(){
        return count++;
    }
}

let plusUn = compteur();
```

Quand on appelle `compteur()`, le code de la fonction anonyme est retourné mais pas exécuté. Pour l'exécuter, il suffit de stocket le résultat retourné par `compteur()` dans une variable et d'ensuite utiliser cette variable comme une fonction. 

En toute logique, lorsque l'on appelle `plusUn`, la fonction a terminée son exécution et donc la variable `count` ne devrait plus être accessible. Pourtant, si on exécute le code, il fonctionne bien! 

```js
alert(plusUn()); //0
alert(plusUn()); //1
alert(plusUn()); //2
```

C’est là tout l’intérêt et la magie des closures : si une fonction interne parvient à exister plus longtemps que la fonction parente dans laquelle elle a été définie, alors les variables de cette fonction parente vont continuer d’exister au travers de la fonction interne qui sert de référence à celles-ci. 

# Gestion du délai avec `setTimeout()` et `setInterval()`

## La méthode `setTimeout()`

Cette méthode permet d'exécuter une fonction ou un bloc de code après une certaine période définie. 

```js
function message(){
    setTimeout(alert, 2000, 'Message d\'alerte après 1 secondes');
}
```

La méthode `clearTimeout()` permet d'annuler ou de supprimer le délai défini. 

```js
function message(){
    let timeOut = setTimeout(alert, 2000, 'Message d\'alerte après 1 secondes');
}
function stopDelai(){
    cleartTimeout(timeOut);
}
```

## La méthode setInterval()

Il s'agit d'une méthode qui exécute une fonction en l'appelant en boucle selon un intervalle de temps fixe entre chaque appel. Cela peut être utile sur un site comme pour indiquer l'heure qui se met automatique à jour toutes les secondes. 

```js
function afficheHeure(){
    setInterval(function(){
        let d = new Date();
        p.innerHTML = d.toLocaleTimeString();
    }, 1000)
}
```

La méthode `clearInterval()` permet d'annuler ou de supprimer le délai défini. 

```js
function timer(){
    intervalId = setInterval(function(){
        p1.textContent = heu + ' : ' + min + ' : ' + sec + ' . ' + dec;
        dec += 1;
        if(dec >= 10){dec = 0; sec += 1;}
        if(sec >= 60){sec = 0; min += 1;}
        if(min >= 60){min = 0; heu += 1;}
    }, 100)
}
function stopTimer(){
    clearInterval(intervalId);
}
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)