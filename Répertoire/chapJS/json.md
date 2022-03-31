# JSON

Voici les points abordés dans cette section : 

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)

Le JSON est un format d'échange de données léger et donc performant. JSON est une syntaxe pour sérialiser (mettre des données en série) des objets, des tableaux, des nombres, des chaînes de caractères, des booléens et des valeurs null.

JSON est construit par rapport à 2 structures : 

* Une collection de paires nom/valeur

* Une liste ordonnée de valeurs

Ce sont donc 2 structures que l'on retrouve partout dans les langages de programmation.

De nombreuses personnes pensent encore que JSON fait partie du langage JavaScript et n’est qu’un objet JavaScript. **C’est faux** : JSON est un format de texte indépendant de tout langage.

Il existe 2 méthodes en JSON :

- La méthode `parse()` : Analyse une chaine de caractères JSON et construit la valeur JS ou l'objet d'écrit par cette chaine. 

- La méthode `stringify()` : Convertir une valeur JS en chaine JSON. 

```js
     HTML JS 

    Result
    Skip Results Iframe

EDIT ON

//Objet JavaScript
let utilisateur = {
    "prenom": "Loic",
    "nom": "Calcagno",
    "adresse": {
        "ville": "La Hestre",
        "cp": 7170,
        "pays": "Belgique"
    },
    "mails": [
        "loic.calcagno@hotmail.com",
        "calcagnoloic93@gmail.com"
    ]
  };

//Conversion en chaine JSON
let json = JSON.stringify(utilisateur);
```

[Retour vers les chapitres JS](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/js.md)
