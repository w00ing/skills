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
- `humanizer`
- `humanize-chinese`
- `humanize-german`
- `humanize-italian`
- `humanize-japanese`
- `humanize-korean`
- `refactor`
- `refactor-all`

## Install

```bash
skills=(
  commit
  commit-all
  commit-and-push
  commit-all-and-push
  blog-post
  grill-me
  grill-with-docs
  humanizer
  humanize-chinese
  humanize-german
  humanize-italian
  humanize-japanese
  humanize-korean
  refactor
  refactor-all
)

for s in "${skills[@]}"; do
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
- `$humanizer`
- `$humanize-chinese`
- `$humanize-german`
- `$humanize-italian`
- `$humanize-japanese`
- `$humanize-korean`
- `$refactor`
- `$refactor-all`
