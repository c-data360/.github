# 🔁 Pull Request Process - C-DATA³⁶⁰

## Fundamental rule

> **No code enters `develop` or `main` without a reviewed Pull Request.**
> No exceptions. Even if you're in a hurry. Even if "it's just a small fix".

---

## When to open a PR?

- ✅ Your feature is complete and tested locally
- ✅ Your code compiles without errors
- ✅ You've checked there are no forgotten `console.log` or debug code
- ✅ Your branch is up to date with `develop` (or `main` for a hotfix)

```bash
# Update your branch before opening the PR
git checkout develop
git pull origin develop
git checkout feature/my-feature
git merge develop
# Resolve conflicts if needed, then push
git push origin feature/my-feature
```

---

## How to open a PR

1. Go to the GitHub repo
2. Click **"Compare & pull request"**
3. Check: **base** = `develop` (or `main` for hotfix), **compare** = your branch
4. Fill in the PR template **entirely**
5. Assign the right **reviewer**
6. Add the appropriate **labels** (`feature`, `fix`, `hotfix`...)
7. Link the corresponding **issue** if it exists (`Closes #42`)

---

## Being a good reviewer

- ✅ Review within **24 business hours**
- ✅ Comment in a **constructive and precise** way
- ✅ Approve only if you are **convinced** the code is correct
- ❌ Do not approve out of politeness or to unblock quickly

---

## After the merge

- The branch is **deleted automatically** (configured at the organization level)
- Go back to `develop` and pull:

```bash
git checkout develop
git pull origin develop
```
