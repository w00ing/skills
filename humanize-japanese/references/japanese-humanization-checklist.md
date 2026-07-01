# Japanese Humanization Checklist

Use this checklist after reading `SKILL.md`. Preserve meaning first; naturalness is never permission to alter facts.

## Source Anchors

- Microsoft Japanese Localization Style Guide: clear, friendly, concise Japanese for software/product contexts.
- textlint-ja Japanese preset: low-false-positive checks for ordinary Japanese prose.
- textlint-ja technical-writing preset: sentence length, punctuation, duplicate particles, weak phrases, and consistency checks for technical/product prose.
- textlint-ja AI-writing preset: AI-generated Japanese pattern detection.
- JTF Style Guide for Translators Working into Japanese: commercial translation style selection and consistency.
- General `humanizer`: inflated significance, vague attribution, rule of three, passive/subjectless phrasing, and formulaic contrast patterns.

## High-Priority Patterns

1. **English skeleton in Japanese**
   - Watch: overexplicit subjects, `あなたの`, `それは`, noun-first sentence flow copied from English.
   - Fix: omit what Japanese readers infer and move the point earlier.

2. **Weak generic endings**
   - Watch: `〜することができます`, `〜を実現します`, `〜を提供します`, `〜を可能にします`.
   - Fix: use `〜できます`, `〜します`, or a concrete verb.

3. **Long noun chains**
   - Watch: `プロジェクト管理ワークフロー機能`.
   - Fix: split or turn part of it into a clause.

4. **Repeated conjunctions and particles**
   - Watch: repeated `また`, `さらに`, `加えて`, duplicate `が`, duplicate `の`, too many `、`.
   - Fix: split the sentence or remove the signpost.

5. **Inflated marketing words**
   - Watch: `革新的`, `強力`, `包括的`, `シームレス`, `最適化`, `効率化` without evidence.
   - Fix: describe the behavior supported by current source material.

6. **Translationese passives**
   - Watch: `〜されます` when no actor matters, or when an active product action is clearer.
   - Fix: use active Japanese or natural intransitive phrasing.

7. **Register mixing**
   - Watch: `です・ます` mixed with `だ・である`, or stiff technical prose inside CTA/hero copy.
   - Fix: keep customer-facing pages in clear `です・ます` unless the surrounding page says otherwise.

8. **Latin-term handling**
   - Watch: unnecessary translation of product names or inconsistent spacing around `Mac`, `macOS`, `PDF`.
   - Fix: preserve official spelling and match local spacing/punctuation conventions.

## Product And Service Claim Checks

- Base claims about features, platform support, integrations, data handling, pricing, availability, legal status, and compliance on current user or project sources.
- Do not add guarantees or imply capabilities absent from those sources.
- When a claim is uncertain or its source is missing, narrow the wording or flag it for verification.

## Formatting Checks

- Preserve the official spelling and casing of names and technical terms in the supplied source.
- Keep URL paths, query params, analytics params, and code identifiers unchanged.
- Avoid unnecessary exclamation marks in product copy.
- Keep metadata concise; do not force every SEO phrase into one sentence.

## Final Pass

- Read the result aloud.
- Remove one `また`/`さらに` if paragraphs feel like a generated outline.
- Check that every product claim is supported by current source material.
- Confirm no SEO term was stuffed into an unnatural sentence.
