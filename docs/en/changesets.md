# 📦 Changesets — Versioning & Changelog

We use **[Changesets](https://github.com/changesets/changesets)** to manage semantic versioning and automatic changelog generation.

---

## Principle

Every significant code change must be accompanied by a **changeset** — a small file describing the nature of the change (`patch`, `minor`, `major`) and a human-readable summary.

These files accumulate in `.changeset/` across PRs, then are consumed during a release to:

1. Automatically bump the versions of affected packages
2. Generate entries in `CHANGELOG.md`

---

## When to create a changeset?

| Situation | Changeset? |
|---|---|
| New user-facing feature | ✅ `minor` |
| Bug fix | ✅ `patch` |
| Breaking change (API, contract, schema) | ✅ `major` |
| Internal refactoring, style, docs | ❌ No |
| Dependency updates (no API impact) | ❌ No |

---

## Workflow

### 1. Create a changeset after your change

```bash
pnpm changeset
```

An interactive prompt will ask:
- The affected package(s)
- The bump type (`patch`, `minor`, `major`)
- A summary of the change (displayed in the changelog)

A file is created in `.changeset/` — **commit it with your code**.

```bash
git add .changeset/
git commit -m "chore: add changeset for feat(auth)"
```

### 2. On release — bump versions

```bash
pnpm changeset:version
```

This command:
- Reads all `.changeset/` files
- Updates the affected `package.json` files
- Generates / updates `CHANGELOG.md` files
- Deletes the consumed `.changeset/` files

Commit the result:

```bash
git add .
git commit -m "chore: version packages"
```

### 3. Publish (if applicable)

```bash
pnpm changeset publish
```

> In this project, releases are automated via GitHub Actions (`.github/workflows/release.yml`). The workflow automatically creates a release PR whenever it detects unconsumed changesets on `main`.

---

## Bump types

| Type | When | Version example |
|---|---|---|
| `patch` | Bug fix, minor correction | `1.2.3` → `1.2.4` |
| `minor` | Backward-compatible new feature | `1.2.3` → `1.3.0` |
| `major` | Breaking change | `1.2.3` → `2.0.0` |

---

## Rules

- ✅ One changeset per feature or fix (one PR = one changeset)
- ✅ The changeset message is written to be read in a changelog (not like a commit)
- ✅ Commit the `.changeset/` file in the same PR as the code
- ❌ Do not manually bump `package.json` files
- ❌ Do not edit `CHANGELOG.md` files by hand
