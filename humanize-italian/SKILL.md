---
name: humanize-italian
description: Polish, rewrite, or review Italian public copy so it sounds natural to Italian readers while preserving meaning, product truth, SEO intent, and Shotomatic brand trust. Use for it landing pages, metadata, CTAs, FAQs, blog/changelog prose, translation polish, "AI-sounding Italian", "italiano da IA", "italiano tradotto", "Itanglese", "umanizza italiano", or Italian copy QA before publishing.
---

# Humanize Italian

Use this skill for Italian copy polish, especially customer-facing Shotomatic pages.

This is not an AI-detector bypass workflow. Treat it as editorial polish: make Italian text clear, idiomatic, and trustworthy while keeping facts unchanged.

## Required Reads

Read these before editing:

- `AGENTS.md`
- target file or pasted source text
- `references/italian-humanization-checklist.md`

When the copy is public-facing Shotomatic copy, also read:

- `.agents/skills/shotomatic-public-copy-qa/SKILL.md`
- one nearby English source page or product page if needed for product-truth calibration

## Operating Rules

- Preserve facts, prices, product capabilities, dates, URLs, legal claims, and tracking paths.
- Use contemporary Italian for Italy unless the user specifies another market.
- Preserve Shotomatic product truth:
  - Mac app.
  - local-first screenshot capture/export workflows.
  - no unsupported cloud sync, team collaboration, Windows, Android, iOS, Italy hosting, payment, tax, or compliance claims.
- Prefer natural Italian syntax over word-for-word English structure.
- Keep English only for standard product/technical terms, brand names, and acronyms.
- Keep brand/product names in their official spelling: `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.
- Do not over-polish. Prefer small, high-signal changes unless the whole paragraph is translationese.

## Workflow

1. Identify the copy type: landing-page hero, metadata, CTA, FAQ, blog/changelog body, legal/support copy, or UI microcopy.
2. Audit for Italian AI/translationese patterns:
   - English calques and `Itanglese`
   - nominal bureaucratic phrasing
   - inflated adjective chains
   - unnatural punctuation copied from English
   - repeated `non solo ..., ma anche ...`
   - overuse of `soluzione`, `esperienza`, `ottimizzare`, `semplificare`
   - register mismatch between direct product copy and formal institutional prose
3. Rewrite with the smallest edit that solves the problem.
4. Re-scan against `references/italian-humanization-checklist.md`.
5. If editing repo files, patch directly and then run normal repo verification when code/content paths require it.

## Italian Copy Standard

Prefer:

- concrete verbs
- idiomatic sentence rhythm
- one clear claim per sentence
- direct user benefit grounded in real product behavior
- natural Italian punctuation, capitalization, and date/time formats
- CTA labels that sound like product UI, not translated slogans

Avoid:

- `si configura come`, `rappresenta una soluzione`, `in un mondo sempre piu digitale`
- generic hype such as `rivoluzionario`, `innovativo`, `potente`, `senza soluzione di continuità`, unless directly justified
- filler intensifiers such as `significativamente`, `concretamente`, `rapidamente` stacked together
- English terms where ordinary Italian is clearer
- commas that separate subject and verb

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

- return the polished Italian text
- then give a short note listing the main changes

## Source Attribution

This skill distills reusable guidance from:

- Microsoft Italian Localization Style Guide
- Unbabel Italian language guidelines
- Sailfish OS Italian localization style guide
- Hypnosdesign `claude-skill-scrittura-italiana` / Italian humanizer notes
- the general `humanizer` skill's AI-writing pattern taxonomy
