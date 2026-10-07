# 📦 CSS Box Model

Le **Box Model** est une notion fondamentale en CSS.

L'idée est simple :

> **Chaque élément HTML est considéré comme une boîte.**

Par exemple :

```html
<div class="box">Hello</div>
```

Cette `<div>` est une boîte composée de **4 parties** :

```text
┌──────────────────────────────┐
│           MARGIN             │
│  ┌────────────────────────┐  │
│  │        BORDER          │  │
│  │  ┌──────────────────┐  │  │
│  │  │     PADDING      │  │  │
│  │  │  ┌────────────┐  │  │  │
│  │  │  │  CONTENT   │  │  │  │
│  │  │  └────────────┘  │  │  │
│  │  └──────────────────┘  │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
```

Il faut retenir :

**Content → Padding → Border → Margin**

---

## 1. `content` — contenu

C'est ce qu'il y a **à l'intérieur** de l'élément :

* texte
* image
* bouton
* etc.

```css id="2cpsb4"
.box {
    width: 200px;
    height: 100px;
}
```

Ici :

```text
width  → largeur du contenu
height → hauteur du contenu
```

---

## 2. `padding` — espace intérieur

Le `padding` est l'espace entre le **contenu et la bordure**.

```css id="l85eh7"
.box {
    padding: 20px;
}
```

Visualise :

```text
┌─────────────────────┐
│      padding        │
│   ┌─────────────┐   │
│   │   content   │   │
│   └─────────────┘   │
└─────────────────────┘
```

👉 Le padding donne de **l'espace à l'intérieur**.

---

## 3. `border` — bordure

La `border` est la **ligne autour de la boîte**.

```css id="z83l9m"
.box {
    border: 2px solid black;
}
```

Visualisation :

```text
┌─────────────────────┐
│                     │
│       content       │
│                     │
└─────────────────────┘
       ↑
     border
```

---

## 4. `margin` — espace extérieur

Le `margin` est l'espace **à l'extérieur de la boîte**.

```css id="q5d9i3"
.box {
    margin: 20px;
}
```

Si tu as deux boîtes :

```text
┌───────────┐
│   BOX 1   │
└───────────┘
      ↑
    margin
      ↓
┌───────────┐
│   BOX 2   │
└───────────┘
```

👉 Le margin sert à créer de l'espace **entre les éléments**.

---

# ⭐ Différence Padding / Margin

C'est très important.

### `padding`

➡️ espace **à l'intérieur**

```text
border
 ↓
┌───────────────┐
│    padding    │
│   ┌───────┐   │
│   │text   │   │
│   └───────┘   │
└───────────────┘
```

### `margin`

➡️ espace **à l'extérieur**

```text
      margin
        ↓
   ┌─────────┐
   │  BOX    │
   └─────────┘
        ↑
      margin
```

🧠 Astuce :

> **Padding = espace dedans**
> **Margin = espace dehors**

---

# 5. Exemple complet

```html id="r15cmm"
<div class="box">
    Hello
</div>
```

```css id="8yhq3q"
.box {
    width: 200px;
    height: 100px;

    padding: 20px;

    border: 2px solid black;

    margin: 30px;
}
```

La boîte possède donc :

```text
             MARGIN 30px
       ┌─────────────────────┐
       │                     │
       │    BORDER 2px       │
       │  ┌───────────────┐  │
       │  │ PADDING 20px  │  │
       │  │  ┌─────────┐  │  │
       │  │  │ CONTENT │  │  │
       │  │  │ 200x100 │  │  │
       │  │  └─────────┘  │  │
       │  └───────────────┘  │
       └─────────────────────┘
```

---

# 🧠 Résumé à apprendre

```text
CSS BOX MODEL

┌─────────────────────┐
│       MARGIN        │  ← extérieur
│  ┌───────────────┐  │
│  │    BORDER     │  ← bordure
│  │  ┌─────────┐  │  │
│  │  │ PADDING │  │  │ ← intérieur
│  │  │ CONTENT │  │  │ ← contenu
│  │  └─────────┘  │  │
│  └───────────────┘  │
└─────────────────────┘
```

**Dans l'ordre :**

> 🟦 Content → 🟩 Padding → 🟨 Border → 🟥 Margin

Et la phrase la plus importante :

> **Padding = espace à l'intérieur de la boîte.**
> **Margin = espace à l'extérieur de la boîte.**
