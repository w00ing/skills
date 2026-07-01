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
   - Watch: `画面キャプチャ自動化ワークフロー管理機能`.
   - Fix: split or turn part of it into a clause.

4. **Repeated conjunctions and particles**
   - Watch: repeated `また`, `さらに`, `加えて`, duplicate `が`, duplicate `の`, too many `、`.
   - Fix: split the sentence or remove the signpost.

5. **Inflated marketing words**
   - Watch: `革新的`, `強力`, `包括的`, `シームレス`, `最適化`, `効率化` without evidence.
   - Fix: describe the actual screenshot/export behavior.

6. **Translationese passives**
   - Watch: `〜されます` when no actor matters, or when an active product action is clearer.
   - Fix: use active Japanese or natural intransitive phrasing.

7. **Register mixing**
   - Watch: `です・ます` mixed with `だ・である`, or stiff technical prose inside CTA/hero copy.
   - Fix: keep customer-facing pages in clear `です・ます` unless the surrounding page says otherwise.

8. **Latin-term handling**
   - Watch: unnecessary translation of product names or inconsistent spacing around `Mac`, `macOS`, `PDF`.
   - Fix: preserve official spelling and match local spacing/punctuation conventions.

## Product Truth Checks

- Shotomatic is a Mac app.
- Captures and exports are local-first.
- Do not imply team collaboration, cloud sync, remote monitoring, Windows support, mobile support, hosted storage, or enterprise compliance.
- Do not promise perfect automation, guaranteed website access, legal permission to capture third-party content, or universal cookie/paywall handling.

## Formatting Checks

- Preserve `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.
- Keep URL paths, query params, analytics params, and code identifiers unchanged.
- Avoid unnecessary exclamation marks in product copy.
- Keep metadata concise; do not force every SEO phrase into one sentence.

## Final Pass

- Read the result aloud.
- Remove one `また`/`さらに` if paragraphs feel like a generated outline.
- Check that every marketing claim points to an actual Shotomatic feature.
- Confirm no SEO term was stuffed into an unnatural sentence.
