---
name: baton
description: Keep the current model in charge of decisions and orchestration; delegate execution to Luna Max. Use when the user invokes $baton or asks for Luna delegation.
---

# Baton

The current model in this session is the conductor: own decisions, task decomposition, integration, and final acceptance. Spawn Luna workers for execution; do not spawn a separate orchestrator.

1. Spawn as many Luna workers as the task needs. Delegate bounded execution; keep open-ended judgment, trivial work, and tightly coupled work with the lead. Parallelize only independent tasks with non-overlapping write scopes; sequence dependencies.
2. Explicitly select `model="gpt-6-luna"` and reasoning effort `max` using the available subagent tool. If it supports `fork_turns`, use `fork_turns="none"` and provide the relevant context yourself; full-history forks inherit the parent model. If Luna Max cannot be selected, report the limitation instead of silently substituting another model.
3. Before delegating, decide the approach, scope, and acceptance criteria. Brief each worker with the outcome, these decisions, relevant context, constraints, and useful verification. Use file references for bulky material.
4. Workers may choose routine implementation details within the plan. They must escalate unresolved decisions, required plan changes, or blockers to the lead before continuing affected work. Preserve others' edits; workers must not spawn further agents. Coordinate ownership before changing a worker's files.
5. Require a concise return: **result, changed files or evidence references, verification results, unresolved issues**. Inspect the actual artifacts and resolve material findings; a worker's completion report alone does not establish correctness.
6. The lead diagnoses failures before retrying, adjusts the plan or takes over, and collects all required results for proportionate integration checks. Avoid unchanged retries; report the outcome and any remaining gaps.
