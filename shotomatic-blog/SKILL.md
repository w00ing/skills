---
name: shotomatic-blog
description: Write or update Shotomatic landing-page blog posts in `shotomatic-landing-page/src/content/blog/` with correct frontmatter, internal intent metadata, supporting links, stock hero images, and publish-readiness QA. Use when asked to draft, revise, or QA Shotomatic blog posts.
---

# Shotomatic Blog

Produce a high-quality Shotomatic blog post that is ready for `review` by default. Use the repo guide as the schema and style source of truth, then execute the workflow end to end: research, frontmatter, body, image, and QA.

## When To Use

Use this skill when the task is any of:

- create a new Shotomatic blog post
- rewrite or tighten an existing blog post
- add or fix `internal` intent metadata
- replace or optimize a blog hero image
- run a publish-readiness pass on a blog draft or review post

Do not use this skill for glossary or changelog content.

## Required Reads

Before writing:

- read the repo `AGENTS.md`
- read `shotomatic-landing-page/docs/content/blog-guide.md`
- if editing, read the target post in `shotomatic-landing-page/src/content/blog/`
- skim 1-2 nearby blog posts in the same intent cluster

## Defaults

- new post status: `review`
- incomplete work: keep as `draft`
- use targeted research for drift-prone facts
- use stock or open-source hero images, not custom-generated blog art
- store hero images locally under `shotomatic-landing-page/public/images/blog/`

## Workflow

### 1) Lock The Post Intent

- identify the core reader problem and search intent
- define the post's job in `internal`:
  - `contentType`
  - `purpose`
  - `solves`
  - `targetQueries`
  - `supportsPages`
  - `notes`
- make the post support a real landing or commercial page, not just exist as standalone content
- do not let a whole batch default to `how-to`; keep the planned mix intentional

### 2) Gather Truth Before Writing

- verify Shotomatic claims from the repo and current product surface
- verify drift-prone external facts from official sources only when needed:
  - competitor pricing
  - competitor OCR or export support
  - licensing and source pages for stock images
- avoid stale or speculative claims

### 3) Build The Frontmatter Correctly

- follow `shotomatic-landing-page/docs/content/blog-guide.md` exactly
- fill all required fields
- make `title` and `description` match the primary search intent
- set `internal.contentType` intentionally:
  - `how-to`
  - `comparison`
  - `decision`
  - `concept`
- choose intentional `relatedPosts`
- choose `relatedGlossaryTerms` only for glossary terms that are actually mentioned in the article body
- prefer `relatedGlossaryTerms` over hardcoded markdown glossary links
- set `publishAt` only when the post is truly ready for scheduled publishing

### 4) Write The Post

- lead with the user problem in the first paragraph
- make the intro, early headings, and FAQ reflect `targetQueries`
- keep body structure concrete:
  - problem-aware intro
  - short answer or framing
  - main comparison or workflow sections
  - product-fit section
  - practical close or FAQ
- use Shotomatic naturally:
  - explain where it fits
  - avoid overpromotion
- make `supportsPages` real:
  - add natural in-body links to the intended landing or commercial pages
- keep glossary connections low-clutter:
  - no glossary rail or glossary section by default
  - use glossary support only when the exact glossary term is truly mentioned

### 5) Handle The Hero Image

- use a stock or open-source image that is commercially usable
- keep it directionally relevant; it does not need to be perfectly literal
- download it locally
- optimize before publish:
  - prefer `webp`
  - default target `1600x1067`
  - strip metadata
  - usually keep it around `60KB - 150KB`
- use a descriptive local filename
- keep frontmatter `width` and `height` aligned with the actual file
- never hotlink external image URLs
- leave the source URL and license page in thread or PR notes

### 6) Run The QA Pass

Before finishing, check:

- frontmatter shape is valid
- `internal` block still matches the actual article
- `internal.contentType` matches the real editorial job of the post
- headings and body reflect the main `targetQueries`
- `relatedPosts` are intentional
- `relatedGlossaryTerms` matches exact glossary term mentions in the body
- in-body links support `supportsPages`
- product claims match shipped behavior
- competitor claims are current or removed
- hero image path exists locally and is optimized
- post status is intentionally `draft`, `review`, or `published`

## Prompt

When using this skill, operate with this prompt:

> Write or revise this Shotomatic blog post as a search-intent-matched, publish-ready content asset. Follow `shotomatic-landing-page/docs/content/blog-guide.md` exactly. Fill complete frontmatter, including `internal` intent metadata with an intentional `contentType` and curated `relatedGlossaryTerms`. Only connect the post to glossary terms when the exact glossary term is actually mentioned in the article body. Keep glossary support inline and low-clutter. Make the article genuinely useful first, then clearly show where Shotomatic fits. Verify product-truth from the repo. Verify external drift-prone claims from official sources only when necessary. Use a commercially safe stock or open-source hero image, store it locally under `public/images/blog/`, optimize it before publish, and leave source and license notes in the thread or PR notes. Default new posts to `review` unless the user clearly asks for another status.

## Output Contract

For a new post, finish with:

- the markdown post created or updated
- the local hero image added or replaced
- frontmatter complete, including `internal`
- a short QA summary
- source URL and license page noted in the thread or PR notes

For an existing post, finish with:

- revised markdown and/or hero image
- a short list of what changed
- any remaining factual or publishing risks
