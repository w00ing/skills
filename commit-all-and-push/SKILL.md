---
name: commit-all-and-push
description: Commit all local changes as a single Conventional Commit by using the `commit-all` skill, then push commits to the remote tracking branch. Use when the user explicitly asks to commit everything and push.
---

# Commit All And Push

Use the `commit-all` skill first, then push.

## Steps

1. Run the `commit-all` skill workflow and complete the commit.
2. Confirm branch and upstream.
```bash
git branch --show-current
git rev-parse --abbrev-ref --symbolic-full-name @{u}
```
3. Push.
```bash
git push
```
4. Verify state.
```bash
git status --short
```
