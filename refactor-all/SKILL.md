---
name: refactor-all
description: Full-scope parallel refactor for active repository changes. Use when the user explicitly says "$refactor-all" or requests broad cleanup across all current staged+unstaged tracked edits, not just files Codex touched.
---

# Refactor All

Refactor all current tracked changes in the working tree.

## Defaults

- Scope: staged + unstaged tracked modified files.
- Parallelism: up to 4 workers (cap by file count).
- Strategy: single mode; choose depth by risk.

## Workflow

1. Read constraints first.
- Read nearest `AGENTS.md` in repo.
- If in submodule, read submodule `AGENTS.md` too.
- Apply stricter rule on conflicts.

2. Build full scope.

```bash
git diff --name-only --diff-filter=d
git diff --cached --name-only --diff-filter=d
```

- Merge + dedupe paths.
- Keep tracked files only.
- If empty, report and stop.

3. Partition for parallel workers.
- Sort files by path.
- Pick `workers = min(4, file_count)`.
- Split into non-overlapping chunks.

4. Spawn workers in parallel.
- Use `spawn_agent` with `agent_type: worker` per chunk.
- Worker prompt must include:
  - owned file list
  - "You are not alone in the codebase; ignore edits from others unless in owned files."
  - goals: readability, maintainability, low-risk efficiency, AGENTS compliance
  - constraints: no destructive git commands, no out-of-scope edits, escalate risky semantic changes

5. Collect and reconcile.
- Wait for all workers.
- Resolve overlap/conflict conservatively.
- Keep behavior stable unless explicitly requested otherwise.

6. Verify and report.
- Run smallest relevant checks.
- Prefer: `typecheck`, `test`, `lint` when available.
- Report scope, touched files, improvements, compliance notes, risks.

## Guardrails

- No destructive git commands.
- No edits outside assigned worker ownership.
- Do not revert unrelated user changes.
- Stop and escalate when semantic risk is non-trivial.
