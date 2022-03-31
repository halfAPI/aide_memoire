# Les modules javascript

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

En programmation, un module est un bloc cohérent de code. C'est-à-dire un bloc de code contenant ses propres fonctionnalités fonctionnant ensemble et qui est séparé du reste du code. 

L’avantage principal des modules est une meilleure séparation qui résulte dans une meilleure maintenabilité et lisibilité du code.

Depuis 2015, cependant, les modules font partie des spécifications officielles du langage et possèdent donc des fonctionnalités définies par le JavaScript, ce qui rend leur utilisation beaucoup plus simple et plus puissante. 

# Définition et création de modules

Pour utiliser correctement des modules, on doit utiliser les déclarations `import` et `export`. Le concept du module est qu'on peut exporter des modules entiers ou des éléments de certains modules puis les importer dans d'autres scripts. 

Les éléments qui peuvent être exportés sont précédés de la mention `export`. Pour importer dans un script, on utilise la mention `import` suivi du mot clé `from` avec le chemin relatif du fichier.

Créons un module `module.js` : 

```js
/*
 *====================
 *     module.js
 *====================
 */

export function disBonjour(prenom) {
    alert('bonjour' + prenom);
}

function nomComplet(prenom, nom) {
    alert(prenom + nom);
}
```

Maintenant on va importer la fonction dans un autre script `cours.js` :

```js
/*
 *====================
 *      cours.js
 *====================
 */

import {disBonjour} from './module.js'

disBonjour("loic")
```

**Même si les deux scripts sotn dans le même dossier, il faut préciser `./` pour que l'import se fasse correctement.**

De plus, dans la structure `head` du html, il faudra préciser qu'on importe un module : 

```html
<script type="module" src="cours.js" async></script>
```

**Si vous voulez tester ceci en local, il est nécessaire de télécharge un serveur sur la machine (WAMP ou MAMP ou XAMP).**

# Les fonctionnalités principales des modules 

## Le mode strict 

Les modules utilisent par défaut le mode strict. 

## La portée des modules

Les modules possèdent leur propre espace global de portée. Cela signifie que les variables et fonctions ne seront par défaut pas accessibles dans les autres scripts. Pour y avoir accès, il faut passer par l'export/import. 

## L'évaluation des modules

Le code des modules n'est évalué qu'une seule fois. Si le code est importé plusieurs fois, il ne sera exécuté que dans un fichier et ensuite le résultat sera exporté aux autres scripts. 

## Les modules utilisent `defer`

Les modules utilisent par défaut `defer` quand ils sont chargés dans le navigateur. Cela signifique que : 

* Les modules importés avec `script type="module" src="..."` ne bloquent pas l'analyse du code HTML

* Les modules attendent que le document HMLT soit complètement chargé pour s'exécuter

* L'ordre des scripts est respecté : le premier module inséré s'exécutera en premier, etc ...

## Utilisation d'`async` dans les modules

On peut ajouter `async` pour que les modules s'exécutent de façon asynchrone. Cela peut être utile dans le cas où l’on souhaite importer des modules qui sont indépendants du reste de la page (modules de statistique, de publicité, etc.). 

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)