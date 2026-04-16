# 🌿 GitFlow

## Vue d'ensemble

```
main          ← Production. Stable. Sacrée. On n'y touche jamais directement.
│
├── hotfix/   ← Correction urgente en production. Créée depuis main.
│
develop       ← Branche d'intégration. Toujours à jour. Base de tout développement.
│
├── feature/  ← Nouvelle fonctionnalité. Créée depuis develop.
│
└── release/  ← Préparation d'une version. Créée depuis develop.
```

---

## 📌 Règles absolues

> ❌ **On ne push JAMAIS directement sur `main` ou `develop`**
> ✅ **Tout passe par une Pull Request reviewée**

---

## 🔄 Cycle de vie d'une fonctionnalité

### 1. Créer sa branche depuis `develop`

```bash
git checkout develop
git pull origin develop
git checkout -b feature/nom-fonctionnalite
```

### 2. Développer et committer

```bash
git add .
git commit -m "feat: description courte de ce que tu as fait"
git push origin feature/nom-fonctionnalite
```

### 3. Ouvrir une Pull Request

- Base : `develop`
- Compare : `feature/nom-fonctionnalite`
- Remplir le template de PR
- Assigner un reviewer

### 4. Après validation → merge dans `develop` puis supprimer la branche

---

## 🚨 Cycle de vie d'un Hotfix

```bash
# Depuis main uniquement
git checkout main
git pull origin main
git checkout -b hotfix/description-courte

# ... corriger le bug ...

git commit -m "fix: description du correctif"
git push origin hotfix/description-courte

# Ouvrir une PR vers main ET une PR vers develop
```

> ⚠️ Un hotfix doit toujours être mergé dans **main ET develop** pour ne pas perdre la correction.

---

## 🚀 Cycle de vie d'une Release

```bash
# Depuis develop
git checkout develop
git pull origin develop
git checkout -b release/v1.2.0

# Derniers ajustements, bump de version...
git commit -m "chore: bump version to 1.2.0"
git push origin release/v1.2.0

# PR vers main, puis PR vers develop
```

---

## 📛 Nommage des branches

| Type               | Format                       | Exemple                          |
| ------------------ | ---------------------------- | -------------------------------- |
| Fonctionnalité     | `feature/nom-fonctionnalite` | `feature/authentification-oauth` |
| Correction urgente | `hotfix/description-courte`  | `hotfix/fix-login-crash`         |
| Release            | `release/vX.Y.Z`             | `release/v1.2.0`                 |

### Règles de nommage

- ✅ **En anglais** - comme les commits et le code
- ✅ Minuscules uniquement
- ✅ Tirets `-` pour séparer les mots (pas d'underscore `_`, pas d'espace)
- ✅ Nom court mais descriptif
- ❌ Pas de caractères spéciaux
- ❌ Pas de `/` supplémentaires dans le nom
