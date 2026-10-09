Je vais t'expliquer `display` en CSS avec des exemples simples, des dessins et quand utiliser chaque valeur, pour que tu puisses aussi l'expliquer à ton professeur.

# 1. `display: block`

Un élément `block` commence sur une nouvelle ligne et prend généralement toute la largeur disponible.

DIV 1 — ligne complète

DIV 2 — nouvelle ligne

DIV 3 — nouvelle ligne

HTML

```
<div>Home</div>
<div>About</div>
<div>Contact</div>
```

CSS

```
div {
    display: block;
}
```

Résultat : les éléments sont les uns sous les autres.

À utiliser pour : les sections, les paragraphes et les grands blocs.

Exemples d'éléments qui sont `block` par défaut : `div`, `p`, `h1`, `section`.

# 2. `display: inline`

Un élément `inline` reste sur la même ligne que le texte ou les autres éléments inline.

Home

About

Contact

Les éléments sont côte à côte, comme des mots dans une phrase.

HTML

```
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Contact</a>
```

Les liens `<a>` sont `inline` par défaut.

CSS

```
a {
    display: inline;
}
```

À retenir :

* L'élément ne commence pas obligatoirement sur une nouvelle ligne.

* `width` et `height` ne s'appliquent pas comme sur un élément `block`.

* Les éléments restent sur la même ligne si l'espace disponible le permet.

À utiliser pour : les liens dans une phrase, les petits textes ou les éléments qui doivent rester dans la même ligne.

# 3. `display: inline-block`

C'est un mélange de `inline` et `block`.

* Comme `inline` : les éléments restent côte à côte.

* Comme `block` : tu peux définir leur `width` et leur `height`.

Home

About

Contact

Chaque élément a sa propre largeur et sa propre hauteur, mais ils restent sur la même ligne.

HTML

```
<div class="box">Home</div>
<div class="box">About</div>
<div class="box">Contact</div>
```

CSS

```
.box {
    display: inline-block;
    width: 100px;
    height: 60px;
    margin-right: 15px;
}
```

Explication :

* `display: inline-block;` : place les blocs côte à côte.

* `width: 100px;` : largeur de chaque bloc.

* `height: 60px;` : hauteur de chaque bloc.

* `margin-right: 15px;` : espace à droite de chaque bloc.

À utiliser pour : des petits blocs, des boutons ou des éléments de navigation quand tu ne veux pas utiliser Flexbox.

Attention : si la largeur totale des éléments dépasse celle du parent, certains éléments peuvent passer à la ligne.

# 4. `display: none`

Cette valeur cache complètement un élément et supprime l'espace qu'il occupait dans la disposition de la page.

HTML

```
<div class="message">Bonjour !</div>
<p>Bienvenue sur le site.</p>
```

CSS

```
.message {
    display: none;
}
```

Résultat : « Bonjour ! » ne s'affiche pas et le paragraphe remonte à sa place.

À utiliser pour : masquer un menu, un message ou un élément.

À ne pas confondre avec `visibility: hidden`, qui cache l'élément mais conserve son espace.

# 5. `display: flex`

Flexbox permet d'organiser facilement les éléments à l'intérieur d'un conteneur.

Home

About

Contact

Les éléments sont alignés sur une ligne par défaut.

HTML

```
<nav>
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
</nav>
```

CSS

```
nav {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

Voici le rôle de chaque propriété :

* `display: flex;` : active Flexbox.

* `justify-content: center;` : centre les éléments sur l'axe principal.

* `align-items: center;` : les aligne au centre sur l'axe secondaire.

* `gap: 20px;` : crée un espace de 20 pixels entre les éléments.

Pour placer les éléments verticalement :

CSS

```
nav {
    display: flex;
    flex-direction: column;
    gap: 20px;
}
```

À utiliser pour : les navigations, les boutons, les cartes et l'alignement des éléments.

# 6. `display: grid`

Grid permet d'organiser les éléments en lignes et en colonnes.

1

2

3

4

5

6

Six éléments, trois colonnes.

HTML

```
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
</div>
```

CSS

```
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
}
```

Explication :

* `display: grid;` : active Grid.

* `grid-template-columns: repeat(3, 1fr);` : crée trois colonnes de largeur égale.

* `gap: 15px;` : crée un espace entre les éléments.

À utiliser pour : les galeries d'images, les grilles de cartes et les mises en page avec plusieurs colonnes.

# 7. Comparaison à retenir

| Propriété      | Résultat principal                    | `width` / `height`         |
| -------------- | ------------------------------------- | -------------------------- |
| `block`        | Nouvelle ligne                        | Oui                        |
| `inline`       | Même ligne                            | Pas comme un bloc          |
| `inline-block` | Même ligne, avec comportement de bloc | Oui                        |
| `none`         | Élément masqué, sans espace réservé   | Sans effet sur l'affichage |
| `flex`         | Organisation flexible d'un groupe     | Oui                        |
| `grid`         | Organisation en lignes et colonnes    | Oui                        |

# 8. Quel `display` choisir ?

Je veux placer mes `div` les unes sous les autres.

`display: block;`

Je veux garder mes liens dans la même ligne.

`display: inline;`

Je veux quatre `div` côte à côte sans Flexbox, avec une largeur définie.

`display: inline-block;`

Je veux aligner facilement les éléments et gérer l'espace entre eux.

`display: flex;` avec `gap`.

Je veux plusieurs colonnes et plusieurs lignes.

`display: grid;`

## 9. Petit test

1. Tu veux quatre blocs côte à côte avec une largeur de 100px, sans Flexbox.

display: block;

display: inline;

display: inline-block;

2. Tu veux centrer facilement les liens d'une navigation et mettre 20px entre eux.

display: flex;

display: none;

display: block;

3. Tu veux afficher trois cartes en trois colonnes.

display: inline;

display: grid;

display: none;

Mon conseil pour ton projet Campus Life : maîtrise d'abord `block`, `inline` et `inline-block`, puis utilise Flexbox pour la navigation et Grid pour les cartes. Ce sont des outils complémentaires, pas des concurrents.
