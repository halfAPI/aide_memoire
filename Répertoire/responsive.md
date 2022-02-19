# Le responsive web

L'idée du responsive est que la page web s'adapte en fonction de la taille de l'écran. 

![](https://cdn.mos.cms.futurecdn.net/7vpUPMSbPfhxiUNYj5XnE6.jpg)

[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

On utilise les `media queries` afin de mentionner comment la page doit se comportée suite à un changement de taille de l'écran. 

```
@media (taille1) and (taile2) {
    //instruction en css
}
```

Si par exemple, on veut que la taille des paragraphes changent de tailles entre 780px et 540px, on écrit :

```
@media (min-width: 540px) and (max-width: 780px){
    p {
        font-size : 18px;
    }
}
```

On peut également combiner les infos, du style, "un écran dont la résolution est comprise entre 200px et 640px" :

```
@media screen and (min-width: 200px) and (max-width: 640px) {
  .bloc {
    display:block;
    clear:both;
  }
}
```

Il existe des gammes de taille en fonction de l'écran que l'on vise. On peut simplement prendre ces différentes mesures mais on peut également les changer ou les adapter : 

```
 /* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {...}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {...}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {...}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {...}

/* Extra large devices (large laptops and desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {...} 
```
[Retour vers le README](https://github.com/CalcagnoLoic/aide_memoire/blob/main/README.md)

