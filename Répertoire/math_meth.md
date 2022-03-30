# Les méthodes de l'objet global `Math`

Voici les différentes méthodes que l'on peut appliquer à un objet de type `Math`.

Dans cette section, seule les méthodes seront définies. Pour plus d'exemples, rendez-vous sur [ce lien](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Math)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

- `Math.abs()` : La fonction Math.abs() retourne la valeur absolue d'un nombre, c'est-à-dire :

Math.abs ( x ) = | x | =  x si x ≥ 0  ET  - x si x < 0


- `Math.acos()` : La fonction Math.acos() renvoie l'arc cosinus d'une valeur exprimée en radians. Cela est défini par :

∀ x ∊ [ - 1 ; 1 ] , Math.acos ( x ) = arccos ( x ) = le seul y ∊ [ 0 ; π ] tel que cos ( y ) = x 


- `Math.acosh()` : La fonction Math.acosh() renvoie l'arc cosinus hyperbolique d'un nombre.Elle est définie par :

∀ x ≥ 1 , Math.acosh ( x ) = arcosh ( x ) = l'unique y ≥ 0 tel que cosh ( y )

- `Math.asin()` : La fonction Math.asin() renvoie l'arc sinus d'un nombre (en radians). Elle est définie par :

∀ x ∊ [ - 1 ; 1 ] , Math.asin ( x ) = arcsin ( x ) = le seul y ∊ [ $\frac{-π}{2}$ ;  $\frac{π}{2}$ ] tel que sin ( y ) = x 

- `Math.asinh()` : La fonction Math.asinh() renvoie l'arc sinus hyperbolique d'un nombre :

Math.asinh ( x ) = arsinh ( x ) = le seul y tel que sinh ( y ) = x 

- `Math.atan()` : La fonction Math.atan() renvoie l'arc tangente d'un nombre exprimée en radians. Elle est définie par :

Math.atan ( x ) = arctan ( x ) =le seul y ∊ [ $\frac{-π}{2}$ ;  $\frac{π}{2}$ ] tel que tan ( y ) = x 

- `Math.atan2()` : La fonction Math.atan2() renvoie l'arc tangente du quotient de ses arguments, ce qui, pour Math.atan2(y,x), correspond à l'angle plan (exprimé en radians) entre la droite passant par l'origine et le point de coordonnées (x,y).

- `Math.atanh()` : La fonction Math.atanh() renvoie l'arc tangente hyperbolique d'un nombre :

∀ x ∊ ( - 1 , 1 ) , Math.atanh ( x ) = arctanh ( x ) = le seul y tel que tanh ( y ) = x 

- `Math.cbrt()` : La fonction Math.cbrt() renvoie la racine cubique (le nom anglais étant cubic root) d'un nombre :

Math.cbrt( x ) = $\sqrt[3]{x}$ = le seul y tel que y 3 = x 

- `Math.ceil()` : La fonction Math.ceil() retourne le plus petit entier supérieur ou égal au nombre donné.

- `Math.clz32()` : La fonction Math.clz32() renvoie le nombre de zéros de tête dans la représentation binaire sur 32 bits d'un nombre.

- `Math.cos()` : La fonction Math.cos() retourne le cosinus d'un angle dont la valeur est exprimée en radians.

- `Math.cosh()` : La fonction Math.cosh() renvoie le cosinus hyperbolique d'un nombre, défini par :

Math.cosh(x) = $\frac{e^x + e^x}{2}$

- `Math.exp()` : La fonction Math.exp() renvoie l'exponentielle d'un nombre 

- `Math.expm1()` : La fonction Math.expm1() renvoie $e^x$ - 1, avec x l'argument donné et e la base du logarithme nepérien.

- `Math.floor()` : La fonction Math.floor(x) renvoie le plus grand entier qui est inférieur ou égal à un nombre x.

- `Math.fround()` : La fonction Math.fround() renvoie le nombre flottant à précision simple sur 32 bits qui est le plus proche du nombre fourni.

- `Math.hypot()` : La fonction Math.hypot() renvoie la racine carrée de la somme des carrés de ses arguments. On peut également la définir avec la formule suivante :

 Math.hypot ( v 1 , v 2 , … , v n ) = $\sum_{i=1}^{n} v_i^2 = \sqrt{v_1^2+v_2^2 + ... + v_n^2}$

- `Math.imul()` : La fonction Math.imul() renvoie le résultat de la multiplication de deux nombres, calculée avec la représentation sur 32 bits de ces nombres, à la façon du langage C.

- `Math.log()` : La fonction Math.log() renvoie le logarithme naturel (aussi appelé logarithme népérien) d'un nombre, défini par :

∀ x > 0 , Math.log ( x ) = ln ( x ) = le seul y tel que e y = x 

- `Math.log10()` : La fonction Math.log10() renvoie le logarithme en base 10 d'un nombre, donné par la formule :

∀ x > 0 , Math.log10 ( x ) = log 10 ( x ) = l'unique y tel que $10^y$ = x 

- `Math.log1p()` : La fonction Math.log1p() renvoie le logarithme népérien (en base e) d'un nombre +1, donné par la formule :

∀ x > - 1 , Math.log1p ( x ) = ln ( 1 + x ) 

- `Math.log2()` : La fonction Math.log2() renvoie le logarithme en base 2 d'un nombre :

∀ x > 0 , Math.log2 ( x ) = log 2 ( x ) = l'unique y tel que $y^2$ = x 

- `Math.max()` : La fonction Math.max() renvoie le plus grand nombre d'une série de 0 ou plusieurs nombres.

- `Math.min()` : La fonction Math.min() renvoie le plus petit nombre d'une série de 0 ou plusieurs nombres ou bien NaN si au moins un des arguments fourni n'est pas un nombre ou ne peut pas être converti en nombre.

- `Math.pow()` : La fonction Math.pow() renvoie un nombre à une certaine puissance, c'est-à-dire `base^exposant`.

- `Math.random()` : La fonction Math.random() renvoie un nombre flottant pseudo-aléatoire compris dans l'intervalle [0, 1[ (ce qui signifie que 0 est compris dans l'intervalle mais que 1 en est exclu) selon une distribution approximativement uniforme sur cet intervalle.

- `Math.round()` : La fonction Math.round() retourne la valeur d'un nombre arrondi à l'entier le plus proche.

- `Math.sign()` : La fonction Math.sign() renvoie le signe d'un nombre et permet de savoir si un nombre est positif, négatif ou nul.

- `Math.sin()` : La fonction Math.sin() renvoie le sinus d'un nombre.

- `Math.sinh()` : La fonction Math.sinh() renvoie le sinus hyperbolique d'un nombre

- `Math.sqrt()` : La fonction Math.sqrt() renvoie la racine carrée d'un nombre. Cette fonction est définie par :

∀ x ≥ 0 , Math.sqrt ( x ) = $\sqrt{x}$ = l'unique y ≥ 0 tel que y² = x 

- `Math.tan()` : La fonction Math.tan() renvoie la tangente d'un nombre exprimant un angle en radians.

- `Math.tanh()` : La fonction Math.tanh() renvoie la tangente hyperbolique d'un nombre définie par :

tanh x = $\frac{sin x}{cos x}$

- `Math.trunc()` : La fonction Math.trunc() retourne la troncature entière d'un nombre en retirant sa partie décimale.

Math.trunc ( x ) = |x| si x ≥ 0  ET |x| si x < 0 

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)