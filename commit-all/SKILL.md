---
name: commit-all
description: Commit all local changes in the current repository, including tracked, untracked, and deletions, as a single Conventional Commit. Use only when the user explicitly wants all changes committed together.
---

# Commit All

Commit every local change in one commit.

## Steps

1. Review what will be committed.
```bash
git status --short
git diff --name-status
```

2. Stage everything.
```bash
git add -A
```

3. Commit using Conventional Commits format.
```bash
git commit -m "<type>(<scope>): <single intent>"
```
- Use `type(scope)!: subject` when there is a breaking change.
- Prefer: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `build`, `ci`, `perf`.

4. Verify commit and remaining state.
```bash
git log --oneline --decorate -n 1
git status --short
```
