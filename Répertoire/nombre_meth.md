# Les méthodes de l'objet global `Number`

Voici les différentes méthodes que l'on peut appliquer à un objet de type `Number`.

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Number)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

- `Number.isFinite()` : La méthode Number.isFinite() permet de déterminer si la valeur fournie est un nombre fini.
```
Number.isFinite(valeurÀTester);

// exemple :
console.log(Number.isFinite(1 / 0));
// expected output: false
```

- `Number.isInteger()` : La méthode Number.isInteger() permet de déterminer si l'argument est un nombre entier.

```
Number.isInteger(valeurÀTester)

// exemple :
function fits(x, y) {
  if (Number.isInteger(y / x)) {
    return 'Fits!';
  }
  return 'Does NOT fit!';
}
console.log(fits(5, 10));
// expected output: "Fits!"
```

- `Number.isNaN()` : La méthode Number.isNaN() permet de déterminer si la valeur passée en argument est NaN, avec un type Number. 

```
Number.isNaN(valeurÀTester)

// exemple :
function typeOfNaN(x) {
  if (Number.isNaN(x)) {
    return 'Number NaN';
  }
  if (isNaN(x)) {
    return 'NaN';
  }
}
console.log(typeOfNaN('100F'));
// expected output: "NaN"
```

- `Number.isSafeInteger()` : La méthode Number.isSafeInteger() permet de déterminer si la valeur, passée en argument, est un entier représentable correctement en JavaScript 

```
Number.isSafeInteger(valeurÀTester)
```

- `Number.parseFloat()` : La méthode Number.parseFloat() analyse et convertit une chaîne de caractères en un nombre flottant. 

```
Number.parseFloat(chaîne)

// exemple :
function circumference(r) {
  if (Number.isNaN(Number.parseFloat(r))) {
    return 0;
  }
  return parseFloat(r) * 2.0 * Math.PI ;
}
console.log(circumference('4.567abcdefgh'));
// expected output: 28.695307297889173
```

- `Number.parseInt()` : La méthode Number.parseInt() analyse et convertit une chaine de caractères, fournie en argument, en un entier dans la base souhaitée.

```
Number.parseInt(chaîne [, base])

// exemple :
function roughScale(x, base) {
  const parsed = Number.parseInt(x, base);
  if (Number.isNaN(parsed)) {
    return 0;
  }
  return parsed * 100;
}
console.log(roughScale(' 0xF', 16));
// expected output: 1500
```

- `Number.toExponential()` : La méthode toExponential() renvoie une chaîne de caractères, représentant l'objet Number en notation exponentielle.

```
numObj.toExponential([nbChiffresDécimaux])

// exemple :
function expo(x, f) {
  return Number.parseFloat(x).toExponential(f);
}
console.log(expo(123456, 2));
// expected output: "1.23e+5"
```

- `Number.toFixed()` : La méthode toFixed() permet de formater un nombre en notation à point-fixe.

```
numObj.toFixed([nbChiffres])

// exemple :
function financial(x) {
  return Number.parseFloat(x).toFixed(2);
}
console.log(financial(123.456));
// expected output: "123.46"
```

- `Number.toLocaleString()` : La méthode toLocaleString() permet de renvoyer une chaîne de caractères représentant un nombre en tenant compte de la locale.

```
objetNumber.toLocaleString([locales [, options]])

// exemple :
function eArabic(x){
  return x.toLocaleString('ar-EG');
}

console.log(eArabic(123456.789));
// expected output: "١٢٣٬٤٥٦٫٧٨٩"
```

- `Number.toPrecision()` : La méthode toPrecision() renvoie une chaîne de caractères représentant un nombre avec la précision donnée.

```
numObj.toPrecision([précision])

// exemple :
function precise(x) {
  return x.toPrecision(4);
}
console.log(precise(123.456));
// expected output: "123.5"
```

- `Number.toString()` : La méthode toString() renvoie une chaîne de caractère représentant l'objet Number.

```
numObj.toString([base])

// exemple :
function hexColour(c) {
  if (c < 256) {
    return Math.abs(c).toString(16);
  }
  return 0;
}
console.log(hexColour(233));
// expected output: "e9"
```

- `Number.valueOf()` : La méthode valueOf() renvoie la valeur primitive correspondant à celle représentée par l'objet Number.

```
objetNumber.valueOf()

// exemple :
const numObj = new Number(42);
const num = numObj.valueOf();
console.log(num);
// expected output: 42
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

