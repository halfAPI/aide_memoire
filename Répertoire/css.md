# Les commandes utilisées en CSS

Une cheatsheet interactive sur le CSS se trouve [ICI](https://htmlcheatsheet.com/css/)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

## Les propriétés de mise en forme du texte

- `font-family` : nom de la police

- `@font-face` : police personnalisée

- `font-size` : taille du texte

- `font-weight` : mettre en gras

- `font-style` : mettre un style de texte (italique, oblique, ...)

- `text-decoration` : soulignement, ligne au-dessus, barré, ...

- `font` : super propriété de police permettant de combiner les propriétés `font`. Exemple : `font : Arial 12px bolder`

- `font-variant` : petites capitales

- `text-transform` : permet de modifier le texte (uppercase, lowercase, etc)

- `text-align` : alignement horizontal (gauche, centré, droite, justifier)

- `vertical-align` : alignement vertical (sur des cellules de tableau ou sur des éléments `inline-block`)

- `line-height` : hauteur de ligne

- `text-indent` : ajout d'alinéa

- `white-space` : césure

- `word-wrap` : césure forcée

- `text-shadow` : ombre de texte (horizontale, verticale, fondu, couleur : `text-shadow : 5px 5px 2px blue`)

## Les propriétés de couleur et de fond 

- `color` : couleur du texte

- `background-color` : couleur de fond

- `background-image` : image de fond

- `background-attachment` : fond fixe (`fixed`, `scroll`)

- `background-repeat` : répétition du fond (`repeat-x`, `repeat-y`, `no-repeat`, `repeat`)

- `background-position` : position du fond

- `background` : super propriété du fond permettant de combiner les propriétés `background`. Exemple : `background : url(example.png) no repeat scroll`

- `opacity` : transparence

## Les propriétés des boîtes

![box-model](https://upload.wikimedia.org/wikipedia/commons/7/7a/Boxmodell-detail.png)

- `width` : largeur

- `height` : hauteur

- `min-width` : largeur minimale

- `max-width` : largeur maximale

- `min-height` : hauteur minimale

- `max-height` : hauteur maximale

- `margin-top` : marge en haut

- `margin-left` : marge à gauche

- `margin-rigth` : marge à droite

- `margin-bottom` : marge en bas

- `margin` : super propriété combinant les propriétés de `marge`. (haut, droit, bas, gauche => `5px 15px 2px 15px`)

- `padding-top` : marge intérieure en haut

- `padding-left` : marge intérieure à gauche

- `padding-right` : marge intérieure à droite

- `padding-bottom` : marge intérieure en bas
 
- `padding` : super propriété combinant les propriétés de `padding`. (haut, droit, bas, gauche => `5px 15px 2px 15px`)

- `border-width` : épaisseur de la bordure

- `border-color` : couleur de la bordure

- `border-style` : type de la bordure

- `border` : super propriété combiant les 3 propriétés précédentes (exemple `border : 1px solid black`)

- `border-top` : bordure du haut

- `border-left` : bordure à gauche
 
- `border-rigth` : bordure à droite

- `border-bottom` : bordure du bas

- `border-radius` : bordure arrondie

- `box-shadow` : ombre de la boite (horizontale, verticale, fondu, couleur => `box-shadow : 6px 6px 1px blue`)

## Les propriétés de positionnement et d'affichage 

- `display` : type d'élément (`block`, `inline-block`, `table`, `none`, `flex`, `inline`, ...)

- `visibility` : visibilité

- `clip` : affichage d'une partie de l'élément

- `overflow` : comportement en cas de dépassement (`auto`, `scroll`, `visible`, `hidden`)

- `float` : flottant

- `clear` : arrêt d'un flottant

- `position` : positionnement 

![positionnement](https://cdn.educba.com/academy/wp-content/uploads/2019/12/CSS-Position.jpg)

- `top` : positionnement par rapport au haut

- `bottom` : positionnement par rapport au bas

- `left` : positionnement par rapport à la gauche

- `rigth` : positionnement par rapport à la droite

- `z-index` : ordre d'affichage en cas de superposition. La plus grande valeur est affichée par-dessus les autres.

## Les propriétés des styles

- `list-style-type` : type de liste

- `liste-style-position` : position en retrait

- `list-style-image` : puce personnalisée

- `list-style` : super propriété de `list-style`

## Les propriétés des tableaux

- `border-collapse` : fusion des bordures

- `empty-cells` : affichage des cellules vides

- `caption-side` : position du titre du tableau

## Les sélecteurs CSS 

- `.class` : sélectionne les éléments ayant une classe .class

- `.class1.class2` : sélectionne tous les éléments comprenant à la fois .class1 et .class2

- `.class1 .class2` : sélectionne tout les éléments .class2 qui sont des descendants de .class1

- `#exemple` : sélectionne les éléments ayant un ID correspondant à exemple

- `*` : sélectionne tout les éléments 

- `p` : sélectionne les éléments p

- `p.intro` : sélectionne tout les éléments p ayant une classe intro 

- `div, p` : sélectionne tout les éléments div et p

- `div p` : sélectionne tout les éléments p à l'intérieur des éléments div

- `div > p` : sélectionne les éléments p où le parent est un élément div

- `div + p` : sélectionne le premier élément p qui est placé immédiatement après l'élément div

- `p ~ ul` : sélectionne tout les éléments ul qui sont précédé par un élément p

- `[target]` : sélectionne tout les éléments ayant l'attribut target

- `[target=_blank]` : sélectionne tout les éléments ayant `_blank` comme valeur d'attribut pour target

- `[title~=flower]` : sélectionne tout les éléments avec un titre comprenant le mot flower

- `[lang|=en]` : sélectionne tout les éléments ayant un attribut lang dont la valeur est égal à 'en' ou commence par 'en'

- `a[href^="https"]` : sélectionne tout les éléments a qui ont un attribut href dont la valeur commence par https

- `a[href$="https"]`: sélectionne tout les éléments a qui ont un attribut href dont la valeur fini par .pdf

- `a[href*="w3schools"]` : : sélectionne tout les éléments a qui ont un attribut href dont la valeur contient par w3schools

- `a:active` : sélection les liens actifs

- `p::after` : insert quelque chose après le contenu de chaque p

- `p::before` : insert quelque chose avant le contenu de chaque p

- `input:checked` : sélectionne chaque élément input coché

- `input:defaut` : sélectionne chaque élément input par défaut

- `input:disabled` : sélectionne chaque élément input désactivé

- `p:empty` : sélectionne tout les éléments p qui n'ont pas d'enfants

- `input:enabled` : sélectionne chaque élément input activé

- `p:first-child` : sélectionne tout les éléments p qui sont les premiers enfants des parents

- `p::first-letter` : sélectionne la première lettre de chaque élément p

- `p::first-line` : sélectionne la première ligne de chaque élément p

- `p:first-of-type` = sélectionne chaque éléments p qui sont les premiers éléments p des parents

- `input=focus` : sélectionne les éléments input qui ont un focus

- `:fullscreen` : sélectionne les éléments qui sont en mode fullscreen

- `a:hover` : sélectionne les liens en survol de souris

- `input:in-range` : sélectionne les éléments avec une valeur comprise dans une gamme spécifiée

- `input:indeterminate` : sélectionne les éléments input qui ont un état indéterminé

- `p:lang(it)` : sélectionne chaque éléments p avec un attribut lang égal à 'it'

- `p:last-child` : sélectionne chaque éléments p qui est le dernier enfant des parents 

- `p:last-of-type`:sélectionne chaque éléments p qui sont les derniers éléments p des parents 

- `a:link` : sélection tout les liens non visités

- `::marker` : sélection les marqueurs des listes d'items 

- `:not(p)` : sélectionne chaque éléments qui ne sont pas p

- `p:nth-child(2)` : sélectionne chaque éléments p qui sont le second enfant du parent

- `p:nth-last-of-type(2)` : sélectionne chaque éléments p qui sont les seconds éléments p des parents, en comptant depuis le dernier enfant 

- `p:nth-of-type(2)` : sélectionne chaque éléments p qui sont les seconds éléments p des parents 

- `p:only-of-type` : sélectionne chaque éléments p qui sont les seuls éléments p des parents

- `p:only-child` : sélectionne chaque éléments p qui sont les seuls enfants des parents 

- `input:optional` : sélectionne les éléments input qui n'ont pas d'attribut requis

- `input:out-of-range` : sélectionne les éléments input qui ont une valeur à l'extérieur d'une plage spécifiée

- `input::placeholder` : sélectionne les éléments inputs avec un attribut `placeholder` spécifié

- `input:read-only` : sélectionne les éléments input qui ont un attribut `read-only` spécifié

- `input:read-write` : sélectionne les éléments input qui n'ont pas un attribut `read-only` spécifié

- `input:required` : sélection les éléments input ayant l'attribut requis spécifié

- `:root` : sélectionne l'élément racine du document

- `::selection` : sélectionne la portion d'un élément qui est sélection par un utilisateur

- `#new:target` : sélection l'élément #news qui est actuellement actif

- `input:valid` : selection tout les éléments input avec une valeur valide

- `a:visited` : sélectionne tout les liens visitables

## L'utilisation des flexbox

![](https://sharkcoder.com/files/article/flex1.png)

Pour des illustrations des propriétés sur le container ou les items : https://css-tricks.com/snippets/css/a-guide-to-flexbox/ 

### Les propriétés pour le container 

- `display` : définit le container du flex

- `flex-direction` : définit la direction du flex (`row` : de gauche à droite, `row-reverse` : de droite à gauche, `column` : de haut en bas, `column-reverse` : de bas en haut)

- `flex-wrap` : par défaut, les items de la flex se mettent sur une ligne. Cette propriété permet de changer cela

- `flex-flow` : propriété combinant `flex-direction` et `flex-wrap`

- `justify-content` : définit l'alignement selon l'axe principal du container (centré, début de container, avec espace, ...)

- `align-items` : permet de définir le comportement de la flex par rapport à l'aligment des items 

- `align-content` : permet d'aligner les éléments du container

- `gap`, `row-gap`, `column-gap` : la propriété `gap` permet de controler l'espace entre les items 

### Les propriétés pour les items

- `order` : permet de controler l'ordre des items apparaissant dans le container

- `flex-grow` : permet de définir la capacité pour la flex d'un item de grandir si nécessaire

- `flex-shrink` : permet de définir la capacité pour la flex d'un item de rétrécir si nécessaire

- `flex-basis` : définis par défaut la taille d'un élément

- `flex` : super propriété permettant de combiner `flex-grow`, `flex-shrink` et `flex-basis`

- `align-self` : permet le positonnement d'un item en particulier du container

## L'utilisation de GRID

Pour des illustrations des propriétés sur le container ou les items : https://css-tricks.com/snippets/css/complete-guide-grid/

### Les propriétés pour le container

- `display` : définit l'élément comme un container grid

- `grid-template-columns` : définis les colonnes de la grid

- `grid-template-rows` : définis les lignes de la grid

- `grid-template-areas` : définis le template de la grid

- `grid-template` : super propriété combinant `grid-template-columns`, `grid-template-rows` et `grid-template-areas`

- `column-gap`/`row-gap` : spécifies l'espace entre les lignes dans la grid 

- `gap` : super propriété combinant la propriété précédente

- `justify-items` : définit l'alignement de la grid selon l'axe de la ligne

- `align-items` : définit l'alignement de la grid selon l'axe de la colonne

- `place-items` super propriété combinant les propriétés `justify-items` et `align-items`

- `justify-content` : alignement (selon la ligne) de la grid selon le container

- `align-content` : alignement (selon la colonne) de la grid selon le container

- `place-content` : super propriété combinant les propriétés `justify-content` et `align-content`

- `grid-auto-rows`/`grid-auto-columns` : spécifie la taille de grid auto-générée

- `grid-auto-flow` : permet de controler l'auto-emplacement des items de la grid

- `grid` : super propriété combinant `grid-template-rows`, `grid-template-columns`, `grid-template-areas`, `grid-auto-rows`, `grid-auto-columns` et `grid-auto-flow`

### Les propriétés pour les items

- `grid-column-start`/`grid-row-start` : permet d'indiquer l'endroit où commence l'item

- `grid-column-end`/`grid-row-end` : permet d'indiquer l'endroit où se finit l'item

- `grid-column` : super propriété combinant `grid-column-start` et `grid-column-end`

- `grid-row` : super propriété combinant `grid-row-start` et `grid-row-end`

- `grid-arae` : permet de nommer un item pour qu'il soit référencé par un template créé avec `grid-template-areas`. Cette propriété peut également être un raccouci pour `grid-column-start`/`grid-row-start`/`grid-column-end`/`grid-row-end`

- `justify-self` : aligne un item à l'intérieur de la cellule suivant l'axe de la ligne

- `align-self` : aligne un item à l'intérieur de la cellule suivant l'axe de la colonne

- `place-self` : propriété combinant `justify-self` et `align-self`

Une cheatsheet interactive sur le CSS se trouve [ICI](https://htmlcheatsheet.com/css/)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)
