---
name: humanize-italian
description: Polish, rewrite, or review Italian public copy so it sounds natural to Italian readers while preserving meaning, verified product claims, search intent, and the established product voice. Use for it landing pages, metadata, CTAs, FAQs, blog/changelog prose, translation polish, "AI-sounding Italian", "italiano da IA", "italiano tradotto", "Itanglese", "umanizza italiano", or Italian copy QA before publishing.
---

# Humanize Italian

Use this skill for Italian copy polish, especially public-facing product copy.

This is not an AI-detector bypass workflow. Treat it as editorial polish: make Italian text clear, idiomatic, and trustworthy while keeping facts unchanged.

## Required Reads

Read these before editing:

- `AGENTS.md`
- target file or pasted source text
- `references/italian-humanization-checklist.md`

For product-specific claims, consult current project documentation or an authoritative product source when available.

## Operating Rules

- Preserve facts, prices, product capabilities, dates, URLs, legal claims, and tracking paths.
- Use contemporary Italian for Italy unless the user specifies another market.
- Verify product claims against user-provided or project sources, such as current product documentation or public pages.
- Do not invent features, platform support, integrations, privacy or security guarantees, pricing, availability, or compliance claims. Narrow or flag claims that cannot be verified.
- Prefer natural Italian syntax over word-for-word English structure.
- Keep English only for standard product/technical terms, brand names, and acronyms.
- Keep product and brand names in their official spelling.
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
