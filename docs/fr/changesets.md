# 📦 Changesets - Versioning & Changelog

On utilise **[Changesets](https://github.com/changesets/changesets)** pour gérer le versioning sémantique et la génération automatique des changelogs.

---

## Principe

Chaque changement significatif dans le code doit être accompagné d'un **changeset** - un petit fichier décrivant la nature du changement (`patch`, `minor`, `major`) et un résumé lisible par un humain.

Ces fichiers s'accumulent dans `.changeset/` au fil des PR, puis sont consommés lors d'une release pour :

1. Bumper automatiquement les versions des packages concernés
2. Générer les entrées de `CHANGELOG.md`

---

## Quand créer un changeset ?

| Situation | Changeset ? |
|---|---|
| Nouvelle fonctionnalité visible par l'utilisateur | ✅ `minor` |
| Correction de bug | ✅ `patch` |
| Breaking change (API, contrat, schéma) | ✅ `major` |
| Refactoring interne, style, docs | ❌ Non |
| Mise à jour de dépendances (sans impact API) | ❌ Non |

---

## Workflow

### 1. Créer un changeset après ta modification

```bash
pnpm changeset
```

Un assistant interactif te demande :
- Le ou les packages impactés
- Le type de bump (`patch`, `minor`, `major`)
- Un résumé du changement (affiché dans le changelog)

Un fichier est créé dans `.changeset/` - **committe-le avec ton code**.

```bash
git add .changeset/
git commit -m "chore: add changeset for feat(auth)"
```

### 2. Lors d'une release - bumper les versions

```bash
pnpm changeset:version
```

Cette commande :
- Lit tous les fichiers `.changeset/`
- Met à jour les `package.json` concernés
- Génère / met à jour les `CHANGELOG.md`
- Supprime les fichiers `.changeset/` consommés

Committe le résultat :

```bash
git add .
git commit -m "chore: version packages"
```

### 3. Publier (si applicable)

```bash
pnpm changeset publish
```

> Dans ce projet, les releases sont automatisées via GitHub Actions (`.github/workflows/release.yml`). Le workflow crée une PR de release automatiquement dès qu'il détecte des changesets non consommés sur `main`.

---

## Types de bump

| Type | Quand | Exemple de version |
|---|---|---|
| `patch` | Bug fix, correction mineure | `1.2.3` → `1.2.4` |
| `minor` | Nouvelle fonctionnalité rétrocompatible | `1.2.3` → `1.3.0` |
| `major` | Breaking change | `1.2.3` → `2.0.0` |

---

## Règles

- ✅ Un changeset par fonctionnalité ou correction (une PR = un changeset)
- ✅ Le message du changeset est rédigé pour être lu dans un changelog (pas comme un commit)
- ✅ Committe le fichier `.changeset/` dans la même PR que le code
- ❌ Ne pas bumper manuellement les `package.json`
- ❌ Ne pas éditer les `CHANGELOG.md` à la main
