# AI Context — Dhammapada

## What this project is

A static mini site for studying the Dhammapada (法句经), one of nine scripture sites under The Dharma Gate portal. Same architecture as other DharmaGate spokes — HTML + external CSS, no frameworks.

## Current state (as of 2026-05-24)

- **T0210 rebuild complete** — all 39 section pages generated and audited (0 issues)
- index.html complete (39-card chapter grid, T0210 titles)
- All 39 section pages complete (section1.html – section39.html)
- docs/reference.py rebuilt from T0210 full texts (39 chapters)
- Both audit scripts pass: 0 content issues, 0 structure issues
- Phase 4 (GitHub deploy) is next — repo not yet created

## Card pattern (verse-by-verse)

```html
<div class="explanation-card">
  <p class="line"><strong>Classical Chinese verse (法句经)</strong></p>
  <p class="explanation-zh">Chinese explanation (always visible)</p>
  <button class="toggle-btn" onclick="toggleDetail(this)" aria-expanded="false">English ▾</button>
  <div class="detail-content" hidden>
    <p class="translation">English translation — Buddharakkhita (red)</p>
    <p class="explanation">English commentary (grey)</p>
  </div>
</div>
```

## Summary pattern

```html
<section class="summary">
  <h2>总结 · Summary</h2>
  <p class="summary-zh">Chinese summary</p>
  <button class="toggle-btn" onclick="toggleDetail(this)" aria-expanded="false">English ▾</button>
  <div class="detail-content" hidden>
    <p class="explanation">English summary</p>
  </div>
</section>
```

## Content sources

- **Chinese primary text**: T0210 大正藏 No. 0210 — authoritative classical text, 224 CE, 4-character verse format
- **English translation**: Written for this site, informed by Buddharakkhita (BPS edition) and the T0210 structure
- **Chinese explanations**: Written for this site — accessible modern Chinese
- **English commentary**: Written for this site — contextual, practical

## File structure

```
Dhammapada/
  index.html         <- intro + 39 T0210 chapter cards
  section1.html      <- Ch.1  无常品 Impermanence
  section2.html      <- Ch.2  教学品 Learning
  section3.html      <- Ch.3  多闻品 Extensive Hearing
  section4.html      <- Ch.4  笃信品 Faith
  section5.html      <- Ch.5  戒慎品 Precepts
  section6.html      <- Ch.6  惟念品 Mindfulness
  section7.html      <- Ch.7  慈仁品 Loving-kindness
  section8.html      <- Ch.8  言语品 Speech
  section9.html      <- Ch.9  双要品 The Pairs
  section10.html     <- Ch.10 放逸品 Heedlessness
  section11.html     <- Ch.11 心意品 The Mind
  section12.html     <- Ch.12 华香品 Flowers and Fragrance
  section13.html     <- Ch.13 愚闇品 Fools
  section14.html     <- Ch.14 明哲品 The Wise
  section15.html     <- Ch.15 罗汉品 The Arahant
  section16.html     <- Ch.16 述千品 Thousands
  section17.html     <- Ch.17 恶行品 Evil Deeds
  section18.html     <- Ch.18 刀杖品 Rods and Weapons
  section19.html     <- Ch.19 老耗品 Old Age
  section20.html     <- Ch.20 爱身品 The Self
  section21.html     <- Ch.21 世俗品 The World
  section22.html     <- Ch.22 述佛品 The Buddha
  section23.html     <- Ch.23 安宁品 Peace
  section24.html     <- Ch.24 好喜品 Pleasure
  section25.html     <- Ch.25 忿怒品 Anger
  section26.html     <- Ch.26 尘垢品 Impurity
  section27.html     <- Ch.27 奉持品 Observance
  section28.html     <- Ch.28 道行品 The Path
  section29.html     <- Ch.29 广衍品 Broad Cultivation
  section30.html     <- Ch.30 地狱品 Hell
  section31.html     <- Ch.31 象喻品 The Elephant
  section32.html     <- Ch.32 爱欲品 Craving
  section33.html     <- Ch.33 利养品 Gain and Support
  section34.html     <- Ch.34 沙门品 The Monk
  section35.html     <- Ch.35 梵志品 The Brahmin
  section36.html     <- Ch.36 泥洹品 Nirvana
  section37.html     <- Ch.37 生死品 Birth and Death
  section38.html     <- Ch.38 道利品 The Way and Benefit
  section39.html     <- Ch.39 吉祥品 Blessings
  css/
    style.css        <- copied verbatim from LotusSutra
  docs/
    readme.md
    architecture.md
    ai-context.md    <- this file
    plan.md
    roadmap.md
    reference.py     <- T0210 authoritative text, 39 chapters (audit reference)
  Backup/
    2026-05-24-pre-T0210/  <- original 26-chapter Pali-structure pages
```

## Design tokens

Same as all DharmaGate spokes — no changes to style.css.

| Token | Value | Usage |
|-------|-------|-------|
| `--red` | `#b83232` | Primary accent, translations |
| `--red-light` | `#d44e4e` | Hover states, headings |
| `--saffron` | `#c8820a` | Chapter number labels |
| `--saffron-lt` | `#e09c2a` | Portal bar links |
| `--ink` | `#1c0f0f` | Header/footer backgrounds |
| `--bg` | `#f7f0e6` | Page background |
| `--text` | `#2d1f1f` | Body text, Chinese explanations |
| `--muted` | `#7a6060` | English text, toggle buttons |
| `--border` | `#e0d0c8` | Card borders, dividers |

## Section page nav pattern

- First chapter: `目录 Contents` only (no prev)
- Middle chapters: `← 第N章` · `目录 Contents` · `第N章 →`
- Last chapter: `← 第N章` · `目录 Contents` only (no next)

## Speech button

🔊 聆听经文 — targets Ting-Ting voice on iOS Safari (zh-CN, rate 0.9)

## Portal link

Portal bar and footer both link to: `https://lugh3456.github.io/DharmaGate/`

## GitHub repo (not yet created)

Will be at: `https://lugh3456.github.io/Dhammapada/`
Repository name: `Dhammapada`
