---
name: no-comments
description: "Sweep comments out of a diff or files with a fresh reviewer, fix the code the comments were apologizing for, and offer to encode real constraints as types, tests or lint instead of prose."
disable-model-invocation: true
license: MIT
metadata:
  source: cursor/plugins/pstack/skills/no-comments@ab1f702ce8e8b6557edb56b09f52cde8bfb83f17, with pstack/agents/comment-sicko.md inlined (MIT, Copyright (c) 2026 Lauren Tan)
---

# No comments

A comment that explains code is a sign the code could say it instead. Kill the comment, then make
the code say it. A fresh reviewer does the killing. You audit its work and fix what it flagged.

## Scope

Use the files or diff the caller names. Otherwise use the diff against the base branch, default
`origin/main`, including the working tree. Other sessions may share this checkout: leave out changes you did not make.

## Steps

1. **Sweep.** Spawn a fresh subagent with the scope and the Sweep rules below, word for word. It
   edits comments only and reports. Without subagents, do the sweep yourself first, then audit it
   as a separate pass.
2. **Audit the report and the diff.** Reject any application-code edit, any edit outside the
   scope, any deleted comment the keep list protects, any `MUST KILL` with a wrong reason, and any
   flag on code that is intentionally kept. A reshape flag on a surprise in our own code stays
   actionable. Do not restore that comment. Check for lint and TypeScript suppressions in scope
   that the sweep missed. A suppression that hides a correctness or safety rule is a `MUST KILL`.
   Restore a deletion only when it fits a keep clause exactly and you can show it. Before
   accepting a thin `IMPORTANT` or `do not remove` kill or keep, prove it as described in Proving a
   claim. An ambiguous kill stays killed. A refuted or still ambiguous keep is deleted. If the
   report is wrong, revert it and rerun the sweep once with the failure named. If the second one
   is wrong too, stop and report the run as failed.
3. **Fix the trivial flags directly.** Delete the dead path, drop the parameter, call the real
   API. When a fix needs a new shape, sketch it first, once, for all accepted flags together:
   types, signatures and module boundaries, with bodies left as `not implemented`. Stop at the
   sketch. Step 4 builds it.
4. **Fix the root cause, inside the scope.** Make the smallest change that removes the reason for
   the comment, and remove every workaround the flags name. Find the first place the code went
   wrong, not where it showed. A guard is a fix only when the state it handles is legitimate.
   Never add a guard to quiet a symptom. Integrate the change as if it had been a day-one
   assumption, not bolted on. When the root cause is outside the scope, land the smallest fix
   inside it and report the rest as open. Neither rule widens the scope.
5. **Encode constraints.** A comment that says `do not remove`, `do not change wording`, or `talk
   to X before changing` is a constraint. Keep the ones about things we cannot change. For the
   rest, offer the cheapest encoding inside the scope: a type, a runtime check, a test, or a lint
   rule. Wait for the person's approval. A run with nobody watching needs approval given up front.
   If approved, encode it, then delete the comment. Otherwise delete it, report the constraint as
   open, and sketch the work outside the scope.
6. **Report** the deletion count, restored comments, reruns, the sketch, fixes, encoding offers,
   encodings made, constraints left unenforced, and other open work.

## Proving a claim

To prove a comment's claim, read the code around it and its callers until the behavior is plain.
For why it is that way, read its history: `git log -L <start>,<end>:<file>`, `git blame`, and the
pull request behind the commit (`gh pr view`). A claim holds only when it is true today on a path
that still runs.

## Sweep rules

Give these to the sweep subagent as its whole brief.

> You hate comments. Take the scope you were given. Narration, banners, commented-out code and
> sermons justifying a workaround all go.
>
> Only these may stay:
>
> - Legal or license headers.
> - Non-obvious behavior forced by an external dependency, platform, vendor or protocol we cannot
>   reshape. A surprise in our own code is not that. Delete its comment and mark the exact symbol
>   `MUST KILL`, for a rename, an extraction, a type or a redesign that makes the behavior obvious
>   without prose.
> - Formatter ignores such as `// prettier-ignore`. A lint suppression stays only when its rule
>   is faulty, pedantic or about style.
> - Doc comments that define a public API contract.
> - Issue or RFC links that explain a constraint the code cannot express.
>
> That list is the only exception. When unsure whether a clause applies, the comment goes.
>
> `oxlint-disable`, `eslint-disable`, `@ts-ignore`, `@ts-expect-error` and similar suppressions are
> suspect. Look up the rule. If it catches real bugs or protects correctness or safety, delete the
> suppression and mark the exact guilty symbol `MUST KILL`.
>
> `IMPORTANT`, `do not remove`, `too risky`, `fine for now` and long justifications are a lead, not
> proof. Read the nearby code first. If the claim is not obvious there, trace the symbol through
> its callers and its git history. Only a gotcha from the keep list, proven true today on a live
> path, stays. A surprise in our own code goes, with the reshape flag above. Doubt after the search
> means it goes.
>
> A long justification without a proven exception is a confession. Delete it. Never shorten it
> into a smaller excuse. Mark the exact guilty symbol `MUST KILL` and stop there.
>
> Every flag names code inside the scope and is true. Invent nothing. Edit comments and name
> refactor targets only. Never write application code.
>
> Report only: the files touched, the deletion count, each `MUST KILL` flag in one line, and what
> you skipped.
