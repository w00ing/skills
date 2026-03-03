---
name: commit
description: Split only the changes you made into clear, reviewable Git commits grouped by behavior or concern. Use when Codex must avoid pre-existing local edits, stage partial hunks safely, and create Conventional Commits messages for your changes.
---

# Split Logical Commits

Create small, coherent commits from the changes you made only.

## Workflow

1. Define the allowed scope for your changes.
- Build an explicit allowed file list from files you edited.
- Never stage files outside that list, even if they are modified.
- If ownership is uncertain for a file or hunk, leave it unstaged.
- Ignore changes you did not make; do not fix, format, or reorganize them.

2. Inspect the current tree.
```bash
git status --short
git diff --name-status
git diff --cached --name-status
```

3. Build a commit plan before staging.
- Group changes by intent, not by file type.
- Prefer one behavior change or refactor concern per commit.
- Keep unrelated formatting changes in separate commits.
- Write a one-line purpose for each planned commit.

4. Stage only the first logical slice from allowed files.
```bash
git add -p
# For fully-related files:
git add <path>
# If you stage too much:
git restore --staged <path>
```
- Do not stage paths outside the allowed file list.

5. Verify the staged diff matches exactly one intent.
```bash
git diff --cached
```
- If mixed concerns appear, unstage and restage more narrowly.
- If unrelated changes appear, unstage them immediately.

6. Run the smallest relevant checks for that slice.
- Prefer targeted tests/typechecks for files touched by the staged diff.
- If no targeted checks exist, run the standard project checks required before commit.

7. Commit with a Conventional Commits message.
```bash
git commit -m "<type>(<scope>): <single intent>"
```
- Use Conventional Commits format: `type(scope)!: subject`.
- Use `!` only for breaking changes.
- Prefer these types: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `build`, `ci`, `perf`.
- Keep subject imperative and specific.
- Include a short body when rationale is non-obvious.

8. Repeat staging, verification, and commit steps until all changes you made are committed.

9. Validate final state.
```bash
git status --short
git log --oneline --decorate -n <N>
```
- Confirm all changes you made are committed.
- Remaining uncommitted files should be pre-existing or intentionally excluded.
- Confirm commit order reads as a logical story.

## Heuristics For Good Boundaries

- Separate pure renames/moves from behavioral edits when practical.
- Separate mechanical refactors from bug fixes.
- Separate test-only changes unless tests are inseparable from behavior.
- Keep each commit independently understandable and bisect-friendly.

## Guardrails

- Do not rewrite or discard user changes to simplify commit splitting.
- Do not include pre-existing local edits that you did not make.
- Do not touch or clean up unrelated changes you did not make; leave them as-is.
- Avoid destructive commands like `git reset --hard`.
- Prefer `git add -p` and `git restore --staged` for safe iteration.
