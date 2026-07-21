# Kashida Plus

**A rule-based elongation engine for Arabic & Kurdish Sorani typography.**

Free, browser-based tool for designers who need proper *kashida* (ـــ / tatweel) stretching — logo work, headlines, or line-fitting — without hand-placing every stretch mark in Illustrator. No signup, no backend, free forever.

## What it does

Kashida for All takes Arabic or Kurdish Sorani text and inserts tatweel (ـ) at the joints where elongation is typographically valid — never inside non-connecting letters, never breaking ligatures like lam-alef, and (optionally) never on a word's final joint. Three modes decide *where* those stretches go:

| Mode | Behavior |
|---|---|
| **Logo** | One dramatic stretch per word, placed at the single highest-scoring joint. Classic calligraphic/logotype look. |
| **Balance** | Distributes elongation across a percentage of a word's joints, controlled by the Coverage slider. |
| **Fit** | Pads each line with kashidas until it reaches a target character width — for justified-looking blocks of text. |

Every joint is scored before the engine decides which ones to stretch, and every decision can be overridden — click any joint in the preview to add or remove a kashida by hand.

## How the engine works

1. **Script detection** — walks the text character by character using Unicode ranges to identify Arabic letters, including Kurdish Sorani additions (ڕ, ژ, ۆ, ە).
2. **Join validation** — checks each letter pair against a non-connector set (ا, د, ذ, ر, ز, و, ة, ء and Kurdish equivalents) and blocks known ligatures (lam-alef), so kashidas never land somewhere that would break the script.
3. **Joint scoring** — ranks valid joints using rules like preference for classical seat letters (س ش ص ف ق ك…), position within the word, and the neighboring character.
4. **Placement** — depending on mode, takes the single top joint (Logo), the top N% by coverage (Balance), or fills joints round-robin until a line hits its target width (Fit).
5. **Rendering** — repaints the preview character-by-character so every joint is independently clickable for manual correction, with kashidas visually distinguished from the source text.

Everything runs client-side. No text ever leaves the browser.

## Features

- **3 stretch modes** — Logo, Balance, Fit
- **Manual override** — click any joint in the live preview to add/remove a kashida by hand; manual edits are tracked separately from auto-generated ones
- **4 presets** — Subtle, Balanced, Dramatic, Logotype
- **Configurable rules** — toggle seat-letter preference, short-word skipping, final-joint protection, and kashida highlighting independently
- **40-font Arabic library** — Naskh/Text, Kufi/Geometric, Modern Sans, Display/Headline, and Calligraphic/Nastaliq families via Google Fonts, plus a 16-font quick-swap gallery
- **Before/after compare** — toggle the untouched source text under the output
- **Live stats** — kashida count, character count, manual edit count
- **One-click copy** — copies the finished string to clipboard for pasting into Illustrator, Figma, or After Effects
- **Multi-line support** — each line is processed independently

## Tech stack

- Vanilla HTML/CSS/JS — no framework, no build step, no dependencies
- Google Fonts (Arabic font library, loaded via CDN)
- Deployed on Vercel

## Running locally

No install required — it's a single self-contained file:

```bash
git clone <repo-url>
cd kashida-for-all
open index.html
```

Or serve it with any static file server.

## Language support

Built for Arabic and Kurdish Sorani script specifically — the non-connector and seat-letter sets include Kurdish-specific characters (ڕ, ژ, ۆ, ە, گ, چ, پ, ک) alongside standard Arabic.

## Author

Written by [Alan Baban](mailto:alanbaban@33studio.org) — [33 Studio](https://33studio.org)

## License

*(add your preferred license here — MIT recommended for an open tool like this)*
