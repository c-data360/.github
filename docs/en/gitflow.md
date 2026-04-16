# 🌿 GitFlow

## Overview

```
main          ← Production. Stable. Sacred. Never push directly.
│
├── hotfix/   ← Urgent production fix. Created from main.
│
develop       ← Integration branch. Always up to date. Base for all development.
│
├── feature/  ← New feature. Created from develop.
│
└── release/  ← Version preparation. Created from develop.
```

---

## 📌 Absolute rules

> ❌ **Never push directly to `main` or `develop`**
> ✅ **Everything goes through a reviewed Pull Request**

---

## 🔄 Feature lifecycle

### 1. Create your branch from `develop`

```bash
git checkout develop
git pull origin develop
git checkout -b feature/feature-name
```

### 2. Develop and commit

```bash
git add .
git commit -m "feat: short description of what you did"
git push origin feature/feature-name
```

### 3. Open a Pull Request

- Base: `develop`
- Compare: `feature/feature-name`
- Fill in the PR template
- Assign a reviewer

### 4. After approval → merge into `develop` then delete the branch

---

## 🚨 Hotfix lifecycle

```bash
# From main only
git checkout main
git pull origin main
git checkout -b hotfix/short-description

# ... fix the bug ...

git commit -m "fix: description of the fix"
git push origin hotfix/short-description

# Open a PR to main AND a PR to develop
```

> ⚠️ A hotfix must always be merged into **main AND develop** to preserve the fix.

---

## 🚀 Release lifecycle

```bash
# From develop
git checkout develop
git pull origin develop
git checkout -b release/v1.2.0

# Final adjustments, version bump...
git commit -m "chore: bump version to 1.2.0"
git push origin release/v1.2.0

# PR to main, then PR to develop
```

---

## 📛 Branch naming

| Type          | Format                    | Example                         |
| ------------- | ------------------------- | ------------------------------- |
| Feature       | `feature/feature-name`    | `feature/oauth-authentication`  |
| Urgent fix    | `hotfix/short-description`| `hotfix/fix-login-crash`        |
| Release       | `release/vX.Y.Z`          | `release/v1.2.0`                |

### Naming rules

- ✅ **In English** - like commits and code
- ✅ Lowercase only
- ✅ Hyphens `-` to separate words (no underscore `_`, no spaces)
- ✅ Short but descriptive name
- ❌ No special characters
- ❌ No additional `/` in the name
