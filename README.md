# skills

Codex skill collection.

## Included skills

- [baton](baton/SKILL.md)
- [commit](commit/SKILL.md)
- [commit-all](commit-all/SKILL.md)
- [commit-and-push](commit-and-push/SKILL.md)
- [commit-all-and-push](commit-all-and-push/SKILL.md)
- [blog-post](blog-post/SKILL.md)
- [codex-imagegen](codex-imagegen/SKILL.md)
- [grill-me](grill-me/SKILL.md)
- [grill-with-docs](grill-with-docs/SKILL.md)
- [humanizer](humanizer/SKILL.md)
- [humanize-chinese](humanize-chinese/SKILL.md)
- [humanize-german](humanize-german/SKILL.md)
- [humanize-italian](humanize-italian/SKILL.md)
- [humanize-japanese](humanize-japanese/SKILL.md)
- [humanize-korean](humanize-korean/SKILL.md)
- [refactor](refactor/SKILL.md)
- [refactor-all](refactor-all/SKILL.md)

## Install

Replace `<skill-name>` with a name from the list above (for example, `baton`) to install it globally for Codex.

```bash
npx skills add w00ing/skills --skill "<skill-name>" --agent codex --global
```

`codex-imagegen` lets an agent without an image model use Codex's, so install it for that agent and keep the [Codex CLI](https://github.com/openai/codex) installed and signed in:

```bash
npx skills add w00ing/skills --skill codex-imagegen --agent "<agent>" --global
```

## Invocation labels

- `$baton`
- `$commit`
- `$commit-all`
- `$commit-and-push`
- `$commit-all-and-push`
- `$blog-post`
- `$codex-imagegen`
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
