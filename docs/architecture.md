# Architecture — Dhammapada

## Overview

Dhammapada is a **static multi-page mini site** hosted on GitHub Pages. It is a spoke in the hub-and-spoke model under The Dharma Gate portal, following the same architecture as all other DharmaGate scripture sites.

- The **hub** is [The Dharma Gate](https://lugh3456.github.io/DharmaGate/)
- This **spoke** is a standalone repository with its own index and 26 section pages
- The hub links to this site; this site links back via portal bar and footer

HTML + external CSS only. No frameworks, no build tools.

---

## Folder Structure

```
Dhammapada/
  index.html         <- intro page with 26 chapter cards
  section1.html      <- Ch.1 双品 (20 verses)
  ...
  section26.html     <- Ch.26 婆罗门品 (41 verses)
  css/
    style.css        <- all styles (design tokens, components, responsive)
  docs/
    readme.md
    architecture.md  <- this file
    ai-context.md
    plan.md
    roadmap.md
  Backup/            <- dated backups
```

---

## Page Structure — Index

```
<portal-bar>           <- link back to DharmaGate
<header.site-header>   <- "Dhammapada" title, Chinese subtitle, tradition label
<section.intro>        <- brief description of the text
<main.chapter-grid>    <- 26 chapter cards (link to section pages)
  a.chapter-card       <- chapter number + Chinese title
<footer>
```

---

## Page Structure — Section Pages

```
<portal-bar>                <- link back to DharmaGate
<header.section-header>     <- chapter name (Chinese + English), nav links
<main.section-container>
  section.full-text         <- full classical Chinese text + 🔊 聆听经文 button
  section.line-explanation
    h2                      <- "逐句解释"
    .explanation-card       <- one per verse:
      p.line                <- classical Chinese verse (bold)
      p.explanation-zh      <- Chinese explanation (always visible)
      button.toggle-btn     <- "English ▾"
      .detail-content       <- hidden by default:
        p.translation       <- Buddharakkhita English translation (red)
        p.explanation       <- English commentary (grey)
  section.summary
    h2                      <- "总结 · Summary"
    p.summary-zh            <- Chinese summary
    button.toggle-btn       <- "English ▾"
    .detail-content         <- hidden by default:
      p.explanation         <- English summary
<script>                    <- toggleDetail() + speak()
<footer>
```

---

## CSS Architecture

All styles in `css/style.css` — copied verbatim from LotusSutra. Labelled sections:

```
DESIGN TOKENS
SKIP LINK
RESET & BASE
PORTAL BAR
HEADER — INDEX
HEADER — SECTION PAGE
INTRO — INDEX
SECTION CARD GRID
SECTION PAGE CONTAINER
FULL TEXT BLOCK
LINE-BY-LINE EXPLANATION
EXPAND / COLLAPSE TOGGLE
SUMMARY
FOOTER
RESPONSIVE
```

---

## Chapter Grid (index.html)

Uses `.chapter-grid` / `.chapter-card` layout (same as LotusSutra). Each card shows:
- `.chapter-num` — chapter number in Chinese ordinal (第一章, 第二章, etc.)
- `.chapter-zh` — Chinese chapter name (e.g. 双品)
- `.chapter-en` — English chapter name (e.g. Pairs) — added via inline style on index

---

## Expand/Collapse Pattern

Same as all DharmaGate spokes:
- `<button class="toggle-btn">` triggers `toggleDetail(btn)`
- Sibling `<div class="detail-content" hidden>` holds English content
- `aria-expanded` updated for accessibility
- ▾/▴ swapped on toggle

---

## Speech Synthesis

🔊 聆听经文 button reads all classical Chinese verses for the chapter. Targets Ting-Ting voice (zh-CN, rate 0.9).

---

## External Dependencies

Google Fonts:
- Noto Serif SC — headings, Chinese primary text
- Noto Sans SC — body text, buttons

No other external dependencies.

---

## Responsive Breakpoints

| Breakpoint | Change |
|-----------|--------|
| > 600px | Default layout |
| <= 600px | 2-column chapter grid, reduced padding |

---

## Hosting

GitHub Pages via `lugh3456` account.
Repository name: `Dhammapada`
Live URL (when deployed): `https://lugh3456.github.io/Dhammapada/`
