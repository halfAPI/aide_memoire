# Les méthodes de l'objet global `Set`

Voici les différentes méthodes que l'on peut appliquer à un objet de type `Set`.

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Set)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

- `Set.add()` : La méthode add() permet d'ajouter un nouvel élément ayant une valeur donnée à un ensemble Set. Cette valeur sera ajoutée à la fin de l'objet Set.

```
monSet.add(valeur);

// exemple :
const set1 = new Set();

set1.add(42);
set1.add(42);
set1.add(13);

for (const item of set1) {
  console.log(item);
  // expected output: 42
  // expected output: 13
}
```

- `Set.clear()` : La méthode clear() permet de retirer tous les éléments d'un ensemble Set.

```
monSet.clear();

// exemple :
const set1 = new Set();
set1.add(1);
set1.add('foo');

console.log(set1.size);
// expected output: 2

set1.clear();

console.log(set1.size);
// expected output: 0
```

- `Set.delete()` : La méthode delete() permet de retirer un élément donné d'un objet Set.

```
monSet.delete(valeur);

// exemple :
const set1 = new Set();
set1.add({ x: 10, y: 20 }).add({ x: 20, y: 30 });

// Delete any point with `x > 10`.
set1.forEach((point) => {
  if (point.x > 10) {
    set1.delete(point);
  }
});

console.log(set1.size);
// expected output: 1

```

- `Set.entries()` : La méthode entries() renvoie un nouvel objet Iterator qui contient un tableau composé de [valeur, valeur] pour chaque élément de l'objet Set, dans leur ordre d'insertion. En raison de leur structure, les objets Set n'ont pas de clé (key), à la différence des objets Map. Pour garder une structure et une API sembables à celle d'un objet Map, chaque entrée (entry) aura la même valeur pour la clé (key) et pour la valeur (value), c'est pourquoi un tableau de [valeur, valeur] est renvoyé.

```
monSet.entries()

// exemple :
const set1 = new Set();
set1.add(42);
set1.add('forty two');

const iterator1 = set1.entries();

for (const entry of iterator1) {
  console.log(entry);
  // expected output: [42, 42]
  // expected output: ["forty two", "forty two"]
}
```

- `Set.forEach()` : La méthode forEach() permet d'exécuter une fonction donnée, une fois pour chaque valeur de l'ensemble Set. L'ordre appliqué est celui dans lequel les valeurs ont été ajoutées à l'ensemble.

```
monSet.forEach(callback[, thisArg])

// exemple :
function logSetElements(value1, value2, set) {
  console.log(`s[${value1}] = ${value2}`);
}

new Set(['foo', 'bar', undefined]).forEach(logSetElements);

// expected output: "s[foo] = foo"
// expected output: "s[bar] = bar"
// expected output: "s[undefined] = undefined"
```

- `Set.has()` : La méthode has() renvoie un booléen qui indique s'il existe un élément de l'ensemble Set avec une certaine valeur.

```
monSet.has(valeur);

// exemple :
const set1 = new Set([1, 2, 3, 4, 5]);

console.log(set1.has(1));
// expected output: true

console.log(set1.has(5));
// expected output: true

console.log(set1.has(6));
// expected output: false
```

- `Set.values()` : La méthode values() renvoie un nouvel objet Iterator qui contient les valeurs de chaque élément de l'objet Set, dans leur ordre d'insertion.

La méthode keys() est un alias pour cette méthode (afin de conserver une certaine similarité avec les objets Map) et se comportera exactement de la même façon en renvoyant les valeurs des éléments du Set.

```
monSet.values();

// exemple :
const set1 = new Set();
set1.add(42);
set1.add('forty two');

const iterator1 = set1.values();

console.log(iterator1.next().value);
// expected output: 42

console.log(iterator1.next().value);
// expected output: "forty two"
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)