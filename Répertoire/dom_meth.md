# Les méthodes pour la manipulation du DOM

Voici les différentes méthodes pour manipuler le DOM. On peut retrouver les méthodes pour l'interface `document.`, `node.` et `element.`

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur ces liens pour [l'interface document](https://developer.mozilla.org/fr/docs/Web/API/Document), [l'interface node](https://developer.mozilla.org/fr/docs/Web/API/Node) et [l'interface element](https://developer.mozilla.org/fr/docs/Web/API/Element).

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

# Les méthodes de l'interface `Document`

- `document.adoptNode()` : Adopte un noeud. Le noeud (et son sous-arbre) est supprimé du document dans lequel il se trouve (le cas échéant) et son ownerDocument (document propriétaire) est remplacé par le document en cours. Le noeud peut ensuite être inséré dans le document en cours.

```
node = document.adoptNode(externalNode);
```

- `document.append()` : La méthode document.append() insère un ensemble d'objets Node ou d'objets DOMString après le dernier enfant du document. Cette méthode ajoute un enfant à un document. Pour ajouter un élément arbitraire dans l'arbre, voir Element.append().

```
append(...nodesOrDOMStrings)

```

- `document.close()` : La méthode document.close() termine l'écriture dans un document, ouvert avec document.open(). 

```
document.close();
```

- `document.createAttribute()` : La méthode Document.createAttribute() crée un nouveau nœud d'attribut et le renvoie. L'objet a créé un noeud implémentant l'interface Attr. Le DOM n'impose pas le type d'attribut à ajouter à un élément particulier de cette manière.

```
attribut = document.createAttribute(nom)
```

- `document.createCDATASection()` : La méthode document.createCDATASection() crée un nouveau noeud de [section CDATA](https://developer.mozilla.org/fr/docs/Web/API/CDATASection) et le renvoie.

```
CDATASectionNode = document.createCDATASection(data)
```

- `document.createComment()` : La méthode document.createComment() crée et retourne un nouveau noeud de type commentaire.

```
CommentNode = document.createComment(data)
```

- `document.createDocumentFragment()` : Crée un nouvel objet vide de type [DocumentFragment](https://developer.mozilla.org/fr/docs/Web/API/DocumentFragment).

```
let fragment = document.createDocumentFragment();
```

- `document.createElement()` : Dans un document HTML, la méthode document.createElement() crée un élément HTML du type spécifié par tagName ou un HTMLUnknownElement si tagName n’est pas reconnu.

```
let element = document.createElement(tagName[, options]);
```

- `document.createElementNS()` : Crée un élément avec l'URI de l'espace de noms spécifié et un nom qualifié. Pour créer un élément sans spécifier d'URI d'espace de noms, utilisez la méthode createElement.

```
let element = document.createElementNS(namespaceURI, qualifiedName[, options]);
```

- `document.createEvent()` : Crée un event du type spécifié. L'objet retourné doit être intialisé et peut être passé ensuite à element.dispatchEvent.

```
Crée un event du type spécifié. L'objet retourné doit être intialisé et peut être passé ensuite à element.dispatchEvent.
```

- `document.createExpression()` : Cette méthode compile une [XPathExpression](https://developer.mozilla.org/fr/docs/Web/API/XPathExpression) qui peut ensuite être utilisée pour des évaluations (répétées).

```
xpathExpr = document.createExpression(xpathText, namespaceURLMapper);
```

- `document.createNodeIterator()` : Renvoie un nouvel objet [NodeIterator](https://developer.mozilla.org/fr/docs/Web/API/NodeIterator).

```
let nodeIterator = document.createNodeIterator(root, whatToShow, filter);

```

- `document.createNSResolver()` : Crée un XPathNSResolver qui résout les espaces de noms en respectant les définitions dans la portée pour un noeud spécifié.

```
nsResolver = document.createNSResolver(node);
```

- `document.createProcessingInstruction()` : La méthode document.createProcessingInstruction() crée un nouveau noeud d'[instruction de traitement](https://developer.mozilla.org/fr/docs/Web/API/ProcessingInstruction) et le renvoie.

```
Processing instruction node = document.createProcessingInstruction(target, data)
```

- `document.createRange()` : Retourne un objet [Range](https://developer.mozilla.org/fr/docs/Web/API/Range).

```
range = document.createRange();
```

- `document.createTextNode()` : Crée un nouveau nœud de texte.

```
let text = document.createTextNode(données);
```

- `document.createTreeWalk()` : La méthode de création Document.createTreeWalker() renvoie un nouvel objet [TreeWalker](https://developer.mozilla.org/fr/docs/Web/API/TreeWalker).

```
treeWalker = document.createTreeWalker(root, whatToShow, filter, entityReferenceExpansion);
```

- `document.elementFromPoint()` : Renvoie l'élément visible au point donné, spécifié relativement au point supérieur gauche visible dans le document.

```
element = document.elementFromPoint(x,y);
```

- `document.evaluate()` : La méthode evaluate() renvoie un [XPathResult](https://developer.mozilla.org/en-US/docs/Web/API/XPathResult)  basé sur une expression XPath et d'autres paramètres donnés.

```
let xpathResult = document.evaluate(
    xpathExpression,
    contextNode,
    namespaceResolver,
    resultType,
    result
);
```

- `document.exitFullscreen()` : La méthode Document.exitFullscreen() extrait le document du mode plein écran ; elle est utilisée pour inverser les effets d'un appel au mode plein écran réalisé avec la méthode Element.requestFullscreen().

```
document.exitFullscreen();
```

- `document.exitPictureInPicture()` : La méthode du document exitPictureInPicture() demande qu'une vidéo contenue dans ce document, qui est actuellement flottante, soit retirée du mode image dans l'image, rétablissant ainsi l'état précédent de l'écran. Cela annule généralement les effets d'un appel précédent à HTMLVideoElement.requestPictureInPicture(). 

```
exitPromise = document.exitPictureInPicture();
```

- `document.getElementById()` : La méthode getElementById() de Document renvoie un objet Element représentant l'élément dont la propriété id correspond à la chaîne de caractères spécifiée. Étant donné que les ID d'élément doivent être uniques, s'ils sont spécifiés, ils constituent un moyen utile d'accéder rapidement à un élément spécifique.

```
let element = document.getElementById(id);
```

- `document.getElementsByClassName()` : Renvoie un objet de type tableau de tous les éléments enfants qui ont tous les noms de classe donnés. Lorsqu'il est appelé sur l'objet document, le document complet est recherché, y compris le nœud racine. Vous pouvez également appeler getElementsByClassName () sur n'importe quel élément; il retournera uniquement les éléments qui sont les descendants de l'élément racine spécifié avec les noms de classes donnés.

```
let elements = document.getElementsByClassName(names);
```

- `document.getElementsByName()` : Renvoie une liste des éléments portant un name donné dans le document (X)HTML. 

```
elements = document.getElementsByName(name)
```

- `document.getElementsByTagName()` : Renvoie une HTMLCollection des éléments avec le nom de balise donné. Le document complet est recherché, y compris le nœud racine. Le HTMLCollection renvoyée est en direct, ce qui signifie qu'elle se met à jour automatiquement pour rester synchronisée avec l'arborescence DOM sans avoir à rappeler document.getElementsByTagName ().

```
let elements = document.getElementsByTagName(name);
```

- `document.getElementsByTagNameNS()` : Renvoie une liste d'éléments avec la balise de nom donnée appartenant à l'espace de noms donné. Le document complet est recherché, y compris le noeud racine.

```
elements = document.getElementsByTagNameNS(namespace,name)
```

- `document.getSelection()` : Cette méthode fonctionne de manière identique à la méthode Window.getSelection() ; elle renvoie un objet Selection représentant le texte actuellement sélectionné dans le document.

- `document.hasFocus()` : La méthode Document.hasFocus() retourne une valeur Boolean true (vrai) indiquant si le document ou tout élément à l'intérieur du document a le focus. Cette méthode peut être utilisée pour déterminer si l'élément actif d'un document a le focus.

```
focused = document.hasFocus();
```

- `document.hasStorageAccess()` : La méthode document.hasStorageAccess() renvoie une Promise qui se résout en une valeur booléenne indiquant si le document a accès à son stockage.

```
let promise = document.hasStorageAccess();
```

- `document.importNode()` : La méthode document.importNode() crée une nouvelle copie du Node ou DocumentFragment spécifié à partir d'un autre document, afin qu'il puisse être inséré dans le document actuel. Il n'est pas encore inclus dans l'arbre des documents; Pour ce faire, vous devez appeler une méthode telle que appendChild () ou insertBefore ().

```
let node = document.importNode(externalNode, deep);
```

- `document.open()` : La méthode document.open() ouvre un document pour l'écriture.

```
document.open();
```

- `document.querySelector()` : La méthode querySelector() de l'interface Document retourne le premier Element dans le document correspondant au sélecteur - ou groupe de sélecteurs - spécifié(s), ou null si aucune correspondance n'est trouvée.

```
element = document.querySelector(sélecteurs);
```

- `document.querySelectorAll()` : La méthode querySelectorAll() de Element renvoie une NodeList statique représentant une liste des éléments du document qui correspondent au groupe de sélecteurs spécifiés.

```
elementList = parentNode.querySelectorAll(selectors);
```

- `document.releaseCapture()` : Libère la capture de la souris si elle est actuellement activée (bouton gauche enfoncé) sur un élément de ce document. L'activation de la capture de la souris sur un élément se fait en appelant element.setCapture().

```
document.releaseCapture()
```

- `document.replaceChild()` : La méthode document.replaceChildren() remplace les enfants existants d'un document par un nouvel ensemble d'enfants spécifié. 

```
replaceChildren(...nodesOrDOMStrings)
```

- `document.write()` : Écrit une chaîne de texte dans un document ouvert par document.open().

```
document.write(balisage);
```

- `document.writeIn()` : Écrit une chaine de caractères suivie d'un retour de ligne.

```
document.writeln(ligne);
```


[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

# Les méthodes de l'interface `Node`

- `node.appendChild()` : La méthode Node.appendChild() ajoute un nœud à la fin de la liste des enfants d'un nœud parent spécifié. Si l'enfant donné est une référence à un nœud existant dans le document, appendChild() le déplace de sa position actuelle vers une nouvelle position (il n'est pas nécessaire de supprimer le noeud sur son noeud parent avant de l'ajouter à un autre)

```
let elementAjoute = element.appendChild(enfant);
```

- `node.cloneNode()` : La méthode Node.cloneNode() renvoie une copie du nœud sur lequel elle a été appelée.

```
let dupNode = node.cloneNode([deep]);
```

- `node.compareDocumentPosition()` : La méthode node.compareDocumentPosition() compare la position du noeud courant par rapport à un autre noeud dans tout autre document.

```
node.compareDocumentPosition( otherNode )
```

- `node.contains()` : La méthode node.contains() renvoie une valeur Boolean (booléenne) indiquant si un nœud est un descendant d'un nœud donné, c'est-à-dire le nœud lui-même, l'un de ses enfants directs (childNodes), l'un des enfants directs des enfants, et ainsi de suite.

```
document.writeln(ligne);
```

- `node.getRoodNode()` : La méthode getRootNode() de l'interface Node renvoie le contexte de la racine de l'objet, qui peut optionnellement inclure la racine "shadow" si elle est disponible.

```
let root = node.getRootNode(options)
```

- `node.hasChildNode()` : La méthode Node.hasChildNodes() renvoie un Boolean indiquant si le noeud actuel possède des nœuds enfants ou non.

```
bool = node.hasChildNodes();
```

- `node.insertBefore()` : La méthode Node.insertBefore() insère un nœud avant un nœud de référence en tant qu'enfant d'un nœud parent spécifié.

```
let insertedNode = parentNode.insertBefore(newNode, referenceNode);
```

- `node.isDefaultNamespace()` : La méthode Node.isDefaultNamespace() accepte un URI d'espace de nom comme argument et renvoie un Boolean (booléen) avec une valeur true (vrai) si l'espace de nom est celui par défaut du noeud donné ou false (faux) sinon.

```
result = node.isDefaultNamespace(namespaceURI)
```

- `node.isEqualNode()` : La méthode Node.isEqualNode() permet de tester l'égalité entre deux éléments du DOM. Deux noeuds sont équivalents s'ils ont le même type, les mêmes caractéristiques de définition (ID, nombre d'enfants et autres), des attributs qui correspondent etc. L'ensemble spécifique de points des données qui doit correspondre letie en fonction des types de nœuds.

```
let isEqualNode = node.isEqualNode(otherNode);
```

- `node.isSameNode()` : La méthode Node.isSameNode() teste si deux noeuds sont identiques, c'est-à-dire, s'ils font référence au même objet.

```
let isSameNode = node.isSameNode(other);
```


- `node.lookupNamespaceURI()` : La méthode Node.lookupNamespaceURI() accepte un préfixe et renvoie l'URI de l'espace de nom associé avec lui sur le noeud donné s'il le trouve (et null sinon). La fourniture de null pour le préfixe renverra l'espace de nom par défaut.

- `node.lookupPrefix()` : La méthode Node.lookupPrefix() renvoie une DOMString (chaîne de caractères) contenant le préfixe d'un URI d'un espace de nom donné, s'il est présent, et null sinon. Quand plusieurs préfixes sont possibles, le résultat dépend de l'implémentation.

- `node.normalize()` : Place le nœud spécifié et tout son sous-arbre dans une forme « normale ». Dans un sous-arbre normalisé, aucun nœud texte n'est vide et il n'y a pas de nœuds texte adjacents.

```
élément.normalize();
```


- `node.removeChild()` : La méthode Node.removeChild() retire un nœud enfant de l'arbre DOM et retourne le nœud retiré.

```
let oldChild = node.removeChild(child);
```

- `node.replaceChild()` : La méthode Node.replaceChild() remplace un nœud enfant du noeud spécifié par un autre nœud.

```
replacedNode = parentNode.replaceChild(newChild, oldChild);
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

# Les méthodes de l'interface `Element`

- `element.animate()` : La méthode animate() de l'interface Element est un raccourci permettant de créer un nouvel objet Animation, de l'appliquer à un élément puis de la jouer. Elle retourne l'instance Animation alors créée.

```
animate(keyframes, options);
```

- `element.getAttribute()` : getAttribute renvoie la valeur d'un attribut donné de l'élément spécifié. Si l'attribut n'existe pas, la valeur renvoyée sera soit null soit "" (une chaine vide).

```
let attribut = element.getAttribute(nom_attribut)
```

- `element.getAttributeNames()` : Element.getAttributeNames() renvoie les noms des attributs de l'élément sous la forme d'un Array (tableau) de chaînes de caractères. Si l'élément n'a pas d'attributs, il retourne un tableau vide.

```
let attributeNames = element.getAttributeNames();
```

- `element.getAttributeNode()` : Renvoie le nœud d'attribut spécifié pour l'élément courant, en tant que noeud Attr.

```
let attrNode = element.getAttributeNode(attrName);
```

- `element.removeAttribute()` : La méthode removeAttribute(), rattachée à l'interface Element, supprime l'attribut ayant le nom indiqué de l'élément.

```
element.removeAttribute(nomAttribut);
```

- `element.removeAttributeNode()` : removeAttributeNode enlève l'attribut spécifié de l'élément courant.

```
removedAttr =element.removeAttributeNode(attributeNode)
```

- `element.setAttribute()` : Ajoute un nouvel attribut ou change la valeur d'un attribut existant pour l'élément spécifié. Si l'attribut existe déjà, la valeur est mise à jour ; sinon, un nouvel attribut est ajouté avec le nom et la valeur spécifiés.

```
Element.setAttribute(name, value);
```

- `element.setAttrubiteNode()` : setAttributeNode``() ajoute un nouveau nœud Attr à l'élément courant.

```
let replacedAttr = element.setAttributeNode(attribute);
```

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)