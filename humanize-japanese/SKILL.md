---
name: humanize-japanese
description: Polish, rewrite, or review Japanese public copy so it sounds natural to Japanese readers while preserving meaning, verified product claims, search intent, and the established product voice. Use for ja landing pages, metadata, CTAs, FAQs, blog/changelog prose, translation polish, "AI-sounding Japanese", "機械翻訳っぽい", "日本語を自然に", "日本語文案", "AIっぽい日本語", or Japanese copy QA before publishing.
---

# Humanize Japanese

Use this skill for Japanese copy polish, especially public-facing product copy.

This is not an AI-detector bypass workflow. Treat it as editorial polish: make Japanese text clear, natural, and trustworthy while keeping facts unchanged.

## Required Reads

Read these before editing:

- `AGENTS.md`
- target file or pasted source text
- `references/japanese-humanization-checklist.md`

For product-specific claims, consult current project documentation or an authoritative product source when available.

## Operating Rules

- Preserve facts, prices, product capabilities, dates, URLs, legal claims, and tracking paths.
- Use contemporary Japanese for Japan unless the user specifies another market.
- Verify product claims against user-provided or project sources, such as current product documentation or public pages.
- Do not invent features, platform support, integrations, privacy or security guarantees, pricing, availability, or compliance claims. Narrow or flag claims that cannot be verified.
- Prefer natural Japanese clause order over English mirror structure.
- Keep the page's chosen register consistent. Do not mix `です・ます` and `だ・である` in the same passage.
- Keep product and brand names in their official spelling.
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
