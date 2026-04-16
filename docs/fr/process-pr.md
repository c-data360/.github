# 🔁 Process de Pull Request

## Règle fondamentale

> **Aucun code n'entre dans `develop` ou `main` sans Pull Request reviewée.**
> Pas d'exception. Même si tu es pressé. Même si "c'est juste un petit fix".

---

## Quand ouvrir une PR ?

- ✅ Ta fonctionnalité est terminée et testée localement
- ✅ Ton code compile sans erreur
- ✅ Tu as vérifié qu'il n'y a pas de `console.log` ou code de debug oublié
- ✅ Ta branche est à jour avec `develop` (ou `main` pour un hotfix)

```bash
# Mettre à jour sa branche avant d'ouvrir la PR
git checkout develop
git pull origin develop
git checkout feature/ma-fonctionnalite
git merge develop
# Résoudre les conflits si nécessaire, puis push
git push origin feature/ma-fonctionnalite
```

---

## Comment ouvrir une PR

1. Aller sur le repo GitHub
2. Cliquer sur **"Compare & pull request"**
3. Vérifier : **base** = `develop` (ou `main` pour hotfix), **compare** = ta branche
4. Remplir **entièrement** le template de PR
5. Assigner le bon **reviewer**
6. Ajouter les **labels** appropriés (`feature`, `fix`, `hotfix`...)
7. Lier l'**issue** correspondante si elle existe (`Closes #42`)

---

## Être un bon reviewer

- ✅ Reviewer dans les **24h** ouvrées
- ✅ Commenter de façon **constructive et précise**
- ✅ Approuver seulement si tu es **convaincu** que le code est correct
- ❌ Ne pas approuver par politesse ou pour débloquer vite

---

## Après le merge

- La branche est **supprimée automatiquement** (configuré dans l'organisation)
- Tu reviens sur `develop` et tu pull :

```bash
git checkout develop
git pull origin develop
```
