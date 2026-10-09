Je vais t'expliquer les principales valeurs de `display` en CSS, simplement, avec des dessins et des exemples que tu peux tester dans VS Code.

# 1. `display` en CSS, c'est quoi ?

`display` permet de choisir comment un élément HTML se comporte et prend sa place dans la page.

Les valeurs les plus importantes sont :

* `block`

* `inline`

* `inline-block`

* `none`

* `flex`

* `grid`

## 2. `display: block`

Un élément `block` prend généralement toute la largeur disponible et commence sur une nouvelle ligne.

`div 1` — toute la ligne

`div 2` — nouvelle ligne

`div 3` — nouvelle ligne

Exemples d'éléments généralement `block` : `div`, `p`, `h1`, `section`.

HTML

```
<div>Premier</div>
<div>Deuxième</div>
```

CSS

```
div {
    display: block;
}
```

Résultat : les deux `div` sont l'un sous l'autre.

## 3. `display: inline`

Un élément `inline` reste sur la même ligne que les autres éléments, si l'espace est suffisant.

Home

About

Contact

Les éléments restent côte à côte.

Exemples : `span`, `a`, `strong`, `em`.

HTML

```
<a href="#">Home</a>
<a href="#">Inscription</a>
```

CSS

```
a {
    display: inline;
}
```

Résultat : les liens restent sur la même ligne.

Attention : sur un élément `inline`, `width` et `height` ne fonctionnent pas comme sur un élément `block`. Les marges et paddings verticaux ne modifient pas non plus la disposition des lignes de la même façon.

## 4. `display: inline-block`

C'est un mélange de `inline` et `block` :

* Comme `inline` : les éléments restent sur la même ligne.

* Comme `block` : tu peux définir `width`, `height`, `margin` et `padding`.

Bouton 1

Bouton 2

Bouton 3

Les blocs sont côte à côte, avec une largeur et une hauteur.

CSS

```
a {
    display: inline-block;
    width: 120px;
    height: 40px;
    padding: 10px;
}
```

Quand l'utiliser ? Pour des liens qui ressemblent à des boutons, par exemple dans une navigation.

## 5. `display: none`

L'élément disparaît complètement de la page, et l'espace qu'il occupait est libéré.

CSS

```
.menu {
    display: none;
}
```

C'est utile pour masquer un menu ou un élément.

À ne pas confondre avec `visibility: hidden`, qui cache l'élément mais conserve son espace.

## 6. `display: flex`

`flex` permet d'organiser facilement des éléments dans un conteneur, généralement sur une ligne par défaut.

Home

About

Contact

Les éléments sont alignés horizontalement.

CSS

```
nav {
    display: flex;
    gap: 20px;
    justify-content: center;
    align-items: center;
}
```

À retenir :

* `gap` : espace entre les éléments.

* `justify-content` : organisation sur l'axe principal.

* `align-items` : alignement sur l'axe secondaire.

Pour ta navigation YouCode, `display: flex` est très pratique.

## 7. `display: grid`

`grid` permet d'organiser les éléments en lignes et en colonnes.

1

2

3

4

5

6

Six éléments organisés en trois colonnes.

CSS

```
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
}
```

* `grid-template-columns` : définit les colonnes.

* `repeat(3, 1fr)` : crée trois colonnes de largeur égale.

* `gap` : espace entre les éléments.

Pratique pour une galerie d'images ou les cartes d'un site.

## 8. Tableau récapitulatif

| Valeur         | Comportement                       | Utilisation            |
| -------------- | ---------------------------------- | ---------------------- |
| `block`        | Nouvelle ligne, largeur disponible | `div`, `section`       |
| `inline`       | Reste dans la ligne                | Texte, liens           |
| `inline-block` | Même ligne + largeur/hauteur       | Boutons                |
| `none`         | Disparaît sans garder son espace   | Masquer un élément     |
| `flex`         | Organisation flexible              | Navigation, alignement |
| `grid`         | Organisation en lignes et colonnes | Galerie, cartes        |

## 9. Petit exercice pour vérifier ta compréhension

Question : tu veux afficher trois liens `Home`, `About` et `Contact` côte à côte dans ta `nav`, et les centrer facilement. Quelle valeur de `display` choisis-tu ?

`display: block`

`display: inline`

`display: flex`

`display: none`

Conseil : commence par bien comprendre `block`, `inline` et `inline-block`, puis entraîne-toi avec `flex`, que tu utiliseras souvent dans ton projet Campus Life.


















On va apprendre `display: inline-block` et les propriétés CSS qui fonctionnent avec lui, sans utiliser Flexbox. Avec des exemples simples pour ton projet Campus Life.

# 1. `display: inline-block`

Il combine deux comportements :

* `inline` : les éléments restent côte à côte.

* `block` : tu peux définir une largeur et une hauteur.

Exemple HTML :

HTML

```
<div class="box">Home</div>
<div class="box">About</div>
<div class="box">Contact</div>
<div class="box">Inscription</div>
```

CSS

```
.box {
    display: inline-block;
    width: 100px;
    height: 60px;
    background-color: #C7F64A;
}
```

Home

About

Contact

Inscription

Résultat : les blocs se placent côte à côte si l'espace est suffisant.

# 2. `width` et `height`

Ces propriétés définissent les dimensions de chaque bloc.

CSS

```
.box {
    display: inline-block;
    width: 150px;
    height: 80px;
}
```

* `width: 150px;` → largeur de 150 pixels.

* `height: 80px;` → hauteur de 80 pixels.

Tu peux aussi utiliser des pourcentages :

CSS

```
.box {
    display: inline-block;
    width: 23%;
}
```

`23%` signifie 23 % de la largeur du parent.

Pour 4 blocs, `width: 23%` peut convenir si les marges, paddings et espaces ne font pas dépasser la largeur totale.

# 3. `margin` — espace à l'extérieur

`margin` ajoute de l'espace autour du bloc.

CSS

```
.box {
    display: inline-block;
    margin: 10px;
}
```

Home

About

Contact

Le contour représente l'espace extérieur illustré autour de chaque élément.

Les valeurs utiles :

CSS

```
margin: 10px;           /* les 4 côtés */
margin-top: 10px;       /* en haut */
margin-bottom: 10px;    /* en bas */
margin-left: 10px;      /* à gauche */
margin-right: 10px;     /* à droite */
```

Exemple : pour séparer tes 4 `div` horizontalement :

CSS

```
.box {
    display: inline-block;
    margin-right: 20px;
}
```

# 4. `padding` — espace à l'intérieur

`padding` ajoute de l'espace entre le contenu et le bord de son bloc.

CSS

```
.box {
    display: inline-block;
    padding: 20px;
    background-color: #C7F64A;
}
```

Texte

Le padding est l'espace entre le texte et le bord du bloc.

Différence importante :

* `margin` → espace à l'extérieur.

* `padding` → espace à l'intérieur.

# 5. `text-align` — aligner le texte

Pour centrer le texte à l'intérieur de chaque bloc :

CSS

```
.box {
    display: inline-block;
    width: 150px;
    text-align: center;
}
```

Tu peux choisir :

CSS

```
text-align: left;     /* à gauche */
text-align: center;   /* au centre */
text-align: right;    /* à droite */
```

Attention : `text-align` aligne le texte à l'intérieur du bloc. Il ne centre pas le bloc lui-même dans la page.

# 6. `vertical-align` — aligner les blocs verticalement

Quand tes blocs `inline-block` ont des contenus de tailles différentes, leurs alignements peuvent varier.

CSS

```
.box {
    display: inline-block;
    vertical-align: top;
}
```

Valeurs courantes :

CSS

```
vertical-align: top;       /* par le haut */
vertical-align: middle;    /* au milieu */
vertical-align: bottom;    /* par le bas */
```

Cette propriété aide à aligner les blocs entre eux sur la même ligne.

# 7. `background`, `border` et `border-radius`

Ces propriétés décorent tes blocs.

CSS

```
.box {
    display: inline-block;
    width: 150px;
    padding: 15px;
    background-color: #C7F64A;
    border: 2px solid black;
    border-radius: 10px;
}
```

* `background-color` → couleur de fond.

* `border` → bordure.

* `border-radius` → coins arrondis.

# 8. Centrer les blocs sans Flexbox

Pour centrer horizontalement plusieurs éléments `inline-block`, utilise `text-align: center` sur leur parent.

HTML

```
<div class="container">
    <div class="box">Home</div>
    <div class="box">About</div>
    <div class="box">Contact</div>
</div>
```

CSS

```
.container {
    text-align: center;
}

.box {
    display: inline-block;
    width: 120px;
    padding: 15px;
    margin: 5px;
    background-color: #C7F64A;
}
```

Ici, `text-align: center` centre les blocs `inline-block` dans le conteneur.

# 9. La limite à connaître

`inline-block` fonctionne très bien pour mettre plusieurs éléments côte à côte. Mais il ne remplace pas toutes les fonctions de Flexbox.

| Propriété                                | Avec `inline-block`                               |
| ---------------------------------------- | ------------------------------------------------- |
| `width`, `height`                        | Oui                                               |
| `margin`, `padding`                      | Oui                                               |
| `text-align`                             | Oui, sur le parent pour aligner le contenu inline |
| `vertical-align`                         | Oui                                               |
| `background-color`, `border`             | Oui                                               |
| `gap` pour espacer directement les blocs | Non, utilise `margin`                             |
| `align-items`                            | Non                                               |
| `justify-content`                        | Non                                               |

À retenir : pour ton projet, utilise `inline-block` pour mettre tes `div` côte à côte, `margin` pour les séparer, `padding` pour ajouter de l'espace à l'intérieur et `text-align` pour centrer leur texte.
