
# 🌐 Sémantique HTML

## 1. C'est quoi la sémantique HTML ?

La **sémantique HTML** consiste à utiliser une balise qui décrit clairement **le rôle du contenu**.

Par exemple :

```html
<div>Mon titre</div>
```

fonctionne techniquement, mais `<div>` ne dit pas que c'est un titre.

Alors que :

```html
<h1>Mon titre</h1>
```

dit clairement : **« ceci est le titre principal de la page »**.

👉 Donc :

**HTML sémantique = utiliser la balise qui correspond au sens du contenu.**

---

# 2. Structure générale d'une page

Une page HTML sémantique peut ressembler à ceci :

```html
<body>

    <header>
        ...
    </header>

    <nav>
        ...
    </nav>

    <main>

        <section>
            ...
        </section>

        <section>
            ...
        </section>

        <article>
            ...
        </article>

        <aside>
            ...
        </aside>

    </main>

    <footer>
        ...
    </footer>

</body>
```

Voyons chaque balise.

---

# 3. `<header>` — En-tête

`<header>` représente **l'en-tête** d'une page ou d'une section.

Il peut contenir :

* logo
* titre
* introduction
* menu
* informations importantes

Exemple :

```html
<header>
    <h1>Campus Life</h1>
    <p>Bienvenue sur notre plateforme</p>
</header>
```

🧠 À retenir :

> `<header>` = partie supérieure / introduction d'une page ou d'une section.

⚠️ `<header>` n'est pas obligatoirement tout en haut de la page. Une section peut aussi avoir son propre `<header>`.

---

# 4. `<nav>` — Navigation

`<nav>` contient les **liens de navigation principaux**.

Exemple :

```html
<nav>
    <a href="index.html">Accueil</a>
    <a href="about.html">À propos</a>
    <a href="contact.html">Contact</a>
</nav>
```

🧠 À retenir :

> `<nav>` = ensemble de liens permettant de naviguer dans le site.

---

# 5. `<main>` — Contenu principal

`<main>` contient le **contenu principal et unique de la page**.

Exemple :

```html
<main>
    <h1>Campus Life</h1>
    <p>Découvrez la vie à YouCode.</p>
</main>
```

🧠 À retenir :

> `<main>` = le contenu principal de la page.

Normalement, une page possède **un seul `<main>`**.

---

# 6. `<section>` — Section

`<section>` représente une **partie thématique** d'une page.

Par exemple, sur un site Campus Life :

```html
<section>
    <h2>La vie à YouCode</h2>
    <p>Découvrez notre environnement.</p>
</section>

<section>
    <h2>Nos activités</h2>
    <p>Découvrez les différentes activités.</p>
</section>
```

Ici, on a deux thèmes différents.

🧠 À retenir :

> `<section>` = une partie de la page regroupant du contenu autour d'un même thème.

### Très important

Une `<section>` devrait généralement avoir un titre :

```html
<section>
    <h2>Nos activités</h2>
    ...
</section>
```

---

# 7. `<article>` — Article / contenu autonome

`<article>` représente un contenu qui peut être **compris indépendamment du reste de la page**.

Exemples :

* article de blog
* actualité
* publication
* témoignage
* post
* fiche d'un événement

Exemple :

```html
<article>
    <h2>Journée d'intégration</h2>
    <p>Les nouveaux apprenants découvrent YouCode.</p>
</article>
```

🧠 Question à se poser :

> « Est-ce que ce contenu pourrait être déplacé ou partagé seul ? »

Si oui, `<article>` peut être approprié.

---

# 8. `<aside>` — Contenu secondaire

`<aside>` représente un contenu **complémentaire ou secondaire** par rapport au contenu principal.

Exemples :

* informations supplémentaires
* liens utiles
* publicité
* barre latérale
* contenu associé

```html
<aside>
    <h2>Liens utiles</h2>
    <a href="#">Calendrier</a>
    <a href="#">Contact</a>
</aside>
```

🧠 À retenir :

> `<aside>` = information secondaire/complémentaire.

---

# 9. `<footer>` — Pied de page

`<footer>` représente le **pied de page** d'une page ou d'une section.

Il peut contenir :

* copyright
* contact
* liens
* réseaux sociaux
* informations légales

Exemple :

```html
<footer>
    <p>© 2026 Campus Life</p>
    <a href="#">Contact</a>
</footer>
```

🧠 À retenir :

> `<footer>` = informations de fin d'une page ou d'une section.

---

# 10. `<h1>` à `<h6>` — Titres

Les balises `h` représentent les **niveaux de titres**.

```html
<h1>Titre principal</h1>

<h2>Grande partie</h2>

<h3>Sous-partie</h3>

<h4>Sous-sous-partie</h4>

<h5>...</h5>

<h6>...</h6>
```

Hiérarchie :

```text
h1
 ├── h2
 │    ├── h3
 │    └── h3
 └── h2
      └── h3
```

### Exemple

```html
<h1>Campus Life</h1>

<h2>La vie étudiante</h2>

<h3>Les activités</h3>

<h3>Les événements</h3>

<h2>Notre campus</h2>
```

🧠 À retenir :

> `h1` = titre principal
> `h2` = grande partie
> `h3` = sous-partie
> etc.

---

# 11. `<p>` — Paragraphe

`<p>` représente un **paragraphe de texte**.

```html
<p>
    YouCode est un espace où les apprenants peuvent apprendre
    et développer leurs compétences.
</p>
```

🧠 À retenir :

> `<p>` = paragraphe.

---

# 12. `<a>` — Lien

`<a>` représente un **lien hypertexte**.

```html
<a href="https://example.com">Visiter le site</a>
```

Il peut également servir à naviguer entre les pages :

```html
<a href="contact.html">Contact</a>
```

🧠 À retenir :

> `<a>` = lien vers une autre destination.

---

# 13. `<img>` — Image

`<img>` représente une image.

```html
<img src="campus.jpg" alt="Campus YouCode">
```

### `src`

Indique où se trouve l'image.

### `alt`

Décrit l'image.

```html
alt="Campus YouCode"
```

C'est important pour **l'accessibilité** et lorsque l'image ne peut pas être affichée.

---

# 14. `<figure>` — Contenu illustratif

`<figure>` permet de regrouper une image, un graphique, une illustration, etc.

```html
<figure>
    <img src="campus.jpg" alt="Campus YouCode">
    <figcaption>Le campus YouCode</figcaption>
</figure>
```

---

# 15. `<figcaption>` — Légende

`<figcaption>` donne une **légende ou description** à un `<figure>`.

```html
<figure>
    <img src="campus.jpg" alt="Campus">
    <figcaption>Notre espace de formation</figcaption>
</figure>
```

🧠 À retenir :

```text
<figure>       → élément illustratif
<figcaption>   → description/légende
```

---

# 16. `<ul>` — Liste non ordonnée

`<ul>` représente une liste où **l'ordre n'est pas important**.

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

Résultat conceptuel :

```text
• HTML
• CSS
• JavaScript
```

---

# 17. `<ol>` — Liste ordonnée

`<ol>` représente une liste où **l'ordre est important**.

```html
<ol>
    <li>Créer un compte</li>
    <li>Se connecter</li>
    <li>Commencer la formation</li>
</ol>
```

Résultat :

```text
1. Créer un compte
2. Se connecter
3. Commencer la formation
```

---

# 18. `<li>` — Élément de liste

`<li>` représente **un élément dans une liste**.

Il est généralement utilisé avec :

```html
<ul>
```

ou

```html
<ol>
```

Exemple :

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
</ul>
```

---

# 19. `<strong>` — Importance forte

`<strong>` indique que le contenu possède une **importance particulière**.

```html
<p>
    <strong>Attention :</strong> inscription obligatoire.
</p>
```

Par défaut, le navigateur affiche généralement le texte en gras, mais son rôle principal est **sémantique**, pas simplement visuel.

---

# 20. `<em>` — Emphase

`<em>` indique une **emphase** sur un mot ou une partie du texte.

```html
<p>
    Il est <em>très important</em> de respecter les règles.
</p>
```

Par défaut, le navigateur affiche généralement le texte en italique.

---

# 21. `<mark>` — Texte mis en évidence

`<mark>` indique un texte **mis en évidence**.

```html
<p>
    N'oubliez pas la <mark>date d'inscription</mark>.
</p>
```

---

# 22. `<time>` — Date ou heure

`<time>` représente une date ou une heure.

```html
<time datetime="2026-10-07">7 octobre 2026</time>
```

Ou :

```html
<time datetime="18:00">18:00</time>
```

🧠 Très utile pour donner une information temporelle compréhensible par les machines.

---

# 23. `<address>` — Informations de contact

`<address>` représente des informations de contact liées à une personne, organisation ou page.

```html
<address>
    Email : contact@example.com
</address>
```

---

# 24. `<details>` — Contenu ouvrable

`<details>` permet de créer une zone que l'utilisateur peut **ouvrir et fermer**.

```html
<details>
    <summary>Qu'est-ce que YouCode ?</summary>

    <p>YouCode est une école de développement.</p>
</details>
```

`<summary>` représente le titre cliquable.

---

# 25. `<dialog>` — Boîte de dialogue

`<dialog>` représente une **boîte de dialogue** ou une fenêtre modale.

```html
<dialog>
    <p>Votre inscription est terminée.</p>
</dialog>
```

Elle est généralement contrôlée avec JavaScript.

---

# 26. `<form>` — Formulaire

`<form>` représente un **formulaire permettant de saisir/envoyer des informations**.

```html
<form>
    <label for="name">Nom :</label>
    <input id="name" type="text">

    <button type="submit">Envoyer</button>
</form>
```

---

# 27. `<label>` — Étiquette d'un champ

`<label>` décrit un champ de formulaire.

```html
<label for="email">Email :</label>
<input id="email" type="email">
```

Le `for` correspond à l'`id` :

```text
label for="email"
        ↓
input id="email"
```

---

# 28. `<button>` — Bouton

`<button>` représente un **bouton interactif**.

```html
<button type="submit">Envoyer</button>
```

Contrairement à un simple `<div>`, le navigateur comprend que c'est un élément interactif.

---

# 29. `<table>` — Tableau de données

Pour présenter des **données sous forme de tableau** :

```html
<table>
    <caption>Apprenants</caption>

    <thead>
        <tr>
            <th>Nom</th>
            <th>Age</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>Aya</td>
            <td>23</td>
        </tr>
    </tbody>
</table>
```

Les balises importantes :

| Balise      | Rôle               |
| ----------- | ------------------ |
| `<table>`   | tableau            |
| `<caption>` | titre du tableau   |
| `<thead>`   | partie en-tête     |
| `<tbody>`   | corps du tableau   |
| `<tfoot>`   | pied du tableau    |
| `<tr>`      | ligne              |
| `<th>`      | cellule d'en-tête  |
| `<td>`      | cellule de données |

---

# 30. `<div>` — Conteneur générique

`<div>` est un conteneur **sans signification sémantique particulière**.

```html
<div>
    <p>Bonjour</p>
</div>
```

Il est très utile pour organiser/styliser des éléments, mais si une balise sémantique adaptée existe, il vaut mieux l'utiliser.

❌ Moins sémantique :

```html
<div class="header">
```

✅ Plus sémantique :

```html
<header>
```

---

# 31. `<span>` — Conteneur de texte

`<span>` est un conteneur **inline générique**, souvent utilisé pour appliquer du CSS ou cibler une petite partie de texte.

```html
<p>
    Bienvenue à <span>Campus Life</span>.
</p>
```

`<span>` n'a pas de signification sémantique particulière.

---

# ⭐ Les balises sémantiques les plus importantes

Pour ton projet **Campus Life**, retiens surtout celles-ci :

```text
<header>       → en-tête
<nav>          → navigation
<main>         → contenu principal
<section>      → section thématique
<article>      → contenu autonome
<aside>        → contenu secondaire
<footer>       → pied de page

<h1> ... <h6> → titres
<p>            → paragraphe
<a>            → lien
<figure>       → illustration
<figcaption>   → légende
<time>         → date/heure
<address>      → contact

<ul> / <ol>    → listes
<li>           → élément de liste

<form>         → formulaire
<label>        → étiquette
<button>       → bouton

<table>        → tableau de données
```

## 🧠 La différence essentielle

Imagine ta page comme un bâtiment :

```text
<body>
│
├── <header>       → entrée / en-tête
│
├── <nav>          → panneaux pour se déplacer
│
├── <main>         → partie principale du bâtiment
│   │
│   ├── <section>  → salle / zone thématique
│   │
│   ├── <article>  → contenu autonome
│   │
│   └── <aside>    → information complémentaire
│
└── <footer>       → partie finale
```

Et surtout :

**`<div>` = boîte générique**
**`<section>` = boîte avec un thème**
**`<article>` = contenu autonome**
**`<aside>` = contenu secondaire**
**`<header>` = en-tête**
**`<footer>` = pied de page**
**`<nav>` = navigation**
**`<main>` = contenu principal**
