---
name: humanize-german
description: Polish, rewrite, or review German public copy so it sounds natural to German readers while preserving meaning, product truth, SEO intent, and Shotomatic brand trust. Use for de landing pages, metadata, CTAs, FAQs, blog/changelog prose, translation polish, "AI-sounding German", "KI-Text", "Deutsch humanisieren", "Übersetzungsdeutsch", "Anglizismen entfernen", or German copy QA before publishing.
---

# Humanize German

Use this skill for German copy polish, especially customer-facing Shotomatic pages.

This is not an AI-detector bypass workflow. Treat it as editorial polish: make German text clear, idiomatic, and credible while keeping facts unchanged.

## Required Reads

Read these before editing:

- `AGENTS.md`
- target file or pasted source text
- `references/german-humanization-checklist.md`

When the copy is public-facing Shotomatic copy, also read:

- `.agents/skills/shotomatic-public-copy-qa/SKILL.md`
- one nearby English source page or product page if needed for product-truth calibration

## Operating Rules

- Preserve facts, prices, product capabilities, dates, URLs, legal claims, and tracking paths.
- Use contemporary Standard German for Germany unless the user specifies another market.
- Preserve Shotomatic product truth:
  - Mac app.
  - local-first screenshot capture/export workflows.
  - no unsupported cloud sync, team collaboration, Windows, Android, iOS, Germany hosting, payment, tax, or compliance claims.
- Prefer clear verbs over nominalized bureaucratic phrasing.
- Use Anglicisms only when they are standard in German tech/product copy or are product terms.
- Keep brand/product names in their official spelling: `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.
- Do not over-polish. Prefer small, high-signal changes unless the whole paragraph is translationese.

## Workflow

1. Identify the copy type: landing-page hero, metadata, CTA, FAQ, blog/changelog body, legal/support copy, or UI microcopy.
2. Audit for German AI/translationese patterns:
   - English sentence architecture copied into German
   - stiff nominal style
   - inflated product claims
   - repeated signposting
   - excess dashes, colons, lists, or three-part rhythms
   - unnatural Anglicisms or false friends
   - register mismatch between formal `Sie` copy and informal/direct marketing copy
3. Rewrite with the smallest edit that solves the problem.
4. Re-scan against `references/german-humanization-checklist.md`.
5. If editing repo files, patch directly and then run normal repo verification when code/content paths require it.

## German Copy Standard

Prefer:

- direct main clauses
- natural German word order
- active verbs
- concrete product workflow language
- `Sie` only when the surrounding German page already uses formal address
- concise button labels with infinitive verbs where appropriate

Avoid:

- formulas such as `Es ist wichtig zu beachten`, `Darüber hinaus`, `in der heutigen digitalen Welt`, `nicht nur ..., sondern auch ...`
- generic hype such as `revolutionär`, `bahnbrechend`, `nahtlos`, `leistungsstark`, `innovativ`, unless the sentence proves it
- English-style participle chains and abstract noun stacks
- filler claims like `mehr Effizienz`, `optimierte Workflows`, `maximale Produktivität` without concrete behavior
- translating every English product word literally when a German product idiom is better

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

- return the polished German text
- then give a short note listing the main changes

## Source Attribution

This skill distills reusable guidance from:

- Microsoft German Localization Style Guide
- Zulip German translation guidelines
- Marmbiz `humanizer-de` / Martin Moeller German Humanizer notes
- the general `humanizer` skill's AI-writing pattern taxonomy
