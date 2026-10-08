**branching avec Git**

### 1. C’est quoi une branche ?

Imagine ton projet :

```text
main
 │
 ├── projet actuel
 │
 └── ...
```

`main` = version principale et stable du projet.

Tu veux ajouter une nouvelle fonctionnalité. Tu crées une branche :

```text
main
 │
 └── feature-navbar
       │
       ├── modification 1
       ├── modification 2
       └── modification 3
```

Tu travailles sur `feature-navbar` **sans modifier directement `main`**.

---

## 2. Pourquoi utiliser les branches ?

Exemple :

Tu as un site **Campus Life** :

```text
main
```

Le site fonctionne bien.

Tu veux maintenant ajouter :

* une navbar
* une page activités
* une page contact

Tu peux faire :

```text
main
│
├── navbar
├── activities
└── contact
```

Chaque branche permet de travailler sur une fonctionnalité séparément.

---

# 3. Voir la branche actuelle

Dans le terminal :

```bash
git branch
```

Exemple :

```text
* main
```

Le `*` indique la branche dans laquelle tu es actuellement.

---

# 4. Créer une branche

Par exemple, pour travailler sur la navbar :

```bash
git branch navbar
```

Tu as maintenant :

```text
main
navbar
```

⚠️ Mais tu es toujours sur `main`.

Vérifie :

```bash
git branch
```

```text
* main
  navbar
```

---

# 5. Aller sur la nouvelle branche

```bash
git switch navbar
```

Maintenant :

```bash
git branch
```

donne :

```text
  main
* navbar
```

Tu travailles maintenant sur `navbar`.

---

# 6. Méthode plus simple ⭐

Tu peux **créer ET aller directement** sur la branche :

```bash
git switch -c navbar
```

C'est probablement la commande que tu utiliseras le plus.

Elle fait :

```text
git branch navbar
+
git switch navbar
```

en une seule commande.

---

# 7. Travailler normalement

Tu modifies tes fichiers :

```text
index.html
style.css
script.js
```

Puis :

```bash
git status
```

Ensuite :

```bash
git add .
```

Puis :

```bash
git commit -m "add navbar"
```

Ta branche devient :

```text
main
   \
    navbar
       \
        commit "add navbar"
```

---

# 8. Revenir sur main

Quand tu veux retourner sur `main` :

```bash
git switch main
```

Tu passes de :

```text
navbar
```

à :

```text
main
```

---

# 9. Fusionner une branche ⭐

Supposons que tu as terminé la navbar.

Tu es sur :

```text
navbar
```

Tu as fait :

```bash
git add .
git commit -m "add navbar"
```

Maintenant tu veux mettre la navbar dans `main`.

### Étape 1 : revenir sur main

```bash
git switch main
```

### Étape 2 : fusionner navbar

```bash
git merge navbar
```

Git prend les modifications de :

```text
navbar
```

et les ajoute à :

```text
main
```

Tu obtiens :

```text
          navbar
         /
main ----
         \
          fusion
```

---

# 10. Supprimer la branche

Une fois la branche fusionnée, tu peux la supprimer :

```bash
git branch -d navbar
```

⚠️ Cela supprime **la branche**, pas les fichiers ni les modifications déjà fusionnées dans `main`.

---

# 11. Exemple complet pour ton projet

Supposons que tu viens de cloner ton projet :

```bash
git clone URL
cd Campus-Life
```

Tu vérifies :

```bash
git branch
```

Tu as :

```text
* main
```

Tu veux travailler sur la page activités :

```bash
git switch -c activities
```

Tu travailles sur HTML/CSS.

Puis :

```bash
git add .
git commit -m "add activities page"
```

Quand tu as terminé :

```bash
git switch main
```

Puis :

```bash
git merge activities
```

Et finalement :

```bash
git branch -d activities
```

---

## 12. Et avec GitHub ?

Il y a une différence importante.

### Branche locale

```bash
git switch -c activities
```

La branche existe seulement sur ton PC.

Pour envoyer la branche sur GitHub :

```bash
git push -u origin activities
```

Maintenant GitHub connaît aussi :

```text
main
activities
```

---

# 13. Le workflow à retenir ⭐

Pour chaque nouvelle fonctionnalité :

```bash
git switch main
git pull
git switch -c ma-feature
```

Tu travailles :

```bash
git add .
git commit -m "add ma feature"
```

Puis tu envoies :

```bash
git push -u origin ma-feature
```

Ensuite, tu peux fusionner la branche dans `main` avec GitHub (Pull Request) ou avec :

```bash
git switch main
git merge ma-feature
git push
```

---

### 🧠 Les commandes essentielles

| Commande               | Signification                             |
| ---------------------- | ----------------------------------------- |
| `git branch`           | Voir les branches                         |
| `git switch main`      | Aller sur main                            |
| `git switch -c navbar` | Créer + aller sur navbar                  |
| `git add .`            | Préparer les modifications                |
| `git commit -m "..."`  | Enregistrer les modifications             |
| `git push`             | Envoyer vers GitHub                       |
| `git merge navbar`     | Fusionner navbar dans la branche actuelle |
| `git branch -d navbar` | Supprimer la branche                      |

**La règle la plus importante :**

```text
main = projet stable
      ↓
   nouvelle branche
      ↓
   je travaille
      ↓
     commit
      ↓
     merge
      ↓
main = projet mis à jour
```

Et surtout : **`git merge navbar` doit être exécuté depuis `main` si ton objectif est de mettre `navbar` dans `main`.**







les étapes simples pour créer et utiliser une branche Git**, dans l'ordre.

### 1. Vérifier où tu es

```bash
git branch
```

Tu verras par exemple :

```text
* main
```

### 2. Créer une nouvelle branche

```bash
git switch -c navbar
```

Ici `navbar` est le nom de ta branche.

Cette commande fait **2 choses** :

* crée `navbar` 
* te place directement dessus

### 3. Vérifier

```bash
git branch
```

Tu dois avoir :

```text
  main
* navbar
```

Le `*` indique que tu es sur `navbar`.

### 4. Faire tes modifications

Par exemple :

```text
index.html
style.css
```

Tu travailles normalement.

### 5. Vérifier les modifications

```bash
git status
```

### 6. Ajouter les fichiers

```bash
git add .
```

### 7. Faire un commit

```bash
git commit -m "add navbar"
```

### 8. Envoyer la branche sur GitHub

```bash
git push -u origin navbar
```

Maintenant la branche existe aussi sur GitHub.

---

## 🔄 Ensuite, pour mettre la branche dans `main`

### 9. Revenir sur main

```bash
git switch main
```

### 10. Récupérer la dernière version

```bash
git pull
```

### 11. Fusionner la branche

```bash
git merge navbar
```

### 12. Envoyer `main` sur GitHub

```bash
git push
```

### 13. Supprimer la branche si tu n'en as plus besoin

```bash
git branch -d navbar
```

---

### ⭐ À retenir

```text
1. git switch -c navbar
        ↓
2. Je travaille
        ↓
3. git add .
        ↓
4. git commit -m "..."
        ↓
5. git push -u origin navbar
        ↓
6. git switch main
        ↓
7. git merge navbar
        ↓
8. git push
```

C'est le **workflow de base du branching Git**.

