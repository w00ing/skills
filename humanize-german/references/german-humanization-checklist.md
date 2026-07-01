# German Humanization Checklist

Use this checklist after reading `SKILL.md`. Preserve meaning first; naturalness is never permission to alter facts.

## Source Anchors

- Microsoft German Localization Style Guide: market conventions, anti-literal translation guidance, German software tone.
- Zulip German translation guidelines: short instructions, imperatives, and infinitive UI labels.
- Marmbiz `humanizer-de` / Martin Moeller German Humanizer: German-specific AI signals such as participle-I constructions, dash overuse, repeated signposting, Anglicism structures, and rhythm uniformity.
- General `humanizer`: inflated significance, vague attribution, rule of three, passive/subjectless phrasing, and formulaic contrast patterns.

## High-Priority Patterns

1. **Nominalstil**
   - Watch: `die Optimierung der Erstellung`, `die Durchführung der Erfassung`, `die Nutzung von Workflows`.
   - Fix: convert to a verb-driven clause.

2. **English sentence skeleton**
   - Watch: long preposed modifiers, inconsistent `du`/`Sie` address, mirrored `from X to Y` ranges.
   - Fix: use German word order and split overloaded sentences.

3. **Anglicism without need**
   - Watch: `seamless`, `Workflow optimieren`, `Content capturen`, `Asset Management` when ordinary German works.
   - Fix: keep standard tech terms, replace decorative English.

4. **AI signposting**
   - Watch: `Darueber hinaus`, `Zudem`, `Ausserdem`, `Insgesamt`, `Es ist wichtig zu beachten`, repeated at paragraph starts.
   - Fix: remove or replace with a concrete transition.

5. **German participle-I and pseudo-academic phrasing**
   - Watch: `gewährleistend`, `ermöglichend`, `hervorhebend`, `darstellend`.
   - Fix: use finite verbs.

6. **Inflated product language**
   - Watch: `revolutionär`, `bahnbrechend`, `leistungsstark`, `nahtlos`, `umfassend`, `optimale Lösung`.
   - Fix: replace with concrete product behavior.

7. **Dash and colon choreography**
   - Watch: headline-like colon formulas and repeated parenthetical dashes copied from English.
   - Fix: use periods, commas, or a second sentence when German reads more naturally.

8. **Formal address drift**
   - Watch: switching between `du`, `Sie`, and impersonal copy.
   - Fix: match the register and form of address already established on the page.

## Product And Service Claim Checks

- Base claims about features, platform support, integrations, data handling, pricing, availability, legal status, and compliance on current user or project sources.
- Do not add guarantees or imply capabilities absent from those sources.
- When a claim is uncertain or its source is missing, narrow the wording or flag it for verification.

## Formatting Checks

- Use German quotation marks only if the surrounding file already uses them.
- Preserve the official spelling and casing of names and technical terms in the supplied source.
- Keep URL paths, query params, analytics params, and code identifiers unchanged.
- Avoid English title case in German headings unless it is a product name.

## Final Pass

- Read the result aloud.
- Remove one more abstract noun if a direct verb would say the same thing.
- Check that every product claim is supported by current source material.
- Confirm no SEO term was stuffed into an unnatural sentence.
