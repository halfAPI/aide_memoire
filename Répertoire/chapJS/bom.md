# Manipulation du BOM en JS

Voici les points abordés dans cette section :

* API, BOM et interface window

* Interface, objet Navigator et géolocalisation

* Interface et objet History

* Interface et objet Location

* Interface et objet Screen

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# API, BOM et interface window

## Introduction et présentation des API

Une API (Interface de Programmation Applicative) est une interface, c'est-à-dire un ensemble de codes grâce à laquelle un logiciel fournit des services à des clients. 

L'intérêt et le principe d'une API est de faire des opérations complexes en cachant la complexité. Voyons une API comme une commande de voiture. Quand je mets le clignotant, je ne me préoccupe pas de savoir comment la mécanique de la voiture fonctionne. C'est pareil pour une API, j'utilise les commandes pour faire telles ou telles choses. 

Il existe 2 grandes catégories d'API : 

* Les API intégrées aux navigateurs web comme l'`API DOM`, l'`API Geolocation` ou encore l'`API Canvas`.

* Les API externes proposées par certains logiciels ou sites comme l'`API Google Map`, l'`API Twitter` ou bien encore l'`API YouTube`.

## Introduction au Browser Object Model et à l'objet Window

Le BOM est une sorte de super API elle-même composée de plusieurs API. A la base du BOM, on a l'interface Window qui représente une fenêtre de navigation contenant une page ou un document. 

Dans un navigateur, chaque onglet contient son propre objet Window. Les objets suivant appartiennent au BOM et sont des enfants de Window : 

* L'objet Navigator : représente l'état et l'identité du navigateur

* L'objet History : permet de manipuler l'historique de navigation du navigateur

* L'objet Location : fournit des infos relatives à l'URL de la page

* L'objet Screen : permet d'examiner les propriétés de l'écran

* L'objet Document et le [DOM](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/chapJS/dom.md)

## Propriétés, méthodes et fonctionnement de l'objet Window

### Les propriétés

Il existe 4 propriétés renvoyant des infos sur la hauteur et la largeur de la fenêtre. 

- `outerHeight` et `outerWidth` : retournent la hauteur et la largeur de la fenêtre du navigateur en comptant les options du navigateur.

- `innerHeight` et `innerWidth` : retournent la hauteur et la largeur de la partie visible de la fenêtre de navigation.

### Les méthodes

- La méthode `open` va permettre d'ouvrir une certaine ressource dans une fenêtre ou un onglet. Si on veut ouvrir une nouvelle fenêtre, il suffit d'ajouter la valeur `_blank`

```js
let b1 = document.getElementById('b1');
let winSize = 'width=500, height=500');

b1.addEventListener('click, openWindow);

function openWindow(){
    fenetre = window.open('https://www.google.be/', '', winSize)
    //Permet d'ouvrir une fenêtre
}
```

- Les méthodes `resizeBy()` et `resizeTo()` sont deux méthodes permettant de redimensionner en ajoutant ou supprimant un nombre de pixel (`resizeBy()`) ou bien de passer une nouvelle taille (`resizeTo()`).

- Les méthodes `moveBy()` et `moveTo` sont des méthodes permettant de déplacer la fenêtre sur un espace de travail qui déplace soit la fenêtre à sa position de départ (`moveBy()`), soit la déplace par rapport à l'angle supérieur gauche de l'espace de travail (`moveTo`).

- Les méthodes `scrollBy()` et `scrollTo()` permettent d'appliquer un défilement dans le document de la fenêtre ouverte.

- La méthode `close()` permettant de fermer la fenêtre.

```js
function openWindow(){
    //On recupère l'information renvoyée par open() dans une variable "fenetre"
    fenetre = window.open('', '', winSize);
}
function resizeWindowBy(){
    fenetre.resizeBy(200, 100);
}
function resizeWindowTo(){
    fenetre.resizeTo(960, 720);
}
function moveWindowBy(){
    fenetre.moveBy(100, 100);//Déplace la fenêtre 100px à droite et 100px en bas
}
function moveWindowTo(){
    fenetre.moveTo(0, 0);//Place la fenêtre contre le bord supérieur gauche
}
function scrollWindowBy(){
    fenetre.scrollBy(0, 200);//Défile de 200px vers le bas
}
function scrollWindowTo(){
    fenetre.scrollTo(0, 0);//Remonte en haut de la page
}
function closeWindow(){
    fenetre.close();
}
```

Enfin, on peut également ouvrir des boite de dialogues. Il existe 3 méthodes.

- `alert()` : permet d'afficher une boite d'alerte

- `prompt()` : permet d'afficher une boite de dialogue permettant à l'user d'envoyer du texte

- `confirm()` : permet d'ouvrir une boite avec un message facultatif mais surtout avec 2 boutons : Ok et Annuler.

# Interface, objet Navigator et géolocalisation

L'objet Navigator permet de donner des informations sur le navigateur des visiteurs (langue, etc). **ATTENTION** ne jamais faire confiance à 100% aux users!

## Les propriétés de l'objet Navigator

Les propriétés les plus intéressantes sont les suivantes : 

* `language` : retourne la langue définie dans le navigateur

* `geolocation` : permet de définir la localisation

* `cookieEnabled` : détermine si les cookies sont autorisés ou non

* `platform` : retourne la plateforme utilisée

* `appName` : retourne le nom du navigateur

* `appCodeName` : retourne le nom du code du navigateur

* `appVersion` : retourne la version du navigateur

```js
document.getElementById('p1').innerHTML =
    'Langue du navigateur : ' + navigator.language  +
    '<br>Cookies autorisés : ' + navigator.cookieEnabled +
    '<br>Plateforme utilisée : ' + navigator.platform; 
```

## L'interface et l'objet Geolocation

Cet interface permet de géolocalise d'un appareil (que ce soit pc, tablette ou gsm). L'interface `Geolocation` n'implémente et n'hérite d'aucune propriété. Par contre, elle met 3 méthodes à disposition qui ne sont disponibles que dans des contextes sécurisés (HTTPS) : 

* la méthode `getCurrentPosition()` : permet d'obtenir la position actuelle en retournant un objet Position. L'interface Position ne possède aucune méthode mais implémente deux propriétés : 

    * La propriété `timestamp` : représente le moment où la position de l'appareil a été récupérer

    * La propriété `coords` : retourne un objet Coordinates avec les coordonnées de position de l'appareil. L'interface Coordinates ne possède pas de méthodes mais certaines propriétés :

        * `latitude` : la latitude de l'appareil
        * `longitude` : la longitude de l'appareil
        * `altitude` : l'altitude de l'appareil
        * `accuracy` : degré de précision des deux premières propriétés
        * `altitudeAccuracy` : degré de précision de la valeur de la propriété `altitude`
        * `heading` : direction dans laquelle l'appareil se déplace
        * `speed` : vitesse dans laquelle l'appareil se déplace

* la méthode `watchPosition()` : permet de définir une fonction de retour qui sera appelée automatiquement dès que la position de l'appareil change

* la méthode `clearWatch()` : permet de supprimer la fonction de retour passée à `watchPosition`

# Interface et objet History

Cet objet permet de manipuler l'historique du navigateur des visiteurs pour la session courante. 

Voici les différentes propriétés et méthodes disponible dans cet objet :

- La propriété `length` : retourne le nombre d'éléments dans l'historique

- La méthode `go()` : permet de charger une page depuis l'historique de session. 

- La méthode `back()` : permet de charger la page précédente dans l'historique de session

- La méthode `forward()` : permet de charger la page suivante dans l'historique de session

```js
//On définit des gestionnaires d'évènement click pour des boutons
b1.addEventListener('click', hgo);
b2.addEventListener('click', hback);
b3.addEventListener('click', hforward);

function hgo(){
    history.go(-2);
}
function hback(){
    history.back();
}
function hforward(){
    history.forward();
}
```

# Interface et objet Location

Cet interface fournnit des informations relatives à l'URL d'une page : 

Voici les différentes propriétés et méthodes disponible dans cet objet :

- Les propriétés :

    * `hash` : retourne la partie ancre d'une URL
    * `search` : retourne la partie recherche d'une URL
    * `pathname` : retourne le chemin de l'URL
    * `href` : : retourne l'URL complète
    * `hostname` : retourne le nom d'hôte
    * `port` : retourne le port de l'URL
    * `protocole` : retourne le protocole de l'URL
    * `host` : retourne le nom d'hôte et le port relatif à l'URL
    * `origin` : retourne le nom de l'hôte, le port et le protocole de l'URL

- Les méthodes : 
    * `assign()` : charge une ressource à partir d'une URL passée en argument
    * `replace()` : remplace le document actuel par un autre disponible à l'URL fournie en argument 
    * `reload()` : recharge le document actuel

```js
//On définit des gestionnaires d'évènement click pour des boutons
b1.addEventListener('click', recharge);
b2.addEventListener('click', assigne);
b3.addEventListener('click', remplace);

function recharge(){
    location.reload();
}
function assigne(){
    location.assign('https://github.com/CalcagnoLoic/aide_memoire');
}
function remplace(){
    location.replace('https://github.com/CalcagnoLoic/aide_memoire');
}
```

# Interface et objet Screen

Cet objet donne accès aux informations concernant l'écran des visiteurs. 

Screen possède une dizaine de propriétés dont 6 sont bien supportées par les navigateurs et particulièrement intéressantes : 

- `width` : retourne la largeur totale de l'écran

- `availWidth` : retourne la largeur de l'écran moins celle de la barre de tâches

- `heigth` : retourne la hauteur totale de l'écran

- `availHeight` : retourne la hauteur de l'écran moins celle de la barre de tâches

- `colorDepth` : retourne la profondeur de la palette de couleur de l'écran en bits

- `pixelDepth` : retourne la résolution de l'écran en bits par pixel

Il existe 2 méthodes mais elles sont aujourd'hui dépréciées et non utilisées. 

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)