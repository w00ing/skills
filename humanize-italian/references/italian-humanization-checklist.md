# Italian Humanization Checklist

Use this checklist after reading `SKILL.md`. Preserve meaning first; naturalness is never permission to alter facts.

## Source Anchors

- Microsoft Italian Localization Style Guide: avoid word-for-word translation, keep terminology consistent, prefer fluent Italian.
- Unbabel Italian language guidelines: locale formats for dates, time, measures, and proper nouns.
- Sailfish OS Italian style guide: contemporary mobile/software localization style.
- Hypnosdesign `claude-skill-scrittura-italiana`: Italian AI-writing signals around punctuation, rhetoric, bureaucratic nominal style, and English calques.
- General `humanizer`: inflated significance, vague attribution, rule of three, passive/subjectless phrasing, and formulaic contrast patterns.

## High-Priority Patterns

1. **Itanglese and English calques**
   - Watch: `workflow`, `performance`, `asset`, `content`, `seamless`, `privacy-first` when Italian has the clearer phrase.
   - Fix: keep standard terms only when Italian product readers expect them.

2. **Bureaucratic nominal style**
   - Watch: `la gestione dell'acquisizione`, `l'ottimizzazione dei processi`, `la possibilità di esportazione`.
   - Fix: use verbs and shorter clauses.

3. **Fake product grandeur**
   - Watch: `soluzione innovativa`, `strumento rivoluzionario`, `esperienza senza precedenti`, `potente e flessibile`.
   - Fix: state the concrete behavior.

4. **Formulaic contrast**
   - Watch: `non solo ..., ma anche ...`, `non e solo ..., e ...` repeated across sections.
   - Fix: choose the stronger claim and write it plainly.

5. **English punctuation copied into Italian**
   - Watch: comma between subject and verb, repeated em dashes, colon-heavy headlines, title-case headings.
   - Fix: use Italian punctuation and sentence rhythm.

6. **Stacked adverbs/adjectives**
   - Watch: `concretamente, rapidamente e significativamente`, `semplice, potente e intuitivo`.
   - Fix: remove filler or anchor one modifier to evidence.

7. **Awkward impersonal constructions**
   - Watch: `si configura come`, `viene reso possibile`, `e stato progettato per consentire`.
   - Fix: use active or naturally impersonal Italian.

8. **Register mismatch**
   - Watch: institutional prose inside a friendly product page, or casual slogans inside legal/support copy.
   - Fix: match the page and the user's intent.

## Product Truth Checks

- Shotomatic is a Mac app.
- Captures and exports are local-first.
- Do not imply team collaboration, cloud sync, remote monitoring, Windows support, mobile support, hosted storage, or enterprise compliance.
- Do not promise perfect automation, guaranteed website access, legal permission to capture third-party content, or universal cookie/paywall handling.

## Formatting Checks

- Preserve `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.
- Keep URL paths, query params, analytics params, and code identifiers unchanged.
- Use Italian sentence case in headings unless the product style says otherwise.
- Use Italian date/time formats when writing prose examples.

## Final Pass

- Read the result aloud.
- Remove one `soluzione`, `esperienza`, or `ottimizzare` if it does not add meaning.
- Check that every marketing claim points to an actual Shotomatic feature.
- Confirm no SEO term was stuffed into an unnatural sentence.
