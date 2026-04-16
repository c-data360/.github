# 📝 Conventions de Commits

On suit le standard **[Conventional Commits](https://www.conventionalcommits.org/)**.

## Format

```
type(scope): description courte

[corps optionnel]

[footer optionnel]
```

---

## Types de commits

| Type       | Quand l'utiliser                              | Exemple                                    |
| ---------- | --------------------------------------------- | ------------------------------------------ |
| `feat`     | Nouvelle fonctionnalité                       | `feat: ajout de l'authentification Google` |
| `fix`      | Correction de bug                             | `fix: correction du crash au login`        |
| `hotfix`   | Correction urgente en prod                    | `hotfix: patch faille sécurité token JWT`  |
| `refactor` | Refactoring sans changement fonctionnel       | `refactor: simplification du service auth` |
| `style`    | Formatage, espaces, virgules (pas de logique) | `style: formatage composant Header`        |
| `docs`     | Documentation uniquement                      | `docs: mise à jour du README`              |
| `test`     | Ajout ou modification de tests                | `test: ajout tests unitaires service user` |
| `chore`    | Maintenance, dépendances, config              | `chore: mise à jour des dépendances npm`   |
| `perf`     | Amélioration de performance                   | `perf: optimisation requête SQL dashboard` |
| `ci`       | Modification des pipelines CI/CD              | `ci: ajout du job de lint`                 |
| `revert`   | Annulation d'un commit précédent              | `revert: annulation feat login Google`     |

---

## Le scope (optionnel mais recommandé)

Le scope précise **quelle partie** du code est concernée.

```bash
feat(auth): ajout connexion via Google
fix(dashboard): correction affichage graphique vide
refactor(api): restructuration des routes utilisateur
```

---

## Règles

- ✅ Description en **minuscules**
- ✅ Description en **anglais** - les commits, comme le code, sont en anglais
- ✅ Description **courte** (moins de 72 caractères)
- ✅ Temps présent : "add..." et non "added..."
- ❌ Pas de point à la fin
- ❌ Pas de commit fourre-tout : **un commit = une chose précise**

---

## ❌ Ce qu'on ne fait PAS

```bash
# Trop vague
git commit -m "fix"
git commit -m "update"
git commit -m "wip"
git commit -m "aaaaa"

# Fourre-tout
git commit -m "feat: login + fix dashboard + refacto api + style header"
```

## ✅ Ce qu'on fait

```bash
git commit -m "feat(auth): add login form"
git commit -m "fix(auth): handle empty email validation"
git commit -m "style(auth): align submit button"
```
