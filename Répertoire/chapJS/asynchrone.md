# L'asynchrone en JS

Voici les points abordés dans cette section : 

* Introduction à l'asynchrone

* Les promesses 

* Présentation d'Ajax et création de requête

* Présentation et utilisation de l'API Fetch

* Utilisation de `async` et `await`

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Introduction à l'asynchrone

En informatique, on dit que deux opérations sont synchrones lorsque la seconde attend que la première ait fini son travail pour démarrer. Ce qu’il faut retenir de cette définition est le concept de dépendance : le début de l’opération suivante dépend de la complétude de l’opération précédente.

Au contraire, deux opérations sont qualifiées d’asynchrones en informatique lorsqu’elles sont indépendantes c’est-à-dire lorsque la deuxième opération n’a pas besoin d’attendre que la première se termine pour démarrer. 

Par défaut, Javascript est un langage synchrone et bloquant. Cela pose rapidement un problème dans un contexte web. Si une de nos boucles prend beaucoup de temps à s'exécuter, la suite du script est bloqué. Pour éviter ce genre de problème, on utilise de la programmation asynchrone. 

L’idée principale de l’asynchrone est que le reste du script puisse continuer à s’exécuter pendant qu’une certaine opération plus longue ou demandant une réponse / valeur est en cours. Cela permet un affichage plus rapide des pages et en une meilleure expérience utilisateur. 

Le premier outil utilisé en JavaScript pour générer du code asynchrone a été les fonctions de rappel. En effet, une fonction de rappel ou « callback » en anglais est une fonction qui va pouvoir être rappelée (« called back ») à un certain moment et / ou si certaines conditions sont réunies.

L’idée ici est de passer une fonction de rappel en argument d’une autre fonction. Cette fonction de rappel va être rappelée à un certain moment par la fonction principale et pouvoir s’exécuter, sans forcément bloquer le reste du script tant que ce n’est pas le cas. 

En 2015, cependant, le JavaScript a intégré un nouvel outil dont l’unique but est la génération et la gestion du code asynchrone : les promesses avec l’objet constructeur Promise. C’est à ce jour l’outil le plus récent et le plus puissant fourni par le JavaScript nous permettant d’utiliser l’asynchrone dans nos scripts (avec la syntaxe async et await basée sur les promesses et que nous verrons en fin de partie).

Une « promesse » est donc un objet représentant l’état d’une opération asynchrone.Aujourd’hui de plus en plus d’API utilisent les promesses pour gérer les opérations asynchrones.  

# Les promesses 

Une promesse en JavaScript est un objet qui représente l’état d’une opération asynchrone. Une opération asynchrone peut être dans l’un des états suivants :

* Opération en cours (non terminée) ;
* Opération terminée avec succès (promesse résolue) ;
* Opération terminée ou plus exactement stoppée après un échec (promesse rejetée).

Voici un exemple de code avec une fonction asynchrone et une promesse : 

```js
function loadScript(src){
    return new Promise((resolve, reject) => {
        let script = document.createElement('script');
        script.src = src;
        document.head.append(script);
        script.onload = () => resolve('Fichier ' + src + ' bien chargé');
        script.onerror = () => reject(new Error('Echec de chargement de ' + src));
    });
}
```

## Exploiter le résultat d'une promesse avec les méthodes `then()` et `catch()`

Pour obtenir la promesse, on utilise en général la méthode `then()`. Cette méthode permet d'enregistrer deux fonctions de rappel que l'on passe en arguments. Une première que sera appelée si la promesse est résolue et une qui sera appelée si la promesse est rompue.

```js
function loadScript(src){
    return new Promise((resolve, reject) => {
        let script = document.createElement('script');
        script.src = src;
        document.head.append(script);
        script.onload = () => resolve('Fichier ' + src + ' bien chargé');
        script.onerror = () => reject(new Error('Echec de chargement de ' + src));
    });
}

const promesse1 = loadScript('boucle.js');
const promesse2 = loadScript('script2.js');

promesse1.then(
    function(result){alert(result);},
    function(error){alert(error);}
);

promesse2.then(result => alert(result), error => alert(error));
```

Il faut également préciser que l'on peut chainer les promesses : 

```js
function loadScript(src){
    return new Promise((resolve, reject) => {
        let script = document.createElement('script');
        script.src = src;
        document.head.append(script);
        script.onload = () => resolve('Fichier ' + src + ' bien chargé');
        script.onerror = () => reject(new Error('Echec de chargement de ' + src));
    });
}

loadScript('boucle.js')
.then(result => loadScript('script2.js', result))
.then(result2 => loadScript('script3.js', result2))
.catch(alert);
```


# Présentation d'Ajax et création de requête

AJAX () est la première façon de faire des requête asynchrone. C'est une méthode **que l'on utilise de moins en moins**. Pour créer une requête AJAX, on passe par 4 étapes :

* On crée un objet `XMLHttpRequest` ;

* On initialise la requête

* On envoie la requête 

* On crée des gestionnaires d'événements pour prendre en charge la réponse

Voici un exemple de requête : 

```js
let xhr = new XMLHttpRequest();

xhr.open("GET", '/url de l\'API');

xhr.responseType = "json";

xhr.send()
```

Je ne détaillerai pas plus cette section sur AJAX mais voici une adresse pour avoir plus d'infos sur cette technique : [Requête Ajax](https://www.pierre-giraud.com/javascript-apprendre-coder-cours/ajax-xmlhttprequest/)

# Présentation et utilisation de l'API Fetch

Il s'agit d'une nouvelle façon d'effectuer des requêtes HTTP au moyen de l'API Fetch et la méthode fetch(). Cette méthode est au coeur de l'API fetch qui permet l'échange de données avec le serveur de façon asynchrone. 

Cette méthode prend un unique argument : le chemin de l'API qu'on souhaite récupérer. 

La méthode fetch permet de renvoyer une promesse. La promesse sera rompue si la requête HTTP n'a pu être effectuée. Mais ce n'est pas parce que la promesse est rompue qu'elle est considérée comme anormale. On va pour vérifier le statut HTTP au moyen de deux propriétés :

- `ok` : renvoie le booléen true si le statut de la réponse est comprise entre 200 et 299. Sinon false.

- `status` : renvoie le statut code HTTP (200, 301, 404, 500)

Pour récupérer le corps de la réponse, on peut utiliser différente méthode en fonction du format qui nous intéresse : 

- `text()` : retourne la réponse sous forme de chaine de caractère

- `json()` : retourne la réponse sous forme d'objet JSON

- `formData()` : retourne la réponse sous forme d'objet FormData

- `arrayBuffer()` : retourne la réponse sous forme d'ibjet ArrayBuffer

- `blob()` : retourne la réponse sous forme d'objet Blob

```js
fetch("api")
    .then(response => response.json())
    .then(response => alert(JSON.stringify(response)))
    .catch(error => alert("Erreur : " + error))
```

Voici un lien renvoyant vers l'utilisation plus avancée des [requêtes avec l'API fetch](https://www.digitalocean.com/community/tutorials/how-to-use-the-javascript-fetch-api-to-get-data-fr).

# Utilisation de `async` et `await`

La déclaration `async function` et le mot clé `await` sont des « sucres syntaxiques », c’est-à-dire qu’ils n’ajoutent pas de nouvelles fonctionnalités en soi au langage mais permettent de créer et d’utiliser des promesses avec un code plus intuitif et qui ressemble davantage à la syntaxe classique du JavaScript à laquelle nous sommes habitués.

Ces mots clés sont apparus avec la version 2017 du JavaScript et sont très prisés et utilisés par les API modernes. 

- `async` : On met ce mot clé devant une déclaration de fonction afin de transformer la fonction en fonction asynchrone. 

- `await` : Ce mot clé permet d'interrompe l'exécution d'une fonction asynchrone tant qu'une promesse n'est pas résolue ou rejetée. 

Voici un exemple d'écriture de requête : 

```js
function loadScript(src){
    return new Promise((resolve, reject) => {
        let script = document.createElement('script');
        script.src = src;
        document.head.append(script);
        script.onload = () => resolve('Fichier ' + src + ' bien chargé');
        script.onerror = () => reject(new Error('Echec de chargement de ' + src));
    });
}

async function test() {
    const test1 = await loadScript('boucle.js');
    alert(test1);
    const test2 = await loadScript('blblbl.js');
    alert(test2);
    const test3 = await loadScript('cdccdc.js');
    alert(test3);
}

test();
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)