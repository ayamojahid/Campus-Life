# Les éléments `block` et `inline` en HTML

En HTML, les éléments peuvent se comporter de deux façons principales : `block` et `inline`.

## 1. `Block` : élément en bloc

Un élément `block` commence généralement sur une nouvelle ligne et prend toute la largeur disponible.

Exemples : `<div>`, `<p>`, `<h1>`, `<section>`.

Dessin : les blocs se placent l’un sous l’autre.

Premier bloc : div

Deuxième bloc : p

Troisième bloc : h1

Exemple HTML :

HTML

```
<div>Bonjour</div>
<div>Comment ça va ?</div>
```

Résultat :

```
Bonjour
Comment ça va ?
```

Chaque `div` commence sur une nouvelle ligne.

## 2. `Inline` : élément en ligne

Un élément `inline` reste sur la même ligne que le texte ou les autres éléments inline. Il prend seulement la place nécessaire à son contenu.

Exemples : `<span>`, `<a>`, `<strong>`, `<em>`.

Dessin : les éléments restent côte à côte.

Bonjour

tout

le monde !

Exemple HTML :

HTML

```
<span>Bonjour</span>
<span>tout</span>
<span>le monde !</span>
```

Résultat : `Bonjour tout le monde !` — les éléments restent sur la même ligne si l’espace est suffisant.

## 3. Différence entre les deux

| `block`                                        | `inline`                                            |
| ---------------------------------------------- | --------------------------------------------------- |
| Commence sur une nouvelle ligne                | Reste dans la même ligne                            |
| Prend généralement toute la largeur disponible | Prend la largeur de son contenu                     |
| `width` et `height` fonctionnent normalement   | `width` et `height` ne s’appliquent pas normalement |
| Exemple : `div`, `p`, `h1`                     | Exemple : `span`, `a`, `strong`                     |

## 4. Et `inline-block` ?

`inline-block` combine les deux comportements : il reste sur la même ligne, mais tu peux définir sa largeur et sa hauteur.

Dessin : trois blocs sur la même ligne.

Bloc 1

Bloc 2

Bloc 3

CSS

```
div {
    display: inline-block;
    width: 100px;
    height: 50px;
}
```

À retenir : `block` = dessous ; `inline` = à côté ; `inline-block` = à côté avec largeur et hauteur personnalisables.
