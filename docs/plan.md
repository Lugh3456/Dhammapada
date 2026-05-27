# Plan — Dhammapada

## Vision

A clean, bilingual study site for the Dhammapada (法句经) — one of the most beloved texts in Theravada Buddhism. Each of the 26 chapters is presented verse by verse, with the classical Chinese 法句经 text as the primary layer, accessible Chinese commentary always visible, and the Buddharakkhita English translation + commentary available on toggle.

The site is the seventh spoke in The Dharma Gate portal, following the same architecture and design system as the six Mahayana scripture sites already built.

## Objectives

1. Make the Dhammapada accessible for personal study — not as raw scripture but as an annotated reading experience
2. Maintain the bilingual Chinese-first format consistent with all other DharmaGate sites
3. Include every verse — no cutting or condensing of the primary text
4. Present Buddharakkhita's translation faithfully alongside contextual English commentary

## Content Approach

- **Primary text**: Classical Chinese 法句经 (5-character verse format)
- **Chinese explanation**: Modern, accessible Chinese — concept-focused, 2–4 sentences per verse
- **English translation**: Buddharakkhita (BPS edition) — reproduced accurately
- **English commentary**: Contextual explanation — practical, grounded, with relevant analogies where helpful
- **Chapter summary**: Chinese (always visible) + English (toggle) — covers the chapter theme and key takeaways

## Scope

- 26 chapters, 423 verses total
- Average ~16 verses per chapter; longest is Ch.26 (41 verses) which may be split into sub-pages if needed
- One HTML file per chapter (section1.html through section26.html)
- No sub-pages unless a chapter is too long for comfortable reading

## Format

Identical to all other DharmaGate spokes:
- Static HTML + external CSS (no frameworks)
- Same design tokens (red/saffron/cream palette)
- Same card, toggle, and summary patterns
- Same portal bar and footer

## Deployment

- Build everything locally first
- Create GitHub repo `Dhammapada` when all pages are complete
- Push and verify on GitHub Pages
- Activate the card in DharmaGate portal (remove COMING SOON badge)
