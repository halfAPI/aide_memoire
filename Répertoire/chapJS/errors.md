# La gestion des erreurs en JS

Voici les points abordés dans cette section : 

* La gestion des erreurs

* Le mode strict 


[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# La gestion des erreurs

Une erreur est un comportement inattendu et non voulu du script. Il peut y avoir différentes origines à une erreur : 

- Une erreur de syntaxe au sein même du code

- Une erreur de serveur où celui-ci ne peut fournir les fichiers demandés

- Une erreur de navigateur

- Valeur non valide envoyée par un utilisateur

Il existe des méthode permettant de gérer les potentielles erreurs et indiquer quoi faire en cas d'erreur. 

## Gérer une erreur avec les blocs `try ... catch`

Nous allons placer le code à tester (celui qui peut potentiellement générer une erreur) au sein de notre bloc `try` puis allons capturer l’erreur potentielle dans le bloc `catch` et indiquer comment la gérer. 

```js
try{
    alert('Bonjour');  
}catch(err){
    alert('Une erreur a été rencontrée');
}
```

Si jamais l'alerte ne se lance pas à cause d'une erreur, le bloc `catch` s'exécutera.

## L'instruction `throw`

Parfois, on sait à l'avance qu'une erreur sera générée. Imaginons, on intègre une calculatrice à notre site. Si un utilisateur tente de diviser un nombre par 0, on sait qu'on aura une erreur. Dans ce cas, on lance en amont un `throw`. 

Il s'agit en gros d'une exception. C'est une erreur qu'on va déclencher à la place du JS afin de pouvoir la gérer plus facilement. Cela correspond en quelque sorte à la programmation défensive des fonctions dans R.

Pour définir une exception, on déclare via le constructeur `new Error()`

```js
function div(){
    let x = prompt('Entrez un premier nombre (numérateur)');
    let y = prompt('Entrez un deuxième nombre (dénominateur)');
    
    if(isNaN(x) || isNaN(y) || x == '' || y == ''){
        throw new Error('Merci de rentrer deux nombres');
    }else if(y == 0){
         throw new Error('Division par 0 impossible')
    }else{
        alert(x / y);
    }
}

try{
    div();
}catch(err){
    alert(err.message);
}
```

## Le bloc `finally`

Il s'agit d'un bloc optionnel placé après un `try...catch`. Ce bloc permet d'exécuter du code dans tout les cas, qu'une erreur ou une exception se déclenche ou non. 

Le bloc `finally` va être particulièrement utile dans le cas où on veut absolument effectuer certaines opérations même si une exception est levée comme par exemple récupérer une certaine valeur

```js
function div(){
    let x = prompt('Entrez un premier nombre (numérateur)');
    let y = prompt('Entrez un deuxième nombre (dénominateur)');
    
    if(isNaN(x) || isNaN(y) || x == '' || y == ''){
        throw new Error('Merci de rentrer deux nombres');
    }else if(y == 0){
         throw new Error('Division par 0 impossible')
    }else{
        alert(x / y);
    }
}

try{
    div();
}catch(err){
    alert(err.message);
}finally{
    alert('Ce message s\'affichera quoiqu\'il arrive');
}
```

# Le mode strict 

## Présentation du mode strict

Le mode strict de JavaScript est, comme son nom l’indique, un mode qui va contenir une sémantique légèrement différente et plus stricte par rapport au JavaScript « classique ».

Le mode script laisse passer moins d'erreurs (comme les erreurs de syntaxes) que JavaScript classe laisse passer.

## Activer et utiliser le mode strict

Pour active le mode strict sur un script, il suffit d'utiliser `use strict` en début de script ou à un endroit bien précis. 

```js
use strict 
// du code 

//=====================================================OU

let variable = 5 

// du code

function demo(){
    use strict;
    let a = b;
    //du code
}
```

## Les différences entre le mode script et le JavaScript en détail

### Déclarer une variable

- JS classique : Si on oublie `let` ou `var`, aucune erreur n'est levée. La variable deviendra globale. 

- JS strict : Si on oublie, une erreur est levée et aucune variable globale n'est créée.

### Affecter une valeur à une variable ou une propriété non accessible en écriture

- JS classique : Aucune erreur n'est levée. L'affectation est juste ignorée.

- JS strict : Une erreur est levée.

### Tenter de supprimer une propriété non supprimable

- JS classique : Si on tente de supprimer la propriété `prototype` d'un objet, rien ne se passe.

- JS strict : Une erreur est levée.

### Déclarer plusieurs paramètres de même nom dans une fonction

- JS classique : Seul le dernier argument placé à la place des paramètres de même nom sera considéré par JS.

- JS strict : Une erreur est levée.

### Utiliser des notations octales

- JS classique : Si on tente d'écrire de façon octale (`01`), ça passera mais ce n'est pas vraiment souhaitable.

- JS strict : Une erreur est levée.

### Définir des propriétés sur des valeurs primitives

- JS classique : Les définitions seront ignorées.

- JS strict : Une erreur est levée.

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)