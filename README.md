# skills

Codex skill collection.

## Included skills

- `commit`
- `commit-all`
- `commit-and-push`
- `commit-all-and-push`
- `blog-post`
- `grill-me`
- `grill-with-docs`
- `refactor`
- `refactor-all`

## Install

```bash
for s in commit commit-all commit-and-push commit-all-and-push blog-post grill-me grill-with-docs refactor refactor-all; do
  mkdir -p "$HOME/.codex/skills/local/$s"
  cp -R "$s"/. "$HOME/.codex/skills/local/$s"/
done
```

## Invocation labels

- `$commit`
- `$commit-all`
- `$commit-and-push`
- `$commit-all-and-push`
- `$blog-post`
- `$grill-me`
- `$grill-with-docs`
- `$refactor`
- `$refactor-all`
