# Les méthodes de l'objet global `Object`

Voici les différentes méthodes que l'on peut appliquer à un objet de type `Object`.

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Object)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

- `Object.assign()` : La méthode Object.assign() est utilisée afin de copier les valeurs de toutes les propriétés directes (non héritées) d'un objet qui sont énumérables sur un autre objet cible. Cette méthode renvoie l'objet cible.

```js
Object.assign(cible, ...sources)

// exemple :
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };
const returnedTarget = Object.assign(target, source);
console.log(target);
// expected output: Object { a: 1, b: 4, c: 5 }
```

- `Object.create()` : La méthode Object.create() crée un nouvel objet avec un prototype donné et des propriétés données.

```js
Object.create(proto)
Object.create(proto, objetPropriétés)

// exemple :
const person = {
  isHuman: false,
  printIntroduction: function() {
    console.log(`My name is ${this.name}. Am I human? ${this.isHuman}`);
  }
};
const me = Object.create(person);
```

- `Object.defineProperties()` : La méthode Object.defineProperties() permet de définir ou de modifier les propriétés d'un objet directement sur celui-ci. La valeur renvoyée est l'objet modifié.

```js
Object.defineProperties(obj, props)

// exemple :
const object1 = {};

Object.defineProperties(object1, {
  property1: {
    value: 42,
    writable: true
  },
  property2: {}
});

console.log(object1.property1);
// expected output: 42
```

- `Object.defineProperty()` : La méthode statique Object.defineProperty() permet de définir une nouvelle propriété ou de modifier une propriété existante, directement sur un objet. La méthode renvoie l'objet modifié.

```js
Object.defineProperty(obj, prop, descripteur)

// exemple :
const object1 = {};

Object.defineProperty(object1, 'property1', {
  value: 42,
  writable: false
});

object1.property1 = 77;
// throws an error in strict mode

console.log(object1.property1);
// expected output: 42

```

- `Object.entries()` : La méthode Object.entries() renvoie un tableau des propriétés propres énumérables d'un objet dont la clé est une chaîne de caractères, sous la forme de paires [clé, valeur], dans le même ordre qu'une boucle for...in (la boucle for-in est différente car elle parcourt la chaîne des prototypes).

```js
Object.entries(obj)

// exemple :
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// expected output:
// "a: somestring"
// "b: 42"

```

- `Object.freeze()` : La méthode Object.freeze() permet de geler un objet, c'est-à-dire qu'on empêche d'ajouter de nouvelles propriétés, de supprimer ou d'éditer des propriétés existantes, y compris en ce qui concerne leur caractère énumérable, configurable ou pour l'accès en écriture. L'objet devient ainsi immuable. La méthode renvoie l'objet ainsi « gelé ».

```js
Object.freeze(obj)

// exemple :
const obj = {
  prop: 42
};

Object.freeze(obj);

obj.prop = 33;
// Throws an error in strict mode

console.log(obj.prop);
// expected output: 42
```

- `Object.fromEntries()` : La méthode Object.fromEntries() permet de transformer une liste de paires de clés/valeurs en un objet.

```js
Object.fromEntries(iterable);

// exemple :
const entries = new Map([
  ['foo', 'bar'],
  ['baz', 42]
]);

const obj = Object.fromEntries(entries);

console.log(obj);
// expected output: Object { foo: "bar", baz: 42 }

```

- `Object.getOwnPropertyDescriptor()` : La méthode Object.getOwnPropertyDescriptor() renvoie un descripteur de la propriété propre d'un objet (c'est-à-dire une propriété directement présente et pas héritée via la chaîne de prototypes).

```js
Object.getOwnPropertyDescriptor(obj, prop)
```

- `Object.getOwnPropertyDescriptors()` : La méthode Object.getOwnPropertyDescriptors() renvoie l'ensemble des descripteurs des propriétés propres d'un objet donné.

```js
Object.getOwnPropertyDescriptors(obj)
```

- `Object.getOwnPropertyNames()` : La méthode Object.getOwnPropertyNames() renvoie un tableau de toutes les propriétés (qu'elles soient énumérables ou non, tant qu'elles ne sont pas désignées par un symbole) propres à un objet (c'est-à-dire n'étant pas héritées via la chaîne de prototypes).

```js
Object.getOwnPropertyNames(obj)
```

- `Object.getOwnPropertySymbols()` : La méthode Object.getOwnPropertySymbols() renvoie un tableau contenant tous les symboles des propriétés trouvées directement sur un objet donné.

```js
Object.getOwnPropertySymbols(obj)
```

- `Object.getPrototypeOf()` : La méthode Object.getPrototypeOf() renvoie le prototype d'un objet donné (i.e. la valeur de la propriété [[Prototype]] interne).

```js
Object.getPrototypeOf(obj)
```

- `Object.hasOwnProperty()` : La méthode hasOwnProperty() retourne un booléen indiquant si l'objet possède la propriété spécifiée "en propre", sans que celle-ci provienne de la chaîne de prototypes de l'objet.

```js
obj.hasOwnProperty(prop)
```

- `Object.is()` : La méthode Object.is() permet de déterminer si deux valeurs sont les mêmes.

```js
Object.is(value1, value2);
```

- `Object.isExtensible()` : La méthode Object.isExtensible() permet de déterminer si un objet est extensible (c'est-à-dire qu'on peut lui ajouter de nouvelles propriétés).

```js
Object.isExtensible(obj)
```

- `Object.isFrozen()` : La méthode Object.isFrozen() permet de déterminer si un objet est gelé.

```js
Object.isFrozen(obj)
```

- `Object.isPrototypeOf()` : La méthode isPrototypeOf() permet de tester si un objet existe dans la chaîne de prototypes d'un autre objet.

```js
prototypeObj.isPrototypeOf(objet)
```

- `Object.isSealed()` : La méthode Object.isSealed() permet de déterminer si un objet est scellé.

```js
Object.isSealed(obj)
```

- `Object.keys()` : La méthode Object.keys() renvoie un tableau contenant les noms des propriétés propres à un objet (qui ne sont pas héritées via la chaîne de prototypes) et qui sont énumérables. L'ordre de ce tableau est le même que celui obtenu par une boucle for...in (à la différence qu'une boucle for-in liste également les propriétés héritées).

```js
Object.keys(obj)

// exemple :
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};

console.log(Object.keys(object1));
// expected output: Array ["a", "b", "c"]
```

- `Object.preventExtensions()` : La méthode Object.preventExtensions() permet d'empêcher l'ajout de nouvelles propriétés à un objet (i.e. d'étendre l'objet grâce à de nouvelles caractéristiques).

```js
Object.preventExtensions(obj)
```

- `Object.propertyIsEnumerable()` : La méthode propertyIsEnumerable() renvoie un booléen qui indique si la propriété donnée est énumérable.

```js
obj.propertyIsEnumerable(prop)
```

- `Object.seal()` : La méthode Object.seal() scelle un objet afin d'empêcher l'ajout de nouvelles propriétés, en marquant les propriétés existantes comme non-configurables. Les valeurs des propriétés courantes peuvent toujours être modifiées si elles sont accessibles en écriture.

```js
Object.seal(obj)
```

- `Object.setPrototypeOf()` : La méthode Object.setPrototypeOf() définit le prototype (autrement dit la propriété interne [[Prototype]]) d'un objet donné avec un autre objet ou null.

```js
Object.setPrototypeOf(obj, prototype)
```

- `Object.toLocaleString()` : La méthode toLocaleString() renvoie une chaine de caractères représentant l'objet. Cette méthode est destinée à être surchargée par les objets dérivés à des fins spécifiques pour prendre en compte les locales.

```js
obj.toLocaleString()
```

- `Object.toString()` : La méthode toString() renvoie une chaîne de caractères représentant l'objet.

```js
obj.toString()
```

- `Object.valueOf()` : La méthode valueOf() renvoie la valeur primitive d'un objet donné.

```js
object.valueOf()
```

- `Object.values()` : La méthode Object.values() renvoie un tableau contenant les valeurs des propriétés propres énumérables d'un objet dont l'ordre est le même que celui obtenu avec une boucle for...in (la boucle for-in est différente car elle parcourt également les propriétés héritées).

```js
Object.values(obj)

// exemple :
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};

console.log(Object.values(object1));
// expected output: Array ["somestring", 42, false]
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)