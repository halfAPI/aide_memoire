# Manipulation du DOM en JS

Voici les différents points abordés dans cette section : 

* Présentation du DOM HTML

* Accéder à des éléments d'un document et les modifier 

* Naviguer ou se déplacer dans le DOM

* Ajouter, modifier ou supprimer des éléments du DOM

* Manipuler les attributs via le DOM

* Gestion d'évènement et la méthode `addEventListener`

* Empêcher la propagation d'un évènement et annuler son comportement par défaut

Vous pouvez retrouver sur ce lien une liste non exhaustive des [méthodes du DOM](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/dom_meth.md)

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

# Présentation du DOM HTML

Le DOM est une représentation structurée du document sous forme « d’arbre » crée automatiquement par le navigateur. Chaque branche de cet arbre se termine par ce qu’on appelle un nœud qui va contenir des objets. On va finalement pouvoir utiliser ces objets, leurs propriétés et leurs méthodes en JavaScript. 

![Représentation du DOM](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSJGKDiywikJgw7KHnJEOM_p6xYIzIOFHAOPA&usqp=CAU)

# Accéder à des éléments d'un document et les modifier 

## Accéder à un élément à partir de son sélecteur CSS associé

La façon la plus simple d'accéder à un élément est de le faire en ciblant les sélecteurs CSS. Il existe deux méthodes pour faire cela : `querySelector()` et `querySelectorAll()`

```js
//Sélectionne tous les paragraphes du document
document.querySelectorAll('p');
```

## Accéder à un élément en fonction de la valeur de son attribut id

Pour atteindre un élément du fichier html possédant un id, on peut y accéder au moyen de `getElementById()`.

C'est un moyen simple d'accéder à un élément particulier puisque les id sont uniques dans un document. 

```js
//sélectionne un élément par l'id et modifie la couleur du texte
document.getElementById('p1').style.color = 'blue';
```

## Accéder à un élément en fonction de la valeur de son attribut `class`

Pour atteindre un élément du fichier html possédant une classe, on peut y accéder au moyen de `getElementsByClassName()`.

```js
//Sélectionne les éléments avec une class = 'bleu'
document.getElementsByClassName('bleu');
```

### Accéder à un élément en fonction de son identité

Pour atteindre un élément en fonction de son nom, il suffit d'utiliser `getElementsByTagName()`. 

Lorsqu’on utilise `getElementsByTagName()` avec un objet `Document`, la recherche se fait dans tout le document tandis que lorsqu’on utilise `getElementsByTagName()` avec un objet `Element`, la recherche se fera dans l’élément en question seulement.

### Accéder au contenu des éléments et le modifier

Jusqu'ici, on a pu accéder à des éléments précis du DOM. Mais on peut également vouloir modifier des éléments que l'on a ciblé. Pour cela, on peut utiliser les propriétés suivantes. 

* `innerHTML` : permet de récupérer ou de redéfinir la syntaxe HTML

* `outerHTML` : permet de récupérer ou de redéfinir la syntaxe HTML

* `textContent` : représente le contenu textuel d'un noeud

* `innerText` : représente le contenu textuel visible sur le document final d'un noeud

# Naviguer ou se déplacer dans le DOM

Par souci de compréhension et afin de bien saisir les exemples, rendez-vous [ici](https://www.pierre-giraud.com/javascript-apprendre-coder-cours/dom-navigation-deplacement/)

# Ajouter, modifier ou supprimer des éléments du DOM

Par souci de compréhension et afin de bien saisir les exemples, rendez-vous [ici](https://www.pierre-giraud.com/javascript-apprendre-coder-cours/dom-ajout-modification-suppression/)

# Manipuler les attributs via le DOM

Par souci de compréhension et afin de bien saisir les exemples, rendez-vous [ici](https://www.pierre-giraud.com/javascript-apprendre-coder-cours/dom-manipulation-attribut-style-css/)

# Gestion d'évènement et la méthode `addEventListener`

Un évènement est une action qui se produit et qui possède deux caractéristiques essentielles : 

* Une action que l'on peut 'écouter' : une action que l'on peut détecter

* Une action à laquelle on peut 'répondre' : attacher un code à cette action. 

Voici quelques exemples d'évènements : 

* Le chargement du document 

* Un clic sur un bouton

* Un survol d'un élément par une souris

Vous pouvez trouver sur ce site des exemples de définitions de gestionnairaires d'évènements [ici](https://www.pierre-giraud.com/javascript-apprendre-coder-cours/addeventlistener-gestion-evenement/)

Vous pouvez retrouver sur ce lien une liste non exhaustive des [méthodes du DOM](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/dom_meth.md)

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)