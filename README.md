# refactor skills

Codex skills for post-implementation cleanup with parallel workers.

## Skills

- `$refactor`: scoped cleanup for files Codex changed in the current task only.
- `$refactor-all`: full cleanup for all current staged + unstaged tracked changes.

Both enforce nearest `AGENTS.md` guardrails, avoid destructive git operations, and preserve behavior unless explicitly requested otherwise.

## Install

```bash
mkdir -p ~/.codex/skills/local/refactor ~/.codex/skills/local/refactor-all
cp SKILL.md ~/.codex/skills/local/refactor/SKILL.md
cp refactor-all/SKILL.md ~/.codex/skills/local/refactor-all/SKILL.md
```

## Usage

```text
$refactor
$refactor-all
```
