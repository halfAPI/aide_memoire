# Les concepts de l'algorithmie 

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

```
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

```
let size = 185;
let weight = 80;

if ((size >= 150) || (weight >= 45)) {
  console.log("You probably are an adult");
} else {
  console.log("You probably are a child");
}
```

### La boucle if .. else if .. else

Il s'agit d'une boucle qui teste une condition de départ. Si elle n'est pas respectée, la boucle continue vers les conditions intermédiaires.

```
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

```
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

```
for (let i = 1; i <= 100; i += 1) {
  console.log(i);
}
// Ce code imprime tout les chiffres entre 1 et 100
```

### La boucle do ... while

Il s'agit d'une boucle qui exécute une instruction jusqu'à ce que la condition de test ne soit plus vérifiée. 

```
let result = '';
let i = 0;

do {
  i = i + 1;
  result = result + i;
} while (i < 5);
```

### La boucle switch

L'instruction switch évalue une expression et, selon le résultat obtenu et le cas associé, exécute les instructions correspondantes.

```
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

```
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

```
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

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)