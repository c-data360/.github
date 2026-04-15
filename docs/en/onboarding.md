# 👋 Welcome to C-DATA³⁶⁰

This document is your starting point. Read it entirely before writing a single line of code.

## 📚 Documents to read in order

1. [Our GitFlow](./gitflow.md) - How we manage branches
2. [Commit Conventions](./conventions-commits.md) - How we name commits
3. [Pull Request Process](./process-pr.md) - How we submit our work
4. [Changesets](./changesets.md) - How we version code and generate changelogs

## 🛠️ Basic setup

### 1. Configure your Git identity with your work email

```bash
git config --global user.name "First Last"
git config --global user.email "firstname.lastname@c-data360.ai"
```

### 2. Clone the repository you're working on

```bash
git clone git@github.com:c-data360/repo-name.git
cd repo-name
```

### 3. Install dependencies and configure the environment

> See the relevant repo's README.

## ✅ Checklist before your first commit

- [ ] Git configured with your work email
- [ ] You've read the GitFlow
- [ ] You've read the commit conventions
- [ ] You've read the PR process
- [ ] You've read the Changesets doc
- [ ] You've created your branch from `develop` (never from `main`)
