---
name: humanize-japanese
description: Polish, rewrite, or review Japanese public copy so it sounds natural to Japanese readers while preserving meaning, product truth, SEO intent, and Shotomatic brand trust. Use for ja landing pages, metadata, CTAs, FAQs, blog/changelog prose, translation polish, "AI-sounding Japanese", "機械翻訳っぽい", "日本語を自然に", "日本語文案", "AIっぽい日本語", or Japanese copy QA before publishing.
---

# Humanize Japanese

Use this skill for Japanese copy polish, especially customer-facing Shotomatic pages.

This is not an AI-detector bypass workflow. Treat it as editorial polish: make Japanese text clear, natural, and trustworthy while keeping facts unchanged.

## Required Reads

Read these before editing:

- `AGENTS.md`
- target file or pasted source text
- `references/japanese-humanization-checklist.md`

When the copy is public-facing Shotomatic copy, also read:

- `.agents/skills/shotomatic-public-copy-qa/SKILL.md`
- one nearby English source page or product page if needed for product-truth calibration

## Operating Rules

- Preserve facts, prices, product capabilities, dates, URLs, legal claims, and tracking paths.
- Use contemporary Japanese for Japan unless the user specifies another market.
- Preserve Shotomatic product truth:
  - Mac app.
  - local-first screenshot capture/export workflows.
  - no unsupported cloud sync, team collaboration, Windows, Android, iOS, Japan hosting, payment, tax, or compliance claims.
- Prefer natural Japanese clause order over English mirror structure.
- Keep the page's chosen register consistent. Do not mix `です・ます` and `だ・である` in the same passage.
- Keep brand/product names in their official spelling: `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.
- Do not over-polish. Prefer small, high-signal changes unless the whole paragraph is translationese.

## Workflow

1. Identify the copy type: landing-page hero, metadata, CTA, FAQ, blog/changelog body, legal/support copy, or UI microcopy.
2. Audit for Japanese AI/translationese patterns:
   - English subject-first structure forced into Japanese
   - overexplicit pronouns and possessives
   - repeated `ことで`, `ため`, `可能です`, `実現します`
   - long noun chains and four-kanji process nouns
   - duplicate particles, repeated conjunctions, and too many `、`
   - inflated marketing words without concrete behavior
   - unnatural half-width/full-width handling around Latin terms and numbers
3. Rewrite with the smallest edit that solves the problem.
4. Re-scan against `references/japanese-humanization-checklist.md`.
5. If editing repo files, patch directly and then run normal repo verification when code/content paths require it.

## Japanese Copy Standard

Prefer:

- short sentences mixed with a few explanatory sentences
- omitted subjects when context is clear
- concrete verbs and product actions
- natural `です・ます` customer-facing tone
- UI labels that sound like Japanese software copy
- Japanese punctuation and spacing conventions around Latin product terms

Avoid:

- `〜することができます` when `〜できます` or an active verb works
- `〜を実現します`, `〜を提供します`, `〜を可能にします` as generic claim endings
- `シームレス`, `革新的`, `強力`, `包括的`, `最適化` unless the sentence proves the claim
- repeated `また`, `さらに`, `加えて` signposting
- English-like `あなたの...` possessives where Japanese would omit them

## Output

When asked to fix files:

- patch the text directly
- report the edited files
- mention any verification run

When asked to review:

- findings first
- file and line references when available
- classify each issue as `truth`, `tone`, `localization`, `format`, or `SEO`
- include suggested replacement copy when useful

When asked to humanize pasted text:

- return the polished Japanese text
- then give a short note listing the main changes

## Source Attribution

This skill distills reusable guidance from:

- Microsoft Japanese Localization Style Guide
- textlint-ja Japanese and technical-writing presets
- textlint-ja AI-writing preset
- JTF Style Guide for Translators Working into Japanese
- the general `humanizer` skill's AI-writing pattern taxonomy
