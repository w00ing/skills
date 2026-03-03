---
name: commit-and-push
description: Finish local Git work by first using the `commit` skill to split and create Conventional Commits, then push the resulting commits to the remote tracking branch. Use when the user asks to commit and push changes.
---

# Commit And Push

Use the `commit` skill first to create clean logical commits.

Then push the branch.

## Steps

1. Run the `commit` skill workflow and ensure commits are complete.
2. Confirm branch and tracking remote.
```bash
git branch --show-current
git rev-parse --abbrev-ref --symbolic-full-name @{u}
```
3. Push commits.
```bash
git push
```
4. Verify clean state.
```bash
git status --short
```
