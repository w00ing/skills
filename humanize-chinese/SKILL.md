---
name: humanize-chinese
description: Polish, rewrite, or review Simplified Chinese public copy so it sounds natural to Mainland Chinese readers while preserving meaning, product truth, SEO intent, and Shotomatic brand trust. Use for zh-CN landing pages, metadata, CTAs, FAQs, blog/changelog prose, translation polish, "AI-sounding Chinese", "翻译腔", "中文润色", "中文文案自然化", or Chinese copy QA before publishing.
---

# Humanize Chinese

Use this skill for Simplified Chinese copy polish, especially customer-facing Shotomatic pages.

This is not an "AI detector bypass" workflow. Treat it as editorial polish: make Chinese text clear, natural, region-appropriate, and trustworthy while keeping facts unchanged.

## Required Reads

Read these before editing:

- `AGENTS.md`
- target file or pasted source text
- `references/rightcapital-style-guide.md` for Chinese typography and Mainland usage
- `references/chinese-humanization-checklist.md` for AI/translationese cleanup patterns

When the copy is public-facing Shotomatic copy, also read:

- `.agents/skills/shotomatic-public-copy-qa/SKILL.md`
- one nearby English source page or product page if needed for product-truth calibration

## Operating Rules

- Preserve facts, prices, product capabilities, dates, URLs, legal claims, and tracking paths.
- Use Simplified Chinese and Mainland Chinese vocabulary.
- Preserve Shotomatic product truth:
  - Mac app.
  - local-first screenshot capture/export workflows.
  - no unsupported cloud sync, team collaboration, Windows, Android, iOS, China hosting, ICP, payment, or compliance claims.
- Keep SEO terms natural. Use exact Chinese intent terms only where they fit human prose.
- Do not mention internal SEO strategy, funnel tests, traffic sources, piracy/crack pages, analytics, or operator language in public copy.
- Do not over-polish. Prefer small, high-signal changes unless the whole paragraph is translationese.
- Keep brand/product names in their official spelling: `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.

## Workflow

1. Identify the copy type:
   - landing-page hero
   - metadata
   - CTA
   - FAQ
   - blog/changelog body
   - legal/support copy
2. Audit for:
   - translationese
   - stiff AI phrasing
   - Mainland terminology mismatches
   - punctuation/spacing issues
   - SEO stuffing
   - product-truth risk
3. Rewrite with the smallest edit that solves the problem.
4. Re-scan against the two reference files.
5. If editing repo files, patch directly and then run the normal repo verification when code/content paths require it.

## Chinese Copy Standard

Prefer:

- direct verbs
- short sentences mixed with occasional longer explanatory sentences
- user-facing benefits grounded in real behavior
- concrete workflow language
- common Mainland terms
- Chinese punctuation and spacing rules from the RightCapital guide

Avoid:

- generic phrases such as `提升效率`, `赋能`, `打造`, `一站式`, `轻松实现`, `无缝`, `极致`, `强大而灵活` unless the surrounding sentence proves them
- rigid contrasts copied from English, such as `不只是……更是……`
- repetitive three-part structures
- inflated claims like `最佳`, `革命性`, `必备神器`, `专业级` unless independently justified
- keyword bundles in titles or headings

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

- return the polished Chinese text
- then give a short note listing the main changes

## Source Attribution

This skill uses a local reference derived from RightCapitalHQ's MIT-licensed Chinese writing style guide:

- <https://github.com/RightCapitalHQ/chinese-style-guide>
