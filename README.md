# skills

Codex skill collection.

## Included skills

- `commit`
- `commit-all`
- `commit-and-push`
- `commit-all-and-push`
- `refactor`
- `refactor-all`

## Install

```bash
for s in commit commit-all commit-and-push commit-all-and-push refactor refactor-all; do
  mkdir -p "$HOME/.codex/skills/local/$s"
  cp "$s/SKILL.md" "$HOME/.codex/skills/local/$s/SKILL.md"
done
```

## Invocation labels

- `$commit`
- `$commit-all`
- `$commit-and-push`
- `$commit-all-and-push`
- `$refactor`
- `$refactor-all`
