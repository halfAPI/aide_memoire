# Les attributs ARIA et l'accessibilité

Les attributs ARIA sont nombreux et il est difficile de tous les connaitre. Cette page propose la liste des 80 rôles pour la nature d'un élément ainsi que les autres attributs possible pour donner de l'informations quant à l'action et l'état d'un élément. 

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

## Liste des rôles ARIA [nature de l'élément]

Il existe différentes catégories de rôles : 

* Les rôles de structure de document : il s'agit des rôles utilisés pour fournir une description structurelle d'une section du contenu.

* Les rôles des widget : il s'agit des rôles utilisés pour définir des modèles interactifs sur des widgets.

* Les rôles de points de repères : il s'agit des rôles permettant d'identifier l'organisation et la structure d'une page web. 

* Les rôles 'Live Region' : il s'agit des rôles utilisés pour définir les éléments dont le contenu sera modifié dynamiquement.

* Les rôles de fenêtre : il s'agit des rôles utilisés pour définir des fenêtres de dialogue, d'alerte, etc.

* Les rôles abstrait : il s'agit des rôles qui sont uniquement utilisés par les navigateurs afin d'organiser le document. **NE SONT PAS UTILISES PAR LES DEVS**

Voici la liste des rôles : 

- `ARIA:role = "alert"` : informations importante et généralement urgentes

- `ARIA:role = "alertdialog"` : utilisation sur les boite de dialogue d'alerte interrompant le flux de travail d'un utilisateur 

- `ARIA:role = "application"` : rôle définissant qu'un élément et tout ses enfants sont traités comme une application de bureau et que l'interprétation HTML ne doit pas être utilisée

- `ARIA:role = "article"` :  indique une section d'une page qui pourrait facilement être autonome sur une page, dans un document ou sur un site Web

- `ARIA:role = "banner"` : consiste à définir une en-tête de site global

- `ARIA:role = "button"` : pour les éléments cliquables qui déclenchent une réponse lorsqu'ils sont activés par l'utilisateur. **L'utilisation de la balise `<button>` est recommandée à la place de ce rôle**

- `ARIA:role = "cell"` : identifie un élément comme étant une cellule dans un tableau

- `ARIA:role = "checkbox"` : pour les contrôles interactifs cochables

- `ARIA:role = "columnheader"` : identifie un élément comme étant une cellule dans une ligne contenant des informations d'en-tête pour une colonne

- `ARIA:role = "combobox"` : pour l'entrée qui contrôle un autre élément qui peut apparaître dynamiquement pour aider l'utilisateur à définir la valeur de l'entrée

- `ARIA:role = "command"` : définit un widget qui exécute une action mais ne reçoit pas de données d'entrée

- `ARIA:role = "comment"` : désigne sémantiquement un commentaire

- `ARIA:role = "complementary"` :  utilisé pour désigner une section de support qui se rapporte au contenu principal, mais qui peut être autonome lorsqu'elle est séparée. **L'utilisation de la balise `<aside>` est recommandée à la place de ce rôle**

- `ARIA:role = "composite"` :  indique un widget qui peut contenir des descendants navigables (role abstrait)

- `ARIA:role = "contentinfo"` : définit un pied de page, contenant des informations d'identification telles que des informations de copyright

- `ARIA:role = "definition"` :  indique que l'élément est une définition d'un terme ou d'un concept

- `ARIA:role = "dialog"` :  utilisé pour baliser une boîte de dialogue ou une fenêtre d'application HTML qui sépare le contenu ou l'interface utilisateur du reste de l'application ou de la page Web

- `ARIA:role = "directory"` : pour une liste de références aux membres d'un groupe, comme une table des matières statique

- `ARIA:role = "document"` : le rôle est pour le contenu focalisable dans des widgets ou des applications

- `ARIA:role = "document structural"` : les rôles de structure de document ARIA sont utilisés pour fournir une description structurelle d'une section de contenu.

- `ARIA:role = "feed"` : permet aux lecteurs d'écran d'utiliser le curseur de lecture du mode navigation pour lire et faire défiler un flux de contenu riche qui peut continuer à défiler indéfiniment en chargeant davantage de contenu au fur et à mesure que l'utilisateur lit

- `ARIA:role = "figure"` : utilisé pour identifier une figure à l'intérieur du contenu de la page où la sémantique appropriée n'existe pas déjà

- `ARIA:role = "form"` : utilisé pour identifier un groupe d'éléments sur une page qui fournissent des fonctionnalités équivalentes à un formulaire HTML

- `ARIA:role = "generic"` :  crée un élément conteneur sans nom qui n'a pas de signification sémantique en soi
 
- `ARIA:role = "grid"` : pour un widget qui contient une ou plusieurs rangées de cellules

- `ARIA:role = "gridcell"` : utilisé pour créer une cellule dans une grid 

- `ARIA:role = "group"` : identifie un ensemble d'objets d'interface utilisateur qui n'est pas destiné à être inclus dans un résumé de page ou une table des matières par des technologies d'assistance

- `ARIA:role = "heading"` : définit cet élément comme un titre vers une page ou une section

- `ARIA:role = "img"` : peut être utilisé pour identifier plusieurs éléments à l'intérieur du contenu de la page qui doivent être considérés comme une seule image

- `ARIA:role = "input"` : type générique de widget qui permet la saisie de l'utilisateur

- `ARIA:role = "landmark"` : superclasse abstraite pour les valeurs de rôle aria pour les sections de contenu qui sont suffisamment importantes pour que les utilisateurs veuillent probablement pouvoir y naviguer directement

- `ARIA:role = "link"` : fournit une référence interactive à une ressource

- `ARIA:role = "list"` : peut être utilisé pour identifier une liste d'éléments

- `ARIA:role = "listbox"` : utilisé pour les listes à partir desquelles un utilisateur peut sélectionner un ou plusieurs éléments qui sont statiques

- `ARIA:role = "listitem"` : peut être utilisé pour identifier un élément dans une liste d'éléments

- `ARIA:role = "log"` : utilisé pour identifier un élément qui crée une région active où de nouvelles informations sont ajoutées dans un ordre significatif et où les anciennes informations peuvent disparaître

- `ARIA:role = "main"` : utilisé pour indiquer le contenu principal d'un document

- `ARIA:role = "mark"` : désigne le contenu qui est marqué ou mis en évidence à des fins de référence ou de notation

- `ARIA:role = "marquee"` : un type de région dynamique contenant des informations non essentielles qui changent fréquemment

- `ARIA:role = "math"` : indique que le contenu représente une expression mathématique

- `ARIA:role = "menu"` : indique un menu

- `ARIA:role = "menubar"` : indique la barre du menu

- `ARIA:role = "menuitem"` : indique un item dans le menu

- `ARIA:role = "menuitemcheckbox"` : indique un menu avec un état cochable

- `ARIA:role = "menuitemradio"` : indique un menuitem vérifiable dans un ensemble d'éléments ayant le même rôle, dont un seul peut être vérifié à la fois.

- `ARIA:role = "meter"` : utilisé pour identifier un élément utilisé comme compteur

- `ARIA:role = "navigation"` : utilisé pour identifier les principaux groupes de liens utilisés pour naviguer sur un site Web ou le contenu d'une page

- `ARIA:role = "none"` : synonyme de `role = "presentation"` ; ils suppriment tous deux la sémantique ARIA implicite d'un élément qui est exposée à l'arbre d'accessibilité 

- `ARIA:role = "note"` : suggère une section dont le contenu est entre parenthèses ou accessoire au contenu principal

- `ARIA:role = "option"` : utilisé pour les éléments sélectionnables dans un fichier listbox

- `ARIA:role = "presentation"` : synonyme de `role = "none"` ; ils suppriment tous deux la sémantique ARIA implicite d'un élément qui est exposée à l'arbre d'accessibilité 

- `ARIA:role = "progressbar"` : définit un élément qui affiche l'état d'avancement des tâches

- `ARIA:role = "radio"` : fait partie d'un groupe de boutons cochables

- `ARIA:role = "range"` :  type générique de rôle de structure représentant une plage de valeurs

- `ARIA:role = "region"` : utilisé pour identifier les zones du document que l'auteur juge importantes

- `ARIA:role = "roletype"` : rôle abstrait , est le rôle de base dont héritent tous les autres rôles ARIA

- `ARIA:role = "row"` : ne rangée de cellules dans un tableau

- `ARIA:role = "rowgroup"` : un groupe de lignes dans un tableau

- `ARIA:role = "rowheader"` : une cellule contenant des informations d'en-tête pour une ligne dans un tableau

- `ARIA:role = "scrollbar"` : définit un objet graphique qui contrôle le défilement du contenu à l'intérieur d'une zone de visualisation, indépendamment du fait que le contenu soit entièrement affiché dans la zone de visualisation

- `ARIA:role = "search"` : utilisé pour identifier la fonctionnalité de recherche

- `ARIA:role = "section"` : rôle de superclasse pour les composants de confinement structurel pouvant faire l'objet d'un rendu

- `ARIA:role = "searchbox"` : indique un type de zone de texte destiné à spécifier des critères de recherche.

- `ARIA:role = "sectionhead"` : rôle de superclasse pour les étiquettes ou les résumés du sujet de sa section associée

- `ARIA:role = "select"` : rôle de superclasse pour les widgets de formulaire qui permet à l'utilisateur d'effectuer des sélections à partir d'un ensemble de choix

- `ARIA:role = "separator"` : ndique que l'élément est un séparateur qui sépare et distingue des sections de contenu ou des groupes d'éléments de menu. Le rôle ARIA implicite de l' hrélément de coupure thématique natif est separator

- `ARIA:role = "slider"` : définit une entrée dans laquelle l'utilisateur sélectionne une valeur dans une plage donnée

- `ARIA:role = "status"` : définit une région active contenant des informations consultatives pour l'utilisateur qui ne sont pas suffisamment importantes pour être un alert

- `ARIA:role = "structure"` : rôle est pour les éléments structurels du document

- `ARIA:role = "suggestion"` : rôle de point de repère, désigne sémantiquement une seule modification proposée à un document modifiable

- `ARIA:role = "switch"` : fonctionnellement identique au rôle de case à cocher , sauf qu'au lieu de représenter les états "coché" et "non coché", qui ont une signification assez générique, le switchrôle représente les états "activé" et "désactivé"

- `ARIA:role = "tab"` : indique un élément interactif à l'intérieur d'un `tablist` qui, lorsqu'il est activé, affiche son `tabpanel`

- `ARIA:role = "table"` : identifie l'élément contenant le rôle comme ayant une structure de table

- `ARIA:role = "tablist"` : indique une liste d'éléments, qui sont des références à des éléments de `tabpanel`.

- `ARIA:role = "tabpanel"` : indique un conteneur pour les ressources associées à un onglet, où chaque onglet est contenu dans un `tablist`.

- `ARIA:role = "term"` : peut être utilisé pour un mot ou une phrase avec un correspondant facultatif definition

- `ARIA:role = "textbox"` : utilisé pour identifier un élément qui permet la saisie de texte de forme libre. Dans la mesure du possible, plutôt que d'utiliser ce rôle, utilisez un élément `input` avec `type="text"` , pour une entrée sur une seule ligne, ou un élément `textarea`   pour une entrée sur plusieurs lignes

- `ARIA:role = "timer"` : indique aux technologies d'assistance qu'un élément est un compteur numérique

- `ARIA:role = "toolbar"` : définit l'élément conteneur comme une collection de boutons de fonction couramment utilisés ou de contrôles représentés sous une forme visuelle 

- `ARIA:role = "tooltip"` : bulle de texte contextuelle qui affiche une description d'un élément qui apparaît au survol du pointeur ou au clavier

- `ARIA:role = "tree"` : type de liste qui peut contenir des groupes imbriqués de sous-niveaux qui peuvent être réduits et développés.

- `ARIA:role = "treegrid"` : grille dont les rangées peuvent être développées et réduites de la même manière que pour un arbre.

- `ARIA:role = "treeitem"` : élément optionnel d'un arbre. Il s'agit d'un élément d'un arbre qui peut être développé ou réduit s'il contient un groupe de sous-niveaux d'éléments `treeitem`.

- `ARIA:role = "widget"` : un composant interactif d'une interface utilisateur graphique (GUI)

- `ARIA:role = "window"` : définit une fenêtre de navigateur ou d'application
 
## Liste des attributs aria [action et état de l'élément]

Seul l'indication de l'utilisation des attributs est noté. Pour savoir quelles sont les valeurs possibles à ajouter à chacun des attributs, voici la liste desdits attribus avec les liens vers la documentation pour chacun d'eux : https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques 

### Attributs des widgets

- `aria-autocomplete` : indique si la saisie de texte peut déclencher l'affichage d'une ou plusieurs prédictions de la valeur prévue par l'utilisateur pour une `combobox`, une `searchbox` ou une `textbox`, et précise comment les prédictions seront présentées si elles sont faites.

- `aria-checked` :  indique l'état actuel "coché" des cases à cocher, des boutons radio et d'autres widgets.

- `aria-current` : indique que cet élément représente l'élément actuel dans un conteneur ou un ensemble d'éléments connexes

- `aria-disabled` : indique que l'élément est perceptible mais désactivé, et qu'il n'est donc pas modifiable ou utilisable d'une autre manière

- `aria-errormessage` : identifie l'élément qui fournit un message d'erreur pour cet objet

- `aria-expanded` : défini sur un élément pour indiquer si un contrôle est développé ou réduit, et si ses éléments enfants sont affichés ou masqués

- `aria-haspopup` : indique la disponibilité et le type d'élément popup interactif qui peut être déclenché par l'élément sur lequel l'attribut est défini

- `aria-hidden` : indique si l'élément est exposé à une API d'accessibilité

- `aria-invalid` : indique que la valeur saisie n'est pas conforme au format attendu par l'application

- `aria-label` : définit une valeur de chaîne qui étiquette un élément interactif

- `aria-level` : définit le niveau hiérarchique d'un élément dans une structure

- `aria-modal` : indique si un élément est modal lorsqu'il est affiché

- `aria-multiline` : indique si une zone de texte accepte plusieurs lignes de saisie ou une seule

- `aria-multiselectable` : indique que l'utilisateur peut sélectionner plus d'un élément parmi les descendants sélectionnables actuels

- `aria-orientation` : indique si l'orientation de l'élément est horizontale, verticale ou inconnue/ambiguë

- `aria-placeholder` : définit une courte indication (un mot ou une courte phrase) destinée à aider l'utilisateur à saisir des données lorsqu'un contrôle de formulaire n'a pas de valeur. L'indication peut être un exemple de valeur ou une brève description du format attendu.

- `aria-pressed` : indique l'état actuel "enfoncé" d'un bouton

- `aria-readonly` : indique que l'élément n'est pas modifiable, mais qu'il est par ailleurs utilisable

- `aria-required` : indique que la saisie de l'utilisateur est requise sur l'élément avant qu'un formulaire puisse être soumis

- `aria-selected` : indique l'état actuel "sélectionné" de divers widgets

- `aria-sort` : indique si les éléments d'un tableau ou d'une grille sont triés par ordre croissant ou décroissant

- `aria-valuemax` : définit la valeur maximale autorisée pour un widget de plage

- `aria-valuemin` : définit la valeur minimale autorisée pour un widget de plage

- `aria-valuenow` : définit la valeur actuelle d'un widget de plage

- `aria-valuetext` : définit l'alternative en texte lisible de `aria-valuenow` pour un widget de plage

### Attributs 'live region'

- `aria-live` : indique qu'un élément sera mis à jour et décrit les types de mises à jour que les agents utilisateurs, les technologies d'assistance et l'utilisateur peuvent attendre de la région en direct

- `aria-relevant` : utilisé dans les régions actives ARIA, l'attribut indique les notifications que l'utilisateur déclenchera lorsque l'arbre d'accessibilité d'une région active sera modifié

- `aria-atomic` : dans les régions active ARIA, l'attribut indique si les technologies d'assistance telles qu'un lecteur d'écran présenteront la totalité ou seulement certaines parties de la région modifiée en fonction des notifications de modification définies par l'attribut `aria-relevant`

- `aria-busy` : utilisé dans les régions actives ARIA, l'attribut indique qu'un élément est en cours de modification et que les technologies d'assistance peuvent vouloir attendre que les modifications soient terminées avant d'informer l'utilisateur de la mise à jour

### Attributs 'glisser-déposer'

- `aria-dropeffect` : indique les fonctions qui peuvent être exécutées lorsqu'un objet glissé est relâché sur la cible de dépôt

- `aria-grabbed` : indique l'état "saisi" d'un élément lors d'une opération de glisser-déposer

### Attributs de relation

- `aria-activedescendant` : identifie l'élément actuellement actif lorsque le focus est sur un widget composite, une `combobox`, une `textbox`, un groupe ou une application

- `aria-colcount` : définit le nombre total de colonnes dans une `table`, une `grid` ou `treegrid` lorsque toutes les colonnes ne sont pas présentes dans le DOM

- `aria-colindex` : définit l'index ou la position de la colonne d'un élément par rapport au nombre total de colonnes dans une `table`, une `grid` ou `treegrid`

- `aria-colspan` : définit le nombre de colonnes couvertes par une cellule ou une cellule de grille dans une `table`, une `grid` ou `treegrid`

- `aria-controls` : identifie l'élément (ou les éléments) dont le contenu ou la présence sont contrôlés par l'élément sur lequel cet attribut est défini

- `aria-describedby` : identifie l'élément (ou les éléments) qui décrit l'élément sur lequel l'attribut est défini

- `aria-details` : identifie l'élément (ou les éléments) qui fournit des informations supplémentaires relatives à l'objet

- `aria-errormessage` : identifie l'élément qui fournit un message d'erreur pour cet objet

- `aria-flowto` : identifie l'élément (ou les éléments) suivant(s) dans un ordre de lecture alternatif du contenu. Cela permet aux technologies d'assistance de remplacer l'ordre de lecture par défaut du document source, à la discrétion de l'utilisateur

- `aria-labelledby` : identifie l'élément (ou les éléments) qui étiquette l'élément auquel il est appliqué

- `aria-owns` : identifie un élément (ou des éléments) afin de définir une relation visuelle, fonctionnelle ou contextuelle entre un parent et ses éléments enfants lorsque la hiérarchie DOM ne peut être utilisée pour représenter la relation

- `aria-posinset` : définit le numéro ou la position d'un élément dans l'ensemble actuel de `listitems` ou `treeitems` lorsque tous les éléments ne sont pas présents dans le DOM

- `aria-rowcount` : définit le nombre total de lignes dans une `table`, une `grid` ou `treegrid`

- `aria-rowindex` : définit la position d'un élément par rapport au nombre total de lignes dans une `table`, une `grid` ou `treegrid`

- `aria-rowspan` : définit le nombre de lignes couvertes par une cellule ou une cellule de grid dans une `table`, une `grid` ou `treegrid`

- `aria-setsize` : définit le nombre d'éléments dans l'ensemble actuel de `listitems` ou `treeitems` lorsque tous les éléments de l'ensemble ne sont pas présents dans le DOM

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)