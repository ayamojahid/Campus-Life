## CSS — `class` et `id` 

### 1. `class`

Une **class** sert à donner un même style à **plusieurs éléments**.

### Écriture en HTML

```html
<p class="title">Bonjour</p>
<h2 class="title">Bienvenue</h2>
```

### Écriture en CSS

On utilise **`.`** devant le nom de la classe :

```css
.title {
    color: blue;
    font-size: 20px;
}
```

👉 `class="title"` → `.title`

---

### 2. `id`

Un **id** sert à identifier **un élément unique** dans la page.

### Écriture en HTML

```html
<h1 id="main-title">Campus Life</h1>
```

### Écriture en CSS

On utilise **`#`** devant le nom de l'id :

```css
#main-title {
    color: red;
}
```

👉 `id="main-title"` → `#main-title`

---

## ⭐ Différence principale

|             | `class`            | `id`              |
| ----------- | ------------------ | ----------------- |
| HTML        | `class="title"`    | `id="title"`      |
| CSS         | `.title`           | `#title`          |
| Utilisation | Plusieurs éléments | Un élément unique |
| Exemple     | `.card`            | `#header`         |

### À retenir 🧠

```text
class → .nom
id    → #nom
```

**Exemple complet :**

```html
<h1 id="title">Campus Life</h1>

<p class="text">Bienvenue</p>
<p class="text">Découvrez notre campus</p>
```

```css
#title {
    color: red;
}

.text {
    color: blue;
}
```

➡️ `#title` cible **un seul élément**.
➡️ `.text` peut cibler **plusieurs éléments**.


ou par les balises
```css
p{

}

a{

}

.card p {
    color: blue;
}
```
