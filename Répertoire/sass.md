# SASS/SCSS

Ecrire en SASS ou SCSS c'est comme écrire du CSS mais en étant optimal. En effet, dès qu'on a des répétitions du code en CSS, on peut imbriquer notre code sous forme de SASS/SCSS

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

## Différence entre SASS et SCSS

Il s'agit tout simplement de la présence ou non de parenthèses 

```css
/*SCSS*/
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}

/*SASS*/
$font-stack: Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color
```

_Dans les exemples qui vont suivre, la transformation du SCSS en CSS sera toujours indiquée pour bien comprendre l'écriture du SCSS_

## Les variables 

Il s'agit d'un principe de stockage d'instruction au sein d'une variable. Son utilité est que si un petit bloc d'instruction est répété dans plusieurs balises HTML, on stocke ce bloc dans une variable. Il ne restera plus qu'à faire un appel de cette variable dans les balises adéquates. 

```css
$font-stack: Helvetica, sans-serif
$primary-color: #333

body{
  font: 100% $font-stack
  color: $primary-color
}
```

**Le CSS correspondant :**

```css
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
```

## Les opérateurs

L'écriture en SASS permet d'ajouter des opérateurs mathématiques à notre code. Il s'agit des opérations de base : `+`, `-`, `*`, `math.div()` et `%`.

```css
article[role="main"] {
  width: math.div(600px, 960px) * 100%;
}

aside[role="complementary"] {
  width: math.div(300px, 960px) * 100%;
  margin-left: auto;
}
```

**Le CSS correspondant :**

```css
article[role="main"] {
  width: 62.5%;
}

aside[role="complementary"] {
  width: 31.25%;
  margin-left: auto;
}
```

## Le nesting

Lorsque l'on écrit en HTML, il y a forcément des éléments qui s'emboitent et ont une certaine hiérarchie. En CSS, ce n'est pas possible de retranscrire cela, il faut à chaque fois répéter le bloc ou du moins, améliorer ça en passant par les sélecteurs. 

SASS permet de contrer ce problème en permettant d'imbriquer les éléments suivant la même hiérarchie présente dans le document HTML.

Il faut néanmoins préciser que des éléments trop imbriqués peuvent conduire à un CSS surqualifié, ce qui est considéré comme une mauvaise pratique. 

```css
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}
```

**Le CSS correspondant :**

```css
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

## Les classes étendues

L'utilisation de classes étendues permet de partager un ensemble de propriétés CSS d'un sélecteur à un autre.

```css
/* This CSS will print because %message-shared is extended. */
%message-shared {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

/*This CSS won't print because %equal-heights is never extended.*/
%equal-heights {
  display: flex;
  flex-wrap: wrap;
}

.message {
  @extend %message-shared;
}

.success {
  @extend %message-shared;
  border-color: green;
}

.error {
  @extend %message-shared;
  border-color: red;
}

.warning {
  @extend %message-shared;
  border-color: yellow;
}
```

**Le CSS correspondant :**

```css
/* This CSS will print because %message-shared is extended. */
.message, .success, .error, .warning {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  border-color: green;
}

.error {
  border-color: red;
}

.warning {
  border-color: yellow;
}
```

## L'utilisation de modules

Il n'y a pas d'obligation d'utiliser un seul et même fichier SASS, on peut le diviser. Admettons que dans un fichier, on possède une variable qui nous intéresse dans un autre projet. Alors, on pourrait utiliser un module qui charge le code présent à l'endroit définit afin de charger ladite variable. 

```css
/*Fichier 1 : _base.scss*/
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
////////////////////////////////////////

/*Fichier 2 : styles.scss*/
@use 'base';

.inverse {
  background-color: base.$primary-color;
  color: white;
}
```

**Le CSS correspondant :**

```css
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}

.inverse {
  background-color: #333;
  color: white;
}
```

## Les mixines

A partir du moment où on répète plus de 2 fois un bloc d'instruction, le risque d'erreur augmente lui aussi. C'est pourquoi, il est intéressant de passer par une structure de stockage des instructions, que l'on appelle mixine, et faire un appel à chaque que l'on a besoin de ces instructions. C'est un peu le principe des fonctions en algorithmie. 

```css
@mixin theme($theme: DarkGray) {
  background: $theme;
  box-shadow: 0 0 1px rgba($theme, .25);
  color: #fff;
}

.info {
  @include theme;
}
.alert {
  @include theme($theme: DarkRed);
}
.success {
  @include theme($theme: DarkGreen);
}
```

**Le CSS correspondant :**

```css
.info {
  background: DarkGray;
  box-shadow: 0 0 1px rgba(169, 169, 169, 0.25);
  color: #fff;
}

.alert {
  background: DarkRed;
  box-shadow: 0 0 1px rgba(139, 0, 0, 0.25);
  color: #fff;
}

.success {
  background: DarkGreen;
  box-shadow: 0 0 1px rgba(0, 100, 0, 0.25);
  color: #fff;
}
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)
