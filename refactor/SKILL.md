---
name: refactor
description: Scoped parallel refactor for files Codex changed in the current task. Use when the user says "$refactor" after asking for implementation. Build an explicit allowed file list from your own edits only, then improve code quality and low-risk efficiency in that list while enforcing AGENTS.md rules.
---

# Refactor

Refactor only files you changed in this task.

## Defaults

- Scope: files edited by Codex in current task/session.
- Parallelism: up to 4 workers (cap by file count).
- Strategy: single mode; choose depth by risk.

## Workflow

1. Read constraints first.
- Read nearest `AGENTS.md` in repo.
- If in submodule, read submodule `AGENTS.md` too.
- Apply stricter rule on conflicts.

2. Define allowed scope.
- Build explicit allowed file list from files you edited in this task.
- Never include files only because they are dirty.
- If ownership is uncertain for a file/hunk, exclude it.
- If allowed list is empty or unavailable, stop and ask for explicit files or suggest `$refactor-all`.

3. Validate scope against tree.
- Inspect current tree:

```bash
git status --short
git diff --name-status
git diff --cached --name-status
```

- Keep refactor scope as intersection of allowed list and currently modified tracked files.

4. Partition for parallel workers.
- Sort allowed files by path.
- Pick `workers = min(4, file_count)`.
- Split into non-overlapping chunks.
- Each file belongs to exactly one worker.

5. Spawn workers in parallel.
- Use `spawn_agent` with `agent_type: worker`.
- Each worker prompt must include:
  - owned file list
  - "You are not alone in the codebase; ignore edits from others unless in owned files."
  - goals: readability, maintainability, low-risk efficiency, AGENTS compliance
  - constraints: no destructive git commands, no out-of-scope edits, no risky semantic changes

Worker prompt template:

```text
Refactor owned files only:
<owned_files>

You are not alone in the codebase. Ignore edits from others unless they are in owned files.

Goals:
1) Improve readability/maintainability.
2) Improve efficiency where low-risk and justified.
3) Enforce AGENTS.md rules.
4) Preserve behavior; if unsure, stop and report risk.

Constraints:
- No destructive git commands.
- Do not edit files outside ownership.
- Do not revert unrelated user changes.

Deliver:
- files touched
- refactors applied
- efficiency notes
- risk flags
```

6. Collect and enforce boundaries.
- Wait for all workers.
- Reject/undo any out-of-scope file edits before finalizing.
- If conflicts appear, keep safer/smaller change.

7. Verify and report.
- Run smallest relevant checks.
- Prefer: `typecheck`, `test`, `lint` when available.
- Report:
  - allowed scope
  - touched files (must be subset of allowed scope)
  - refactor summary
  - efficiency improvements
  - AGENTS compliance notes
  - risks/follow-ups

## Guardrails

- Do not touch pre-existing local edits you did not make.
- Do not expand scope without explicit user approval.
- Keep behavior unchanged unless user explicitly asks for behavior change.
- Prefer explicit branching over dense ternaries in complex invocations.
