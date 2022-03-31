# Les méthodes de l'objet global `String`

Voici les différentes méthodes que l'on peut appliquer à un objet de type `String`.

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/String)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

[Retour vers le chapitre 'Les valeurs primitives et les objets globaux en JS'](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/chapJS/primitives.md)

- `String.chartAt()` : La méthode charAt() renvoie une nouvelle chaîne contenant le caractère (ou, plus précisément, le point de code UTF-16) à la position indiquée en argument.

```js
str.charAt(index)

// exemple :
const sentence = 'The quick brown fox jumps over the lazy dog.';
const index = 4;
console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// expected output: "The character at index 4 is q"
```

- `String.charCodeAt()` : La méthode charCodeAt() retourne un entier compris entre 0 et 65535 qui correspond au code UTF-16 d'un caractère de la chaîne situé à une position donnée.

```js
str.charCodeAt(indice)

// exemple :
const sentence = 'The quick brown fox jumps over the lazy dog.';
const index = 4;
console.log(`The character code ${sentence.charCodeAt(index)} is equal to ${sentence.charAt(index)}`);
// expected output: "The character code 113 is equal to q"

```

- `String.codePointAt()` : La méthode codePointAt() renvoie un entier positif qui correspond au code Unicode (code point) du caractère de la chaîne à la position donnée.

```js
str.codePointAt(pos)

// exemple :
const icons = '☃★♲';
console.log(icons.codePointAt(1));
// expected output: "9733"
```

- `String.concat()` : La méthode concat() combine le texte de plusieurs chaînes avec la chaîne appelante et renvoie la nouvelle chaîne ainsi formée.

```js
concat(valeur0, valeur1)

// exemple :
const str1 = 'Hello';
const str2 = 'World';
console.log(str1.concat(' ', str2));
// expected output: "Hello World"
```

- `String.concat()` : La méthode concat() est utilisée afin de fusionner deux ou plusieurs tableaux en les concaténant. Cette méthode ne modifie pas les tableaux existants, elle renvoie un nouveau tableau qui est le résultat de l'opération.

```js
str.concat(string2[, string3, ..., stringN])

// exemple :
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);
```

- `String.endsWith()` : La méthode endsWith() renvoie un booléen indiquant si la chaine de caractères se termine par la chaine de caractères fournie en argument.

```js
str.endsWith(chaîneRecherchée[, position]);

// exemple :
const str1 = 'Cats are the best!';
console.log(str1.endsWith('best', 17));
// expected output: true
```

- `String.fromCharCode()` : La méthode statique String.fromCharCode() renvoie une chaîne de caractères créée à partir de points de code UTF-16.

```js
String.fromCharCode(num1, ..., numN)

// exemple :
console.log(String.fromCharCode(189, 43, 190, 61));
// expected output: "½+¾="
```

- `String.fromCodePoint()` : La méthode statique String.fromCodePoint() renvoie une chaîne de caractères créée à partir d'un suite de codets.

```js
String.fromCodePoint(num1[, ...[, numN]])

// exemple :
console.log(String.fromCodePoint(9731, 9733, 9842, 0x2F804));
// expected output: "☃★♲你"
```

- `String.includes()` : La méthode includes() détermine si une chaîne de caractères est contenue dans une autre et renvoie true ou false selon le cas de figure.

```js
concat(valeur0, valeur1)

// exemple :
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);
```

- `String.concat()` : La méthode concat() est utilisée afin de fusionner deux ou plusieurs tableaux en les concaténant. Cette méthode ne modifie pas les tableaux existants, elle renvoie un nouveau tableau qui est le résultat de l'opération.

```js
str.includes(chaîneRecherchée);
str.includes(chaîneRecherchée, position);

// exemple :
const sentence = 'The quick brown fox jumps over the lazy dog.';
const word = 'fox';
console.log(`The word "${word}" ${sentence.includes(word) ? 'is' : 'is not'} in the sentence`);
// expected output: "The word "fox" is in the sentence"

```

- `String.indexOf()` : La méthode indexOf() renvoie l'indice de la première occurence de la valeur cherchée au sein de la chaîne courante (à partir de indexDébut). Elle renvoie -1 si la valeur cherchée n'est pas trouvée.

```js
str.indexOf(valeurRecherchée)
str.indexOf(valeurRecherchée, indexDébut)
```

- `String.lastIndexOf()` : La méthode lastIndexOf() renvoie l'indice, dans la chaîne courante, de la dernière occurence de la valeur donnée en argument. Si cette sous-chaîne n'est pas trouvée, la méthode renvoie -1. La recherche s'effectue de la fin vers le début de la chaîne, à partir de indiceDébut.

```js
str.lastIndexOf(valeurRecherchée[, indiceDébut])
```

- `String.match()` : La méthode match() permet d'obtenir le tableau des correspondances entre la chaîne courante et une expression rationnelle.

```js
str.match(regexp)

// exemple :
const paragraph = 'The quick brown fox jumps over the lazy dog. It barked.';
const regex = /[A-Z]/g;
const found = paragraph.match(regex);
console.log(found);
// expected output: Array ["T", "I"]
```

- `String.matchAll()` : La méthode matchAll() renvoie un itérateur contenant l'ensemble des correspondances entre une chaîne de caractères d'une part et une expression rationnelle d'autre part (y compris les groupes capturants).

```js
str.matchAll(regexp)

// exemple :
const regexp = /t(e)(st(\d?))/g;
const str = 'test1test2';
const array = [...str.matchAll(regexp)];
console.log(array[0]);
// expected output: Array ["test1", "e", "st1", "1"]

```

- `String.normalize()` : La méthode normalize() permet de renvoyer la forme normalisée Unicode d'une chaîne de caractères.

```js
str.normalize([form]);

// exemple :
const name1 = '\u0041\u006d\u00e9\u006c\u0069\u0065';
const name2 = '\u0041\u006d\u0065\u0301\u006c\u0069\u0065';
console.log(`${name1}, ${name2}`);
// expected output: "Amélie, Amélie"
```

- `String.padEnd()` : La méthode padEnd() permet de compléter la chaîne courante avec une chaîne de caractères donnée afin d'obtenir une chaîne de longueur fixée. Pour atteindre cette longueur, la chaîne complémentaire peut être répétée. La chaîne courante est complétée depuis la fin.

```js
str.padEnd(longueurCible [, chaîneComplémentaire])

// exemple :
const str1 = 'Breaded Mushrooms';
console.log(str1.padEnd(25, '.'));
// expected output: "Breaded Mushrooms........"
```

- `String.padStart()` : La méthode padStart() permet de compléter la chaîne courante avec une chaîne de caractères donnée afin d'obtenir une chaîne de longueur fixée. Pour atteindre cette longueur, la chaîne complémentaire peut être répétée. La chaîne courante est complétée depuis le début.

```js
str.padStart(longueurCible [, chaîneComplémentaire])

// exemple :
const str1 = '5';
console.log(str1.padStart(2, '0'));
// expected output: "05"
```

- `String.raw()` : La méthode statique String.raw() est une fonction d'étiquetage (tag function) pour les gabarits de chaînes de caractères (elle est semblable au préfixe r en Python ou au préfixe @ en C#). Cette fonction permet d'obtenir la chaîne brute pour un gabarit (les caractères spéciaux ne sont pas pris en compte mais retranscrits tels quels, les séquences d'échappement ne sont pas interprétées et les emplacements (ex. ${toto}) sont traités).

```js
String.raw(callSite, ...substitutions)

String.raw`gabaritChaîne`

// exemple :
const filePath = String.raw`C:\Development\profile\aboutme.html`;
console.log(`The file was uploaded from: ${filePath}`);
// expected output: "The file was uploaded from: C:\Development\profile\aboutme.html"
```

- `String.repeat()` : La méthode repeat() construit et renvoie une nouvelle chaine de caractères qui contient le nombre de copie demandée de la chaine de caractères sur laquelle la méthode a été appelée, concaténées les unes aux autres.

```js
str.repeat(compte)

// exemple :
const chorus = 'Because I\'m happy. ';

console.log(`Chorus lyrics for "Happy": ${chorus.repeat(27)}`);

// expected output: "Chorus lyrics for "Happy": Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. Because I'm happy. "

```

- `String.replace()` : La méthode replace() renvoie une nouvelle chaîne de caractères dans laquelle tout ou partie des correspondances à un modèle sont remplacées par un remplacement. Le modèle utilisé peut être une RegExp et le remplacement peut être une chaîne ou une fonction à appeler pour chaque correspondance. Si modèle est une chaîne de caractères, seule la première correspondance sera remplacée.

La chaîne de caractère originale reste inchangée.

```js
chn.replace(regexp|souschn, nouvSouschn|fonction)

// exemple :
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';
console.log(p.replace('dog', 'monkey'));
// expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"
```

- `String.replaceAll()` : La méthode replaceAll() retourne une nouvelle chaîne de caractères dans laquelle toutes les occurrences d'un motif donné ont été remplacées par une chaîne de remplacement. L'argument pattern fournit pour décrire le motif peut être une chaîne de caractères ou une expression rationnelle (RegExp), l'argument replacement peut être une chaîne de caractères ou une fonction qui sera appelée pour chaque correspondance.

La chaîne de caractères initiale restera inchangée.

```js
const newStr = str.replaceAll(regexp|substr, newSubstr|function)
```

- `String.search()` : La méthode search() éxecute une recherche dans une chaine de caractères grâce à une expression rationnelle appliquée sur la chaîne courante.

```js
str.search(regexp)

// exemple :
const paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';
const regex = /[^\w\s]/g;
console.log(paragraph.search(regex));
// expected output: 43
```

- `String.split()` : La méthode split() divise une chaîne de caractères en une liste ordonnée de sous-chaînes, place ces sous-chaînes dans un tableau et retourne le tableau. La division est effectuée en recherchant un motif ; où le motif est fourni comme premier paramètre dans l'appel de la méthode.

```js
str.split([separator[, limit]])

// exemple :
const str = 'The quick brown fox jumps over the lazy dog.';
const words = str.split(' ');
console.log(words[3]);
// expected output: "fox"

```

- `String.startsWith()` : La méthode startsWith() renvoie un booléen indiquant si la chaine de caractères commence par la deuxième chaine de caractères fournie en argument.

```js
str.startsWith(chaîneRecherchée [, position]);

// exemple :
const str1 = 'Saturday night plans';
console.log(str1.startsWith('Sat'));
// expected output: true
```

- `String.substring()` : La méthode substring() retourne une sous-chaîne de la chaîne courante, entre un indice de début et un indice de fin.

```js
str.substring(indiceA[, indiceB])

// exemple :
const str = 'Mozilla';
console.log(str.substring(1, 3));
// expected output: "oz"
```

- `String.toLocaleLowerCase()` : La méthode toLocaleLowerCase() renvoie la chaîne de caractères qui appelle la méthode en une chaîne de caractères représentées en minuscules, en tenant compte des correspondances de caractères propres aux différentes locales.

```js
str.toLocaleLowerCase()
str.toLocaleLowerCase(locale)
str.toLocaleLowerCase([locale, locale, ...])

// exemple :
const dotted = 'İstanbul';
console.log(`EN-US: ${dotted.toLocaleLowerCase('en-US')}`);
// expected output: "i̇stanbul"
```

- `String.toLocaleUpperCase()` : La méthode toLocaleUpperCase() renvoie la chaîne de caractères qui appelle la méthode en caractères majuscules, selon les correspondances de caractères propres aux différentes locales.

```js
str.toLocaleUpperCase()
str.toLocaleUpperCase(locale)
str.toLocaleUpperCase([locale, locale, ...])

// exemple :
const city = 'istanbul';
console.log(city.toLocaleUpperCase('TR'));
// expected output: "İSTANBUL"
```

- `String.toLowerCase()` : La méthode toLowerCase() retourne la chaîne de caractères courante en minuscules.

```js
str.toLowerCase()
```

- `String.toString()` : La méthode toString() renvoie une chaine de caractères représentant l'objet renseigné.

```js
str.toString()

// exemple :
const stringObj = new String('foo');
console.log(stringObj);
// expected output: String { "foo" }
```

- `String.toUpperCase()` : La méthode toUpperCase() retourne la valeur de la chaîne courante, convertie en majuscules.

```js
str.toUpperCase()
```

- `String.trim()` : La méthode trim() permet de retirer les blancs en début et fin de chaîne. Les blancs considérés sont les caractères d'espacement (espace, tabulation, espace insécable, etc.) ainsi que les caractères de fin de ligne (LF, CR, etc.).

```js
str.trim()

// exemple :
const greeting = '   Hello world!   ';
console.log(greeting.trim());
// expected output: "Hello world!";
```

- `String.trimEnd()` : La méthode trimEnd() permet de retirer les blancs situés à la fin d'une chaîne de caractères. trimRight() est un synonyme pour cette méthode.

```js
str.trimEnd();
str.trimRight();

// exemple :
const greeting = '   Hello world!   ';
console.log(greeting.trimEnd());
// expected output: "   Hello world!";
```

- `String.trimStart()` : La méthode trimStart() permet de retirer les blancs au début de la chaîne de caractères. trimLeft() est un synonyme pour cette méthode.

```js
str.trimStart();
str.trimLeft();

// exemple :
const greeting = '   Hello world!   ';
console.log(greeting.trimStart());
// expected output: "Hello world!   ";
```

- `String.valueOf()` : La méthode valueOf() renvoie la valeur primitive de l'objet String.

```js
str.valueOf()
```

[Retour vers le chapitre 'Les valeurs primitives et les objets globaux en JS'](https://github.com/CalcagnoLoic/aide_memoire/blob/main/R%C3%A9pertoire/chapJS/primitives.md)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)