# 👋 Bienvenue chez C-DATA³⁶⁰

Ce document est ton point de départ. Lis-le entièrement avant d'écrire la moindre ligne de code.

## 📚 Documents à lire dans l'ordre

1. [Notre GitFlow](./gitflow.md) - Comment on gère les branches
2. [Conventions de commits](./conventions-commits.md) - Comment on nomme les commits
3. [Process de Pull Request](./process-pr.md) - Comment on soumet son travail
4. [Changesets](./changesets.md) - Comment on versionne le code et génère les changelogs

## 🛠️ Setup de base

### 1. Configure ton identité Git avec ton mail pro

```bash
git config --global user.name "Prénom Nom"
git config --global user.email "prenom.nom@c-data360.ai"
```

### 2. Clone le repo sur lequel tu travailles

```bash
git clone git@github.com:c-data360/nom-du-repo.git
cd nom-du-repo
```

### 3. Installe les dépendances et configure l'environnement

> Voir le README du repo concerné.

## ✅ Checklist avant ton premier commit

- [ ] Git configuré avec ton mail pro
- [ ] Tu as lu le GitFlow
- [ ] Tu as lu les conventions de commits
- [ ] Tu as lu le process de PR
- [ ] Tu as lu la doc Changesets
- [ ] Tu as créé ta branche depuis `develop` (jamais depuis `main`)
