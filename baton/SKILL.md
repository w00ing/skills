---
name: baton
description: Coordinate Luna Max subagents while the lead model plans, integrates, and reviews. Use when the user invokes $baton or asks for Luna delegation.
---

# Baton

Keep the current model as conductor: own task decomposition, architectural decisions, integration, and final acceptance. Delegate bounded execution to Luna.

1. Spawn as many Luna workers as the task needs. Delegate tasks that can run independently alongside useful lead work. Keep trivial or tightly coupled work local. Parallelize only independent tasks with non-overlapping write scopes; sequence dependencies.
2. Explicitly select `model="gpt-6-luna"` and reasoning effort `max` using the available subagent tool. If it supports `fork_turns`, use `fork_turns="none"` and provide the relevant context yourself; full-history forks inherit the parent model. If Luna Max cannot be selected, report the limitation instead of silently substituting another model.
3. Give each worker a self-contained brief: **outcome, relevant context, scope and constraints, completion criteria, useful verification**. Include only what changes its work; use file references for bulky material.
4. Tell workers to stay within their assigned scope, preserve others' edits, and return decisions or blockers to you. Workers must not spawn further agents. Coordinate ownership before changing a live worker's files.
5. Require a concise return: **result, changed files or evidence references, verification results, unresolved issues**. Inspect the actual artifacts and resolve material findings; a worker's completion report alone does not establish correctness.
6. When work fails, diagnose the cause before retrying. Clarify the brief, narrow the task, or take over after coordinating ownership. Avoid unchanged retry loops. Collect all required results and complete proportionate integration checks before reporting the outcome and any remaining gaps.
