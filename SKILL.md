---
name: refactor
description: Parallel refactor orchestrator for active git changes. Use when the user says "$refactor", "run refactor", or asks to clean up current edits after implementation. Inspect staged+unstaged tracked diffs, spawn parallel workers, improve code quality and efficiency, and enforce nearest AGENTS.md rules while preserving behavior.
---

# Refactor

Run a parallel, behavior-safe cleanup pass on current changes.

## Defaults

- Scope: staged + unstaged tracked changes.
- Parallelism: up to 4 workers (cap by file count).
- Strategy: single mode; choose refactor depth by risk.

## Workflow

1. Ground rules first.
- Read nearest `AGENTS.md` in current repo.
- If in a submodule, read submodule `AGENTS.md` too.
- Apply stricter rule on conflicts.

2. Build refactor scope inline.
- Collect unstaged + staged paths:

```bash
git diff --name-only --diff-filter=d
git diff --cached --name-only --diff-filter=d
```

- Merge, dedupe, keep tracked files only.
- If scope empty: report "no tracked staged/unstaged changes" and stop.

3. Partition files for parallel workers.
- Sort scope list by path.
- Pick `workers = min(4, file_count)`.
- Split sorted files into contiguous chunks of near-equal size.
- Each file must belong to exactly one worker.

4. Spawn workers in parallel.
- Use `spawn_agent` with `agent_type: worker` for each chunk.
- Give each worker explicit file ownership.
- Worker prompt must include:
  - "You are not alone in the codebase; ignore edits from others unless in owned files."
  - goals: code quality, efficiency, AGENTS compliance, behavior preservation
  - constraints: no destructive git commands; no unrelated edits; escalate risky semantic changes

Worker prompt template:

```text
Refactor owned files only:
<owned_files>

You are not alone in the codebase. Ignore edits from others unless they are in owned files.

Goals:
1) Improve readability/maintainability (extract helpers, simplify control flow, remove duplication).
2) Improve efficiency where low-risk and justified.
3) Enforce AGENTS.md rules in this repo/submodule.
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

5. Collect and reconcile.
- Wait for all workers.
- If overlap/conflict appears, keep safer/smaller edit and reconcile manually.
- Keep final edits scoped unless dependency-coupled change is required and documented.

6. Verify.
- Run smallest relevant checks for touched code.
- Prefer scripts in this order when available: `typecheck`, `test`, `lint`.
- If unavailable or failing, report exact gap/error.

7. Report concise summary.
- Scope analyzed
- Parallel plan (workers + chunk map)
- Quality refactors
- Efficiency improvements
- AGENTS compliance notes
- Risks/follow-ups

## Guardrails

- Keep behavior unchanged unless user explicitly asks for behavior change.
- Prefer explicit branching over dense ternaries in complex invocations.
- Keep edits scoped; avoid opportunistic repo-wide cleanup.
- Stop and ask user when risk is non-trivial or requirements conflict.
