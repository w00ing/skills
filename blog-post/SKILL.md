---
name: blog-post
description: Write, revise, or QA product/service blog posts with correct repo-specific schema, intent metadata, supporting links, safe hero images, and publish-readiness checks. Use when asked to draft, edit, polish, or prepare blog content.
---

# Blog Post

## Overview

Produce a high-quality blog post that is ready for review by default. Use the repository's blog guide, nearby posts, and content schema as the source of truth, then execute the workflow end to end: research, frontmatter, body, image, language polish, and QA.

## When to use

Use this skill when the task is any of:

- create a new blog post
- rewrite, tighten, or polish an existing post
- add or fix frontmatter, schema fields, or internal intent metadata
- replace or optimize a blog hero image
- run a publish-readiness pass on a draft or review post

Do not use this skill for glossary entries, changelogs, release notes, docs pages, or landing pages unless the user explicitly asks to adapt a blog workflow to that content type.

## Required reads

Before writing:

- read `AGENTS.md` or equivalent repo instructions if present
- read the repo's blog/content guide if one exists
- identify the blog content directory and frontmatter/schema conventions
- if editing, read the target post
- skim 1-2 nearby published or review posts in the same intent cluster
- inspect existing product, pricing, feature, and docs pages before making product claims

## Defaults

- new post status: `review` when the repo supports review states
- incomplete work: keep as `draft`
- use targeted research for drift-prone facts
- use stock or open-source hero images unless the repo clearly prefers product screenshots or generated art
- store hero images locally in the repo's normal blog image directory
- never hotlink external image URLs

## Workflow

### 1) Lock the post intent

- identify the core reader problem and search intent
- define the post's job in the repo's metadata format, such as:
  - `contentType`
  - `purpose`
  - `solves`
  - `targetQueries`
  - `supportsPages`
  - `notes`
- make the post support a real product, service, docs, landing, or commercial page, not just exist as standalone content
- keep the planned mix intentional; do not let a whole batch default to the same content type

Useful content types:

- `how-to`: workflow or tutorial intent
- `comparison`: alternatives, tools, or vendor comparison intent
- `decision`: "which should I use?" or trade-off intent
- `concept`: category, explainer, or vocabulary intent
- `announcement`: product or company update intent

### 2) Gather truth before writing

- verify product/service claims from the repo and current public surface
- verify drift-prone external facts from official sources when needed:
  - pricing
  - product capabilities
  - platform or integration support
  - policies, licenses, and commercial-use rights
  - competitor claims
- avoid stale, speculative, or over-broad claims
- if a fact cannot be verified quickly, remove it or mark it as a publishing risk

### 3) Build the frontmatter correctly

- follow the repo's blog guide or existing content schema exactly
- fill all required fields
- make `title` and `description` match the primary search intent
- choose intentional related posts, categories, tags, and internal links
- include glossary or concept links only when the exact term is actually mentioned in the body
- set publish dates, scheduled dates, and statuses only when they match the repo's publishing rules

### 4) Write the post

- lead with the reader problem in the first paragraph
- make the intro, early headings, and FAQ reflect the target queries
- keep body structure concrete:
  - problem-aware intro
  - short answer or framing
  - main comparison, workflow, or explanation sections
  - product/service-fit section
  - practical close or FAQ
- mention the product or service naturally:
  - explain where it fits
  - avoid overpromotion
  - do not turn every section into a pitch
- make supporting pages real:
  - add natural in-body links to the intended product, service, docs, pricing, or landing pages
- keep glossary and related-concept support low-clutter:
  - no glossary rail or glossary dump section by default
  - use concept links only when they help the reader

### 5) Handle the hero image

- follow the repo's existing hero image conventions
- use a stock, open-source, generated, or product screenshot image only when it is commercially safe and suitable for the post
- keep the image directionally relevant; it does not need to be perfectly literal
- download or generate it locally
- optimize before publish:
  - prefer the repo's standard image format
  - strip metadata
  - keep dimensions and file size appropriate for list/detail usage
- use a descriptive local filename
- keep frontmatter image dimensions aligned with the actual file when the schema stores dimensions
- never hotlink external image URLs
- leave the source URL, prompt, and/or license page in thread or PR notes when relevant

### 6) Polish public copy

Public copy should sound like it was written for a customer trying to solve a real problem, not for an internal SEO/content operation.

- keep internal SEO/ops language inside planning docs or internal metadata
- do not leak internal strategy into titles, descriptions, headings, body copy, FAQs, or CTA labels
- avoid phrases like:
  - `cluster`
  - `support post`
  - `money page`
  - `non-brand`
  - `query-page fit`
  - `traffic absorber`
  - `keyword coverage`
- prefer:
  - the reader's task
  - the practical tradeoff
  - visible product behavior
  - the outcome
- remove stiff cadence, generic conclusions, over-marketed language, and AI-sounding filler
- preserve verified facts, structure, search intent, and internal links while polishing

If a writing-polish skill is available, use it for final public-copy cleanup. If not, perform the polish pass manually.

### 7) Run the QA pass

Before finishing, check:

- frontmatter shape is valid
- internal metadata still matches the actual article
- content type matches the real editorial job of the post
- headings and body reflect the main target queries
- related posts, tags, categories, and glossary terms are intentional
- in-body links support the intended pages
- product/service claims match shipped or publicly documented behavior
- competitor and external claims are current or removed
- pricing, legal, policy, and licensing statements are verified or avoided
- hero image path exists locally and is optimized
- image source/license notes are captured when relevant
- status is intentionally `draft`, `review`, `published`, or the repo's equivalent
- public-facing title, description, headings, body, FAQ, and CTA copy have had a final human polish pass

## Prompt

When using this skill, operate with this prompt:

> Write or revise this blog post as a search-intent-matched, publish-ready content asset. Follow the repository's blog guide and content schema exactly. Fill complete frontmatter, including any internal intent metadata the repo uses. Keep related posts, glossary links, categories, tags, and supporting pages intentional. Make the article genuinely useful first, then clearly show where the product or service fits. Verify product truth from the repo and current public surface. Verify external drift-prone claims from official sources when necessary. Use a commercially safe hero image, store it locally in the repo's normal image directory, optimize it before publish, and leave source/license notes in the thread or PR notes. Polish public copy so it sounds natural and customer-facing. Default new posts to review unless the repo or user clearly asks for another status.

## Output contract

For a new post, finish with:

- the markdown/MDX post created
- the local hero image added, replaced, or explicitly skipped with reason
- frontmatter complete according to the repo schema
- a short QA summary
- source URL, prompt, and/or license page noted when relevant

For an existing post, finish with:

- revised markdown/MDX and/or hero image
- a short list of what changed
- any remaining factual or publishing risks
