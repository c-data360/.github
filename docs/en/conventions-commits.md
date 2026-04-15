# 📝 Commit Conventions - C-DATA³⁶⁰

We follow the **[Conventional Commits](https://www.conventionalcommits.org/)** standard.

## Format

```
type(scope): short description

[optional body]

[optional footer]
```

---

## Commit types

| Type       | When to use                               | Example                                 |
| ---------- | ----------------------------------------- | --------------------------------------- |
| `feat`     | New feature                               | `feat: add Google authentication`       |
| `fix`      | Bug fix                                   | `fix: resolve login crash`              |
| `hotfix`   | Urgent production fix                     | `hotfix: patch JWT token security flaw` |
| `refactor` | Refactoring without functional change     | `refactor: simplify auth service`       |
| `style`    | Formatting, whitespace, commas (no logic) | `style: format Header component`        |
| `docs`     | Documentation only                        | `docs: update README`                   |
| `test`     | Add or modify tests                       | `test: add unit tests for user service` |
| `chore`    | Maintenance, dependencies, config         | `chore: update npm dependencies`        |
| `perf`     | Performance improvement                   | `perf: optimize SQL query in dashboard` |
| `ci`       | CI/CD pipeline changes                    | `ci: add lint job`                      |
| `revert`   | Revert a previous commit                  | `revert: revert feat Google login`      |

---

## The scope (optional but recommended)

The scope specifies **which part** of the codebase is affected.

```bash
feat(auth): add Google login
fix(dashboard): fix empty chart display
refactor(api): restructure user routes
```

---

## Rules

- ✅ Description in **lowercase**
- ✅ Description in **English** - commits, like code, are in English
- ✅ **Short** description (less than 72 characters)
- ✅ Present tense: "add..." not "added..."
- ❌ No period at the end
- ❌ No catch-all commits: **one commit = one specific thing**

---

## ❌ What we DON'T do

```bash
# Too vague
git commit -m "fix"
git commit -m "update"
git commit -m "wip"
git commit -m "aaaaa"

# Catch-all
git commit -m "feat: login + fix dashboard + refacto api + style header"
```

## ✅ What we DO

```bash
git commit -m "feat(auth): add login form"
git commit -m "fix(auth): handle empty email validation"
git commit -m "style(auth): align submit button"
```
