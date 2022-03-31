# Le stockage de données dans le navigateur en JS

Voici les différents points abordés dans cette section : 

* Les cookies

* L'API ``Web Storage``

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Les cookies

Un cookie est un petit fichier qui ne contient généralement qu’une seule donnée et qui va être stocké directement dans le navigateur d’un utilisateur.

Le plus souvent, les cookies sont mis en place (créés) côté serveur et vont être envoyés avec une page lorsque l’utilisateur demande à y accéder. 

Les cookies sont très pratiques car ils permettent de conserver des informations envoyées par l’utilisateur et donc de pouvoir s’en resservir et cela de manière relativement simple.

## Obtenir la liste des cookies et créer un cookie

On utilise le descripteur d'accesseur `document.cookie`. Un descripteur d'accesseur est une propriété décrite par une paire d'accesseeur/mutateur (getter/setter) qui sont des fonctions. 

```js
document.cookie = 'user=Loic';
```

## Les options des cookies

### La portée des cookies

On peut préciser un répertoire dans lequel le cookie est disponible au moyen de l'option `path`. Il faut fournir un chemin absolu. 

```js
document.cookie = 'user=Loic ; path=/';
```

L'option `domain` permet de préciser le domaine sur lequel le cookie doit être accessible. Cette option est bien évidemment limitée à l'ensemble du domaine principal et de ses sous-domaines pour des raisons de sécurité. 

Par exemple, si je crée un cookie pour la page `loic-calcagno.com` sans préciser de domaine, il sera présent dans le domaine mais pas le sous-domaine, ni dans un autre domaine bien évidemment. 

```js
document.cookie = 'user=Loic; path=/; domain=loic-calcagno.com';
```

### L'âge maximal et la date d'expiration des cookies

Par défaut, un cookie est supprimé quand le navigateur est fermé. 

L'option `expire` va permettre d'indiquer une date d'expiration afin que le cookie soit conservé. Si je veux un cookie qui dure 24h :

```js
let date = new Date(Date.now() + 86400000) //= 1jour
date = date.toUTCString();

document.cookie = 'user=Loic; path=/; domain=loic-calcagno.com; expires=' + date;
```

Une autre alternative est d'utiliser l'option `max-age`

```js
document.cookie = 'user=Loic; path=/; domain=loic-calcagno.com; max-age = 86400';
```

### Les cookies et la sécurité

Il existe 2 options :

* `secure` : cette option permet d'indique qu'un cookie doit uniquement être envoyé via HTTPS et non via HTTP

```js
document.cookie = 'user=Loic; path=/; domain=loic-calcagno.com; secure';
```

* `samesite` : empêche le navigateur d'envoyer un cookie lors d'une requête cross-site. Cette option offre une bonne protection contre les [attaques de type XSRF](https://fr.wikipedia.org/wiki/Cross-site_request_forgery). 

    * `samesite="strict"` : indique qu'un cookie ne doit jamais être envoyé si l'utilisateur arrive sur le site depuis un autre site

    *`samesite="lax"` : possède les mêmes caractéristiques que la valeur strict à la différence que les cookies provenant de requêtes GET seront envoyées. 

### L'option `HttpOnly`

Cette option interdit tout simplement tout accès au cookie au JavaScript. Nous ne pouvons pas voir ce cookie ni le manipuler avec `document.cookie`.

Cette option est utilisée pour se prémunir d’attaques XSS (cross-site scripting), qui sont des attaques qui reposent sur l’injection de code JavaScript dans une page avec l’intention que l’utilisateur ou que le site lui-même exécute ce code qui va pouvoir récupérer des informations ou créer des dégâts sur le site. 

### Modifier ou supprimer un cookie en JS

Pour modifier un cookie, il suffit de le réécrire avec le même nom et en changeant les autres informations.

Notez qu’on ne va pas pouvoir changer le nom d’un cookie : si l’on change de nom, cela sera considéré comme un autre cookie et ça n’effacera pas le premier.

Pour supprimer un cookie, la méthode la plus simple est de le réécrire sans valeur et en précisant cette fois-ci une date d’expiration passée

# L'API ``Web Storage``

L’API Web Storage permet de stocker des données sous forme de paires clefs/valeurs qui doivent obligatoirement être des chaines de caractères dans le navigateur de vos visiteurs. 

Pour stocker des données, on utilise les propriétés `localStorage` et `sessionStorage`. La différence entre ces 2 propriétés réside dans le fait que `sessionStorage` stocke les données après un refresh de la page alors que `localStorage` garde les données même après que le visiteur ait quitté son navigateur.

L’API Web Storage va nous permettre de stocker des données plus simplement que les cookies et applique la politique de même origine, ce qui limite les problèmes de sécurité.

## Les propriétés et méthodes de `localStorage` et de `sessionStorage`

Voici la liste des propriétés et méthodes : 

- `setItem()` : permet de stocker une paire clé/valeur

- `getItem()` : permet d'obtenir une valeur liée à une clé

- `removeItem()` : permet de supprimer une paire clé/valeur

- `clear()` : permet de supprimer tous les objets de stockage

- `key()` : permet d'obtenir une clé située à une certaine position

- `length` : permet d'obtenir le nombre de données stockées

## Exemple pratique de l'API Web Storage

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Cours JavaScript</title>
        <meta charset='utf-8'>
        <link rel='stylesheet' href='cours.css'>
        <script src='cours.js' async></script>
    </head>
    <body>
        <form>
            <div>
                <label for='bgtheme'>Choisissez un thème (hexa) :</label>
                <input class='text' id='bgtheme' value='FAFAFA'
                       pattern='[a-fA-F0-9]{6}'>
            </div>
        </form>
    </body>
</html>
```

```js
let htmlElt = document.querySelector('html');
let bgColor = document.getElementById('bgtheme');

//on vérifie si l'objet de stockage est présent ou non
if(localStorage.getItem('bgtheme')){
    updateBg();
}else{
    setBg();
}

//Si aucun objet de stockage => création de l'objet
function setBg(){
    localStorage.setItem('bgtheme', bgColor.value);
    updateBg();
}

//Si objet => on récupère la dernière valeur stockée dans l'objet de stockage et mettre à jour
function updateBg(){
    let bg = localStorage.getItem('bgtheme');
    htmlElt.style.backgroundColor = '#' + bg;
    bgColor.value = bg;
}

bgColor.addEventListener('change', setBg);
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)