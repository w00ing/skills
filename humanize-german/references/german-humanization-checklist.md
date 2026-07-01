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
   - Watch: long preposed modifiers, `mit Shotomatic kannst du/Sie ...`, mirrored `from X to Y` ranges.
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
   - Fix: match the surrounding page. For Shotomatic landing copy, prefer neutral/impersonal phrasing unless the page clearly commits to one form of address.

## Product Truth Checks

- Shotomatic is a Mac app.
- Captures and exports are local-first.
- Do not imply team collaboration, cloud sync, remote monitoring, Windows support, mobile support, hosted storage, or enterprise compliance.
- Do not promise perfect automation, guaranteed website access, legal permission to capture third-party content, or universal cookie/paywall handling.

## Formatting Checks

- Use German quotation marks only if the surrounding file already uses them.
- Preserve `Shotomatic`, `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`.
- Keep URL paths, query params, analytics params, and code identifiers unchanged.
- Avoid English title case in German headings unless it is a product name.

## Final Pass

- Read the result aloud.
- Remove one more abstract noun if a direct verb would say the same thing.
- Check that every marketing claim points to an actual Shotomatic feature.
- Confirm no SEO term was stuffed into an unnatural sentence.
