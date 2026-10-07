# 🎯 Flexbox en CSS

**Flexbox** est un système CSS qui permet de **placer et aligner facilement les éléments** dans une boîte.

Imagine que tu as 3 boîtes :

```text
┌─────────────────────────────────────┐
│  🟥 Box 1    🟦 Box 2    🟩 Box 3   │
└─────────────────────────────────────┘
```

Avec Flexbox, tu peux facilement décider :

* horizontalement ou verticalement
* à gauche, au centre ou à droite
* avec quel espace entre les éléments
* comment les éléments se répartissent

---

# 1. Le principe : `display: flex`

HTML :

```html
<div class="container">
    <div>Box 1</div>
    <div>Box 2</div>
    <div>Box 3</div>
</div>
```

CSS :

```css
.container {
    display: flex;
}
```

Résultat par défaut :

```text
┌─────────────────────────────────────┐
│ ┌──────┐ ┌──────┐ ┌──────┐         │
│ │Box 1 │ │Box 2 │ │Box 3 │         │
│ └──────┘ └──────┘ └──────┘         │
└─────────────────────────────────────┘
```

Sans Flexbox, les éléments peuvent être placés différemment selon leur type.

Avec :

```css
display: flex;
```

👉 le **parent** devient un conteneur Flexbox.

---

# 2. `flex-direction`

Cette propriété définit la **direction** des éléments.

### `row` → horizontal

```css
.container {
    display: flex;
    flex-direction: row;
}
```

```text
🟥 → 🟦 → 🟩
```

C'est la valeur par défaut.

### `column` → vertical

```css
.container {
    display: flex;
    flex-direction: column;
}
```

```text
🟥
↓
🟦
↓
🟩
```

🧠 À retenir :

```text
row    → ligne → horizontal
column → colonne ↓ vertical
```

---

# 3. `justify-content`

C'est une propriété **très importante**.

Elle permet de contrôler la position des éléments sur **l'axe principal**.

Avec `row`, l'axe principal est horizontal :

```text
←──────────────→
    horizontal
```

### `flex-start`

```css
justify-content: flex-start;
```

```text
🟥 🟦 🟩
```

➡️ à gauche.

---

### `center`

```css
justify-content: center;
```

```text
        🟥 🟦 🟩
```

➡️ au centre.

---

### `flex-end`

```css
justify-content: flex-end;
```

```text
                    🟥 🟦 🟩
```

➡️ à droite.

---

### `space-between`

```css
justify-content: space-between;
```

```text
🟥             🟦             🟩
```

➡️ espace entre les éléments.

---

### `space-around`

```css
justify-content: space-around;
```

```text
   🟥        🟦        🟩
```

➡️ espace autour des éléments.

---

### `space-evenly`

```css
justify-content: space-evenly;
```

```text
    🟥        🟦        🟩
```

➡️ espaces égaux partout.

---

# 4. `align-items`

`align-items` contrôle l'alignement sur **l'autre axe**.

Si on est en `row` :

```text
        ↓
        │
        │  axe vertical
        │
        ↓
```

Exemple :

```css
.container {
    display: flex;
    align-items: center;
}
```

Les éléments seront centrés verticalement.

```text
┌─────────────────────────────┐
│                             │
│     🟥   🟦   🟩            │
│                             │
└─────────────────────────────┘
```

---

# ⭐ 5. Centrer parfaitement un élément

C'est l'un des usages les plus connus de Flexbox.

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Résultat :

```text
┌─────────────────────────────┐
│                             │
│                             │
│          🟥                 │
│                             │
│                             │
└─────────────────────────────┘
```

👉 `justify-content: center` → centre horizontalement
👉 `align-items: center` → centre verticalement

---

# 6. `gap`

`gap` permet de créer un espace **entre les éléments**.

```css
.container {
    display: flex;
    gap: 20px;
}
```

Résultat :

```text
🟥  ←20px→  🟦  ←20px→  🟩
```

C'est très pratique pour éviter de mettre des `margin` partout.

---

# 7. `flex-wrap`

Par défaut, Flexbox essaie de garder les éléments sur **une seule ligne**.

Avec :

```css
flex-wrap: wrap;
```

les éléments peuvent passer à la ligne suivante lorsqu'il n'y a plus assez de place.

```text
┌────────────────────────────┐
│ 🟥 🟦 🟩 🟨                │
│ 🟪 🟧                      │
└────────────────────────────┘
```

Très utile pour les **cartes**, galeries, produits, etc.

---

# 8. Exemple réel : des cartes

HTML :

```html
<div class="cards">

    <div class="card">
        <h2>HTML</h2>
        <p>Structure de la page.</p>
    </div>

    <div class="card">
        <h2>CSS</h2>
        <p>Design de la page.</p>
    </div>

    <div class="card">
        <h2>JavaScript</h2>
        <p>Interaction de la page.</p>
    </div>

</div>
```

CSS :

```css
.cards {
    display: flex;
    gap: 20px;
}

.card {
    padding: 20px;
    border: 1px solid black;
}
```

Visuellement :

```text
┌─────────────────────────────────────────┐
│                                         │
│ ┌───────────┐  ┌───────────┐  ┌───────┐ │
│ │   HTML    │  │    CSS    │  │  JS   │ │
│ │           │  │           │  │       │ │
│ │ Structure │  │  Design   │  │ Logic │ │
│ └───────────┘  └───────────┘  └───────┘ │
│                                         │
└─────────────────────────────────────────┘
```

---

# 9. Parent et enfants

C'est **très important** avec Flexbox.

Dans :

```html
<div class="container">
    <div>Box 1</div>
    <div>Box 2</div>
    <div>Box 3</div>
</div>
```

```text
             PARENT
          .container
               │
       ┌───────┼───────┐
       ↓       ↓       ↓
     Box 1   Box 2   Box 3
    enfant   enfant  enfant
```

Quand tu écris :

```css
.container {
    display: flex;
}
```

👉 **C'est le parent qui reçoit `display: flex`.**

Et Flexbox organise principalement **ses enfants directs**.

---

# 🧠 Les propriétés à apprendre en premier

Pour débuter, retiens surtout :

| Propriété         | Rôle                         |
| ----------------- | ---------------------------- |
| `display: flex`   | active Flexbox               |
| `flex-direction`  | direction des éléments       |
| `justify-content` | position sur l'axe principal |
| `align-items`     | alignement sur l'autre axe   |
| `gap`             | espace entre les éléments    |
| `flex-wrap`       | permet de passer à la ligne  |

### Le modèle mental

```text
                 CONTAINER
              display: flex
                    │
        ┌───────────┼───────────┐
        ↓           ↓           ↓
       🟥          🟦          🟩
```

Avec :

```css
.container {
    display: flex;

    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

Tu dis simplement :

> **« Mets mes éléments sur une ligne, au centre, aligne-les au centre et laisse 20px entre eux. »**

C'est ça, l'idée essentielle de **Flexbox**.
