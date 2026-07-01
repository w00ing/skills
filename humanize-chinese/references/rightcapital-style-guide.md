# RightCapital Chinese Style Guide Reference

Source: <https://github.com/RightCapitalHQ/chinese-style-guide>

License: MIT. Copyright (c) 2021 RightCapital Inc.

This is a condensed local reference for the `humanize-chinese` skill. Use the upstream repository for the canonical guide.

## Core Rules

- Use Simplified Chinese.
- Use Mainland Chinese vocabulary and accepted translations.
- Do not use Hong Kong/Taiwan terms when writing for Mainland readers.
- Do not use internet slang, discriminatory language, or vulgar language.
- Use clear and concise language.
- Fix obvious typos and common wrong characters.

## Translation And Terminology

- Use Mainland translations.
- If a technical English word has no widely accepted Chinese translation, or the translation would be ambiguous, keep the English word.
- Use common English abbreviations when they are widely accepted.
- When adding an English original as a gloss, add it only on first mention.
- Brand names should keep official spelling.

Examples:

- Prefer `算法`, `参数`, `数组`, `回调`.
- Avoid `演算法`, `引数`, `阵列`, `回呼`.
- Prefer `登录`, `阈值`, `重启`.
- Avoid `登陆`, `阀值`, `重起`.

## Chinese-English Mixed Text

- Add a space between Chinese characters and English words.
- Add a space between Chinese characters and Arabic numerals.
- Do not add spaces between Chinese punctuation and English/numerals.
- Do not add spaces between Chinese characters and half-width punctuation.
- Do not add spaces around inline formatted Chinese text, links, bold, or emphasis.
- In Chinese sentences, use singular English nouns for standalone English technical nouns unless the official term is plural.

Examples:

- `Shotomatic 可以在 Mac 上自动截图。`
- `一次导出 20 张截图。`
- `订阅价格是 100 美元/月。`
- `这是**重要**功能。`

## Chinese Punctuation

- Chinese sentences use Chinese punctuation.
- Use `。` for periods.
- Use `，` for commas.
- Use `、` for parallel noun lists.
- Use `！`, `？`, `：`, `；`.
- Use curly Chinese quotes: `“”`.
- Use book-title brackets: `《》`.
- Use full-width parentheses `（）` unless both inside and outside are English.
- Use `——` for Chinese em dash.
- Use `……` for Chinese ellipsis.
- Use `/` for slash-separated alternatives.
- Use `-` for hyphenated technical text and `—` or `～` for Chinese ranges.

Rules:

- Use `、` between parallel nouns.
- Do not imitate the English Oxford comma before `和` or `或`.
- Use Chinese punctuation in Chinese sentences, but preserve English punctuation inside an English phrase or sentence.
- Use full-width parentheses when the surrounding sentence is Chinese or the parenthetical content is Chinese.
- Use half-width parentheses only when both surrounding and parenthetical content are English.

## Numbers

- Follow the spirit of GB/T 15835.
- Use Chinese numerals for numbers under 10 when natural.
- Use Arabic numerals for 10 and above.
- Use half-width Arabic numerals.
- Use `万` and `亿` with Arabic numerals when appropriate, such as `300 万`.
- Use Chinese numerals with other Chinese units, such as `三百`.
- Use thousands separators for Chinese-sentence Arabic numerals with four or more digits: `3,000,000`.
- Use half-width `%`: `15%`.

## Dates And Time

- Use year-month-day order.
- Valid examples: `2026 年 6 月 29 日`, `2026-6-29`, `2026-06-29`.
- Use four-digit years.
- Do not pad month/day when using `月` and `日`: write `3 月 31 日`, not `03 月 31 日`.
- Use half-width colon in time: `9:05`.

## Lists

- In Chinese lists, if each item is not a full sentence, use semicolons for intermediate items and a period for the final item.
- If each item is a full sentence, end each with a period.
- Keep list style consistent within one list.

## English Inside Chinese Content

- Use American spelling for English text unless quoting or using a brand spelling.
- Preserve official capitalization for brands and products.
- Avoid all-caps except official names.
- In English sentences, use English punctuation.
- In English text, use Oxford comma for lists with three or more items.

## Shotomatic-Specific Terms

- `Shotomatic` remains English.
- `Mac`, `macOS`, `PDF`, `ZIP`, `MP4`, `JPG`, `PNG`, `WebP`, `OCR`, `API` remain English.
- Good Mainland-friendly terms:
  - automated screenshot: `自动截图`
  - screenshot automation tool: `自动化截图工具`
  - timed screenshot: `定时截图`
  - batch website screenshots: `批量网页截图`
  - screenshot to PDF: `截图转 PDF`
  - local processing: `本地处理`
  - privacy: `隐私`
