Si tu voulais dire **`eventuellement` / `event` et `Grid` en CSS**, je pense que tu parles surtout de **CSS Grid**. Je t’explique le cours simplement.

# CSS Grid — cours simple

**CSS Grid** permet d'organiser les éléments en **lignes et colonnes**.

Imagine une grille :

```text
┌─────────┬─────────┬─────────┐
│    1    │    2    │    3    │
├─────────┼─────────┼─────────┤
│    4    │    5    │    6    │
└─────────┴─────────┴─────────┘
```

C'est très pratique pour créer :

* des cartes
* des galeries
* des layouts de pages
* des menus
* des sections avec plusieurs colonnes

---

## 1. Le parent devient une Grid

HTML :

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
</div>
```

CSS :

```css
.container {
    display: grid;
}
```

⚠️ Pour l'instant, on a seulement dit :

> « `.container` est une grille. »

---

# 2. Créer des colonnes

La propriété principale est :

```css
grid-template-columns
```

Exemple :

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

On obtient :

```text
┌────────┬────────┬────────┐
│   1    │   2    │   3    │
├────────┼────────┼────────┤
│   4    │         │       │
└────────┴────────┴────────┘
```

### Que signifie `1fr` ?

`fr` signifie **fraction de l'espace disponible**.

```css
grid-template-columns: 1fr 1fr 1fr;
```

signifie :

```text
1 part | 1 part | 1 part
```

Donc les trois colonnes ont la même largeur.

---

# 3. Deux colonnes

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

Résultat :

```text
┌────────────┬────────────┐
│     1      │     2      │
├────────────┼────────────┤
│     3      │     4      │
└────────────┴────────────┘
```

---

# 4. Colonnes de tailles différentes

```css
.container {
    display: grid;
    grid-template-columns: 2fr 1fr;
}
```

Résultat :

```text
┌──────────────────┬─────────┐
│                  │         │
│       2fr        │   1fr   │
│                  │         │
└──────────────────┴─────────┘
```

La première colonne prend **2 parts** et la deuxième **1 part**.

Donc :

```text
2fr : 1fr
```

= environ

```text
66% : 33%
```

---

# 5. Ajouter un espace entre les éléments

On utilise :

```css
gap
```

Exemple :

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
}
```

Résultat :

```text
┌───────┐  ┌───────┐  ┌───────┐
│   1   │  │   2   │  │   3   │
└───────┘  └───────┘  └───────┘

      espace = 20px
```

---

# 6. Créer des lignes

On peut également définir les lignes :

```css
grid-template-rows
```

Exemple :

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 100px 200px;
}
```

Cela signifie :

```text
2 colonnes

ligne 1 → 100px
ligne 2 → 200px
```

---

# 7. `repeat()`

Au lieu d'écrire :

```css
grid-template-columns: 1fr 1fr 1fr 1fr;
```

on peut écrire :

```css
grid-template-columns: repeat(4, 1fr);
```

C'est exactement la même chose.

```text
repeat(4, 1fr)

= 1fr 1fr 1fr 1fr
```

Très pratique.

---

# 8. Exemple avec des cartes ⭐

HTML :

```html
<div class="cards">

    <div class="card">Carte 1</div>
    <div class="card">Carte 2</div>
    <div class="card">Carte 3</div>
    <div class="card">Carte 4</div>
    <div class="card">Carte 5</div>
    <div class="card">Carte 6</div>

</div>
```

CSS :

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.card {
    padding: 30px;
    background-color: lightgray;
}
```

Résultat :

```text
┌────────┐  ┌────────┐  ┌────────┐
│ Carte 1│  │ Carte 2│  │ Carte 3│
└────────┘  └────────┘  └────────┘

┌────────┐  ┌────────┐  ┌────────┐
│ Carte 4│  │ Carte 5│  │ Carte 6│
└────────┘  └────────┘  └────────┘
```

---

# 9. Faire prendre plusieurs colonnes à un élément

On utilise :

```css
grid-column
```

Par exemple :

```css
.item1 {
    grid-column: span 2;
}
```

Cela signifie :

> l'élément prend **2 colonnes**.

Exemple :

```text
┌──────────────────────┬─────────┐
│       Item 1         │ Item 2  │
│       2 colonnes     │         │
└──────────────────────┴─────────┘
```

---

# 10. `grid-column`

On peut aussi préciser exactement où l'élément commence et finit :

```css
.item1 {
    grid-column: 1 / 3;
}
```

Cela signifie :

```text
commence à la colonne 1
          ↓
    1     2     3
    |-----|-----|
    └───────────┘
```

Donc l'élément occupe les colonnes **1 et 2**.

---

# 11. `grid-row`

Même principe pour les lignes :

```css
.item1 {
    grid-row: 1 / 3;
}
```

L'élément prend les lignes 1 et 2.

---

# 12. `grid-template-areas` ⭐

C'est très intéressant pour créer la structure d'un site.

HTML :

```html
<div class="page">

    <header>Header</header>

    <nav>Navigation</nav>

    <main>Main</main>

    <footer>Footer</footer>

</div>
```

CSS :

```css
.page {
    display: grid;

    grid-template-columns: 200px 1fr;

    grid-template-areas:
        "header header"
        "nav main"
        "footer footer";
}
```

Puis :

```css
header {
    grid-area: header;
}

nav {
    grid-area: nav;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

On obtient :

```text
┌──────────────────────────────┐
│            HEADER            │
├──────────┬───────────────────┤
│          │                   │
│   NAV    │       MAIN        │
│          │                   │
├──────────┴───────────────────┤
│            FOOTER            │
└──────────────────────────────┘
```

C'est très pratique pour un vrai site web.

---

# 13. Grid vs Flexbox

C'est important de comprendre la différence.

### Flexbox

Flexbox travaille principalement dans **une direction** :

```text
→ → → →
```

ou

```text
↓
↓
↓
```

Donc :

> **Flexbox = 1 dimension**

### Grid

Grid travaille avec :

```text
→ colonnes
↓ lignes
```

Donc :

> **Grid = 2 dimensions**

### Résumé

```text
Flexbox
→ → → →
```

```text
Grid

┌───┬───┬───┐
│   │   │   │
├───┼───┼───┤
│   │   │   │
└───┴───┴───┘
```

---

# 🧠 Les propriétés importantes à apprendre

Pour débuter, retiens surtout :

```css
display: grid;
```

```css
grid-template-columns
```

```css
grid-template-rows
```

```css
gap
```

```css
grid-column
```

```css
grid-row
```

```css
grid-area
```

```css
grid-template-areas
```

Et surtout :

```css
repeat()
```

---

## ⭐ Exemple complet à retenir

```css
.container {
    display: grid;

    grid-template-columns: repeat(3, 1fr);

    gap: 20px;
}
```

Ça veut simplement dire :

> **Je transforme `.container` en Grid → je crée 3 colonnes égales → je mets 20px d'espace entre les éléments.**

C'est la base de **CSS Grid**.
