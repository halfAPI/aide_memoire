# Les méthodes de l'objet global `Array`

Voici les différentes méthodes que l'on peut appliquer à un objet de type `array`.

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

- `Array.concat()` : La méthode concat() est utilisée afin de fusionner deux ou plusieurs tableaux en les concaténant. Cette méthode ne modifie pas les tableaux existants, elle renvoie un nouveau tableau qui est le résultat de l'opération.

```
concat(valeur0, valeur1)

// exemple :
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);
```

- `Array.copyWithin()` : La méthode copyWithin() effectue une copie superficielle d'une partie d'un tableau sur ce même tableau et le renvoie, sans modifier sa taille.

```
arr.copyWithin(cible)
arr.copyWithin(cible, début)
arr.copyWithin(cible, début, fin)

// exemple :
const array1 = ['a', 'b', 'c', 'd', 'e'];
console.log(array1.copyWithin(0, 3, 4));
// expected output: Array ["d", "b", "c", "d", "e"]
```

- `Array.entries()` : La méthode entries() renvoie un nouvel objet qui contient le couple clef/valeur pour chaque éléments du tableau.
```
arr.entries()

// exemple :
const array1 = ['a', 'b', 'c'];
const iterator1 = array1.entries();
console.log(iterator1.next().value);
// expected output: Array [0, "a"]
```

- `Array.every()` : La méthode every() permet de tester si tous les éléments d'un tableau vérifient une condition donnée par une fonction en argument. Cette méthode renvoie un booléen pour le résultat du test.

```
arr.every(callback[, thisArg])

// exemple :
const isBelowThreshold = (currentValue) => currentValue < 40;
const array1 = [1, 30, 39, 29, 10, 13];
console.log(array1.every(isBelowThreshold));
// expected output: true
```

- `Array.fill()` : La méthode fill() remplit tous les éléments d'un tableau entre deux index avec une valeur statique. La valeur de l'index de fin n'est pas incluse. Cette méthode renvoie le tableau modifié.

```
arr.fill(valeur)
arr.fill(valeur, début)
arr.fill(valeur, début, fin)

// exemple :
const array1 = [1, 2, 3, 4];
// on remplit par '0' les positions 2 à 4
console.log(array1.fill(0, 2, 4));
// expected output: [1, 2, 0, 0]
```

- `Array.filter()` : La méthode filter() crée et retourne un nouveau tableau contenant tous les éléments du tableau d'origine qui remplissent une condition déterminée par la fonction callback.

```
arr.filter(callback);

// exemple :
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = words.filter(word => word.length > 6);
console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```

- `Array.find()` : La méthode find() renvoie la valeur du premier élément trouvé dans le tableau qui respecte la condition donnée par la fonction de test passée en argument. Sinon, la valeur undefined est renvoyée.

```
arr.find(callback(element[, index[, tableau]])[, thisArg])

// exemple :
const array1 = [5, 12, 8, 130, 44];
const found = array1.find(element => element > 10);
console.log(found);
// expected output: 12
```

- `Array.findIndex()` : La méthode findIndex() renvoie l'indice du premier élément du tableau qui satisfait une condition donnée par une fonction. Si la fonction renvoie faux pour tous les éléments du tableau, le résultat vaut -1.

```
arr.findIndex(callback(element[, index[, tableau]])[, thisArg])

// exemple :
const array1 = [5, 12, 8, 130, 44];
const isLargeNumber = (element) => element > 13;
console.log(array1.findIndex(isLargeNumber));
// expected output: 3
```

- `Array.flat()` : La méthode flat() permet de créer un nouveau tableau contenant les éléments des sous-tableaux du tableau passé en argument, qui sont concaténés récursivement pour atteindre une profondeur donnée.
```
var nouveauTableau = monTableau.flat([profondeur]);
```

- `Array.flatMap()` : La méthode flatMap() permet d'appliquer une fonction à chaque élément du tableau puis d'aplatir le résultat en un tableau. Cela correspond à l'enchaînement de `Array.prototype.map()` suivi de `Array.prototype.flat()` de profondeur 1. flatMap est plus efficace que la combinaison de ces deux opérations, souvent réalisées conjointement.

```
var new_array = arr.flatMap(function callback(currentValue[, index[, array]]) {
    // return element for new_array
}[, thisArg])

```

- `Array.forEach()` : La méthode forEach() permet d'exécuter une fonction donnée sur chaque élément du tableau.

```
arr.forEach(callback);

// exemple :
const array1 = ['a', 'b', 'c'];
array1.forEach(element => console.log(element));
// expected output: "a"
// expected output: "b"
// expected output: "c"
```

- `Array.concat()` : La méthode concat() est utilisée afin de fusionner deux ou plusieurs tableaux en les concaténant. Cette méthode ne modifie pas les tableaux existants, elle renvoie un nouveau tableau qui est le résultat de l'opération.

```

// exemple :
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);
```

- `Array.from()` : La méthode Array.from() permet de créer une nouvelle instance d'Array à partir d'un objet itérable ou semblable à un tableau.

```
console.log(Array.from('foo'));
// expected output: Array ["f", "o", "o"]

// exemple :
console.log(Array.from('foo'));
// expected output: Array ["f", "o", "o"]
```

- `Array.includes()` : La méthode includes() permet de déterminer si un tableau contient une valeur et renvoie true si c'est le cas, false sinon.

```
array.includes(élémentRecherché)
array.includes(élémentRecherché, indiceDépart)

// exemple :
const array1 = [1, 2, 3];
console.log(array1.includes(2));
// expected output: true
```

- `Array.indexOf()` : La méthode indexOf() renvoie le premier indice pour lequel on trouve un élément donné dans un tableau. Si l'élément cherché n'est pas présent dans le tableau, la méthode renverra -1.

```
arr.indexOf(élémentRecherché)
arr.indexOf(élémentRecherché, indiceDébut)

// exemple :
const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];
console.log(beasts.indexOf('bison'));
// expected output: 1
```

- `Array.isArray()` : La méthode Array.isArray() permet de déterminer si l'objet passé en argument est un objet Array, elle renvoie true si le paramètre passé à la fonction est de type Array et false dans le cas contraire

```
Array.isArray(value)
```

- `Array.join()` : La méthode join() crée et renvoie une nouvelle chaîne de caractères en concaténant tous les éléments d'un tableau. La concaténation utilise la virgule ou une autre chaîne, fournie en argument, comme séparateur.

```
arr.join()
arr.join(séparateur)

// exemple :
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"
console.log(elements.join(''));
// expected output: "FireAirWater"
```

- `Array.keys()` : La méthode keys() renvoie un nouvel objet Array qui contient les clefs pour chaque indice du tableau.

```
arr.keys()

// exemple :
const array1 = ['a', 'b', 'c'];
const iterator = array1.keys();
for (const key of iterator) {
  console.log(key);
}
// expected output: 0
// expected output: 1
// expected output: 2

```

- `Array.lastIndexOf()` : La méthode lastIndexOf() permet de renvoyer le dernier indice pour lequel une valeur donnée est présente dans un tableau. Si la valeur recherchée n'est pas présente, le résultat sera -1. Lors de la recherche, le tableau est parcouru dans le sens des index décroissants, à partir de l'index indexDébut.

```
arr.lastIndexOf(élémentRecherché)
arr.lastIndexOf(élémentRecherché, indexDébut)

// exemple :
const animals = ['Dodo', 'Tiger', 'Penguin', 'Dodo'];
console.log(animals.lastIndexOf('Dodo'));
// expected output: 3
```

- `Array.map()` : La méthode map() crée un nouveau tableau avec les résultats de l'appel d'une fonction fournie sur chaque élément du tableau appelant.

```
var nouveauTableau = arr.map(callback [, thisArg])

// exemple :
const array1 = [1, 4, 9, 16];
const map1 = array1.map(x => x * 2);
console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

- `Array.of()` : La methode Array.of() permet de créer une nouvelle instance d'objet Array à partir d'un nombre variable d'arguments, quels que soient leur nombre ou leur type.

- `Array.pop()` : La méthode pop() supprime le dernier élément d'un tableau et retourne cet élément. Cette méthode modifie la longueur du tableau.

```
arr.pop()
```

- `Array.push()` : La méthode push() ajoute un ou plusieurs éléments à la fin d'un tableau et retourne la nouvelle taille du tableau

```
arr.push(élément1, ..., élémentN)
```

- `Array.reduce()` : La méthode reduce() applique une fonction qui est un « accumulateur » et qui traite chaque valeur d'une liste (de la gauche vers la droite) afin de la réduire à une seule valeur.

```
arr.reduce(callback)
arr.reduce(callback, valeurInitiale)

// exemple :
const array1 = [1, 2, 3, 4];
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  initialValue
);
console.log(sumWithInitial);
// expected output: 10
```

- `Array.reduceRigth()` : La méthode reduceRight() applique une fonction sur un accumulateur et chaque valeur d'un tableau (de la droite vers la gauche) de sorte à réduire le tableau en une seule valeur.

```
arr.reduceRight(callback[, valeurInitiale])

// exemple :
const array1 = [[0, 1], [2, 3], [4, 5]].reduceRight(
  (accumulator, currentValue) => accumulator.concat(currentValue)
);
console.log(array1);
// expected output: Array [4, 5, 2, 3, 0, 1]
```

- `Array.reverse()` : La méthode reverse() transpose les éléments d'un tableau : le premier élément devient le dernier et le dernier devient le premier et ainsi de suite.

```
arr.reverse()

// exemple :
const array1 = ['one', 'two', 'three'];
const reversed = array1.reverse();
console.log('reversed:', reversed);
// expected output: "reversed:" Array ["three", "two", "one"]
```

- `Array.shift()` : La méthode shift() permet de retirer le premier élément d'un tableau et de renvoyer cet élément. Cette méthode modifie la longueur du tableau.

```
arr.shift()
```

- `Array.slice()` : La méthode slice() renvoie un objet tableau, contenant une copie superficielle d'une portion du tableau d'origine, la portion est définie par un indice de début et un indice de fin (exclus). Le tableau original ne sera pas modifié.

```
arr.slice()
arr.slice(début)
arr.slice(début, fin)

// exemple :
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]
```

- `Array.some()` : La méthode some() teste si au moins un élément du tableau passe le test implémenté par la fonction fournie. Elle renvoie un booléen indiquant le résultat du test.

```
arr.some(callback[, objetThis])

// exemple :
const array = [1, 2, 3, 4, 5];
const even = (element) => element % 2 === 0;
console.log(array.some(even));
// expected output: true

```

- `Array.sort()` : La méthode sort() trie les éléments d'un tableau, dans ce même tableau, et renvoie le tableau.

```
arr.sort()
arr.sort(fonctionComparaison)

// exemple :
const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// expected output: Array ["Dec", "Feb", "Jan", "March"]

```

- `Array.splice()` : La méthode splice() modifie le contenu d'un tableau en retirant des éléments et/ou en ajoutant de nouveaux éléments à même le tableau. On peut ainsi vider ou remplacer une partie d'un tableau.

```
var tabElementsSupprimes = array.splice(début, nbASupprimer[, élem1[, élem2[, ...]]])

// exemple :
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
console.log(months);
// expected output: Array ["Jan", "Feb", "March", "April", "June"]
```

- `Array.toLocaleString()` : La méthode toLocaleString() renvoie une chaîne de caractères qui représente les éléments du tableau. Les éléments sont convertis en chaînes de caractères grâce à leurs méthodes toLocaleString et chacune de ces chaînes est séparée des autres avec un séparateur propre à la locale courante (par exemple une virgule ou un point).

```
arr.toLocaleString();
arr.toLocaleString(locales);
arr.toLocaleString(locales, options);

// exemple :
const array1 = [1, 'a', new Date('21 Dec 1997 14:12:00 UTC')];
const localeString = array1.toLocaleString('en', { timeZone: 'UTC' });
console.log(localeString);
// expected output: "1,a,12/21/1997, 2:12:00 PM",
```

- `Array.toString()` : La méthode toString() renvoie une chaine de caractères représentant le tableau spécifié et ses éléments.

```
arr.toString()

// exemple :
const array1 = [1, 2, 'a', '1a'];
console.log(array1.toString());
// expected output: "1,2,a,1a"
```

- `Array.unshift()` : La méthode unshift() ajoute un ou plusieurs éléments au début d'un tableau et renvoie la nouvelle longueur du tableau.

```
arr.unshift([élém1[, ...[, élémN]]])
```

- `Array.values()` : La méthode values() renvoie un nouvel objet Array Iterator qui contient les valeurs pour chaque indice du tableau.

```
var a = ['t', 'i', 't', 'o', 'u'];
var iterateur = a.values();
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)