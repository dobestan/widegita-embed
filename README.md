# widegita-embed

[![npm](https://img.shields.io/npm/v/widegita-embed)](https://www.npmjs.com/package/widegita-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/widegita-embed)
[![Size](https://img.shields.io/badge/size-~5KB-green)](https://bundlephobia.com/package/widegita-embed)

Embed WideGita scripture widgets on any website. **Zero dependencies**, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and automatic daily shloka updates. Each widget includes a "Powered by WideGita" backlink.

WideGita covers the **Bhagavad Gita** — **18 chapters (adhyaya)**, **700 shlokas (verses)**, Sanskrit Devanagari script, **9 English commentators** (Prabhupada, Sivananda, Tilak, Gandhi, Vivekananda, and more), plus **196 Yoga Sutras of Patanjali** and excerpts from 12 principal **Upanishads** — all accessible via free public API.

> **Try the interactive widget builder at [widget.widegita.com](https://widget.widegita.com)**

<p align="center">
  <img src="demo.gif" alt="widegita-embed demo — Bhagavad Gita verse widget with Sanskrit Devanagari and English commentary, light/dark/sepia themes" width="800">
</p>

## Table of Contents

- [Quick Start](#quick-start)
- [What You Can Do](#what-you-can-do)
  - [Verse Card — Single Shloka Display](#verse-card--single-shloka-display)
  - [Chapter Card — Full Adhyaya with Navigation](#chapter-card--full-adhyaya-with-navigation)
  - [Comparison Card — Side-by-Side Shloka Comparison](#comparison-card--side-by-side-shloka-comparison)
  - [Verse of the Day — Auto-Updating Daily Widget](#verse-of-the-day--auto-updating-daily-widget)
  - [Search Box — Full-Text Gita Search](#search-box--full-text-gita-search)
- [Widget Options](#widget-options)
- [Themes](#themes)
- [CDN Options](#cdn-options)
- [Technical Details](#technical-details)
- [Learn More About the Bhagavad Gita](#learn-more-about-the-bhagavad-gita)
- [WideHoly Scripture Family](#wideholy-scripture-family)
- [License](#license)

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-widegita="verse" data-ref="2:47" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

That's it. The widget loads, fetches the shloka from the WideGita API, and renders it with full style isolation. References use `chapter:verse` format — `2:47` means Chapter 2, verse 47 (the famous "Karmanyevadhikaraste" shloka on detached action).

## What You Can Do

The Bhagavad Gita ("Song of God") is a 700-verse dialogue between Prince Arjuna and his charioteer Krishna on the Kurukshetra battlefield, embedded within the Mahabharata. It addresses the nature of the self (Atman), cosmic order (Dharma), devotion (Bhakti), knowledge (Jnana), and selfless action (Karma Yoga). Composed in Sanskrit in a strict metrical form (anushtubh), the Gita has been translated into over 80 languages and commented upon by Adi Shankara, Ramanuja, Madhva, and hundreds of modern scholars. WideGita makes every shloka accessible with multiple commentator perspectives in a single widget.

### Verse Card — Single Shloka Display

A Verse Card renders a single shloka in Sanskrit Devanagari script with transliteration and English translation by the selected commentator. The default commentator is Prabhupada (A.C. Bhaktivedanta Swami, ISKCON), whose word-for-word and purport format is widely used in academic and devotional contexts.

| Commentator | Code | Tradition |
|-------------|------|-----------|
| Prabhupada | `prabhupada` | Vaishnava / ISKCON |
| Sivananda | `sivananda` | Advaita / Divine Life Society |
| Tilak | `tilak` | Maharashtra school |
| Gandhi | `gandhi` | Karma Yoga emphasis |
| Vivekananda | `vivekananda` | Raja/Jnana Yoga |
| Sridhar | `sridhar` | Vaishnava |
| Chinmayananda | `chinmayananda` | Vedanta / Chinmaya Mission |
| Purohit | `purohit` | Poetic rendering |
| Yogananda | `yogananda` | Kriya Yoga / Self-Realization |

```html
<!-- Chapter 2, Verse 47 — Karmanyevadhikaraste (Do your duty without attachment) -->
<div data-widegita="verse"
  data-ref="2:47"
  data-theme="light">
</div>

<!-- Chapter 18, Verse 66 — Sarva-dharman parityajya (Surrender all dharmas to me) with Sanskrit -->
<div data-widegita="verse"
  data-ref="18:66"
  data-translation="prabhupada"
  data-show-original="true"
  data-theme="sepia">
</div>

<!-- Chapter 4, Verse 7 — Yada yada hi dharmasya (Whenever dharma declines) — Sivananda commentary -->
<div data-widegita="verse"
  data-ref="4:7"
  data-translation="sivananda"
  data-size="compact"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

**Available options for Verse Card:**

| Attribute | Values | Default |
|-----------|--------|---------|
| `data-ref` | `"chapter:verse"` e.g. `2:47` | required |
| `data-translation` | `prabhupada`, `sivananda`, `tilak`, `gandhi`, `vivekananda`, `sridhar`, `chinmayananda`, `purohit`, `yogananda` | `prabhupada` |
| `data-show-original` | `true`, `false` | `false` (shows Sanskrit + transliteration) |
| `data-theme` | `light`, `dark`, `sepia` | `light` |
| `data-size` | `default`, `compact` | `default` |

Learn more: [Bhagavad Gita Verse Lookup — widegita.com](https://widegita.com) · [Chapter 2 — Sankhya Yoga](https://widegita.com) · [Karma Yoga — Chapter 3](https://widegita.com)

### Chapter Card — Full Adhyaya with Navigation

A Chapter Card renders all shlokas in a chapter (adhyaya) with previous/next navigation. The 18 adhyayas are named after different paths of yoga — the Bhagavad Gita is itself sometimes called the "Yoga Shastra" (Scripture of Yoga).

| Chapter | Name | Yoga Path | Verses |
|---------|------|-----------|--------|
| 1 | Arjuna Vishada Yoga | Lamentation of Arjuna | 47 |
| 2 | Sankhya Yoga | Transcendent Knowledge | 72 |
| 3 | Karma Yoga | Path of Action | 43 |
| 4 | Jnana Yoga | Path of Knowledge | 42 |
| 6 | Dhyana Yoga | Path of Meditation | 47 |
| 12 | Bhakti Yoga | Path of Devotion | 20 |
| 18 | Moksha Sannyasa Yoga | Liberation through Renunciation | 78 |

```html
<!-- Chapter 2 — Sankhya Yoga (72 verses — the philosophical core) -->
<div data-widegita="chapter"
  data-ref="2"
  data-theme="light">
</div>

<!-- Chapter 12 — Bhakti Yoga (20 verses — shortest chapter) -->
<div data-widegita="chapter"
  data-ref="12"
  data-translation="sivananda"
  data-theme="sepia">
</div>

<!-- Chapter 18 — Moksha Sannyasa Yoga (78 verses — the conclusion) -->
<div data-widegita="chapter"
  data-ref="18"
  data-show-original="true"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

Learn more: [Browse All 18 Adhyayas — widegita.com](https://widegita.com) · [Yoga Paths in the Gita](https://widegita.com) · [Chapter Summaries](https://widegita.com)

### Comparison Card — Side-by-Side Shloka Comparison

Compare two shlokas — useful for showing how the same concept (dharma, moksha, karma) appears across different chapters, or for displaying how two commentators (e.g., Prabhupada vs. Gandhi) interpret the same verse differently.

The Bhagavad Gita has several recurring themes that span all 18 chapters — non-attachment (vairagya), the eternal self (atman), the perishable body (kshetra), and the nature of action (karma). The Comparison Card makes intra-text parallels explicit.

```html
<!-- Compare two descriptions of the eternal self: 2:20 vs 2:23 -->
<div data-widegita="compare"
  data-a="2:20"
  data-b="2:23"
  data-theme="light">
</div>

<!-- Compare two yoga declarations: 2:47 (Karma Yoga) vs 12:2 (Bhakti Yoga) -->
<div data-widegita="compare"
  data-a="2:47"
  data-b="12:2"
  data-show-original="true"
  data-theme="sepia">
</div>

<!-- Compare surrender verses: 9:22 vs 18:66 — two commentators -->
<div data-widegita="compare"
  data-a="18:66"
  data-b="9:22"
  data-translation="prabhupada"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

Learn more: [Gita Thematic Parallels — widegita.com](https://widegita.com) · [Commentator Comparison](https://widegita.com) · [Yoga Philosophy Concepts](https://widegita.com)

### Verse of the Day — Auto-Updating Daily Widget

The Verse of the Day widget displays a curated shloka that changes automatically each day. Results are cached in localStorage and refresh at midnight UTC. The daily selection cycles through all 700 shlokas over approximately two years, ensuring comprehensive coverage of all 18 chapters.

```html
<!-- Verse of the Day — full size, light theme -->
<div data-widegita="votd" data-theme="light"></div>

<!-- Verse of the Day — dark theme -->
<div data-widegita="votd" data-theme="dark"></div>

<!-- Verse of the Day — sepia, warm saffron-toned feel -->
<div data-widegita="votd" data-theme="sepia"></div>

<!-- Compact for narrow sidebars (shloka + chapter/verse reference only) -->
<div data-widegita="votd" data-theme="light" data-size="compact"></div>

<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

Learn more: [Daily Gita Verse — widegita.com](https://widegita.com) · [Gita Reading Schedule](https://widegita.com) · [Yoga Sutras of Patanjali — 196 sutras](https://widegita.com)

### Search Box — Full-Text Gita Search

Embed a full-text search box that queries all 700 shlokas across all 9 commentators. Results appear as the user types with chapter/verse reference and highlighted snippet. Sanskrit transliteration search is supported — searching "karma" returns all karma-related shlokas without requiring Devanagari input.

```html
<!-- Default Gita search box -->
<div data-widegita="search"
  data-placeholder="Search Bhagavad Gita verses…"
  data-theme="light">
</div>

<!-- Sanskrit-aware search -->
<div data-widegita="search"
  data-placeholder="Search in English or Sanskrit transliteration…"
  data-theme="sepia">
</div>

<!-- Dark theme search -->
<div data-widegita="search"
  data-placeholder="Find a shloka…"
  data-theme="dark">
</div>

<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

Learn more: [Gita Full-Text Search — widegita.com](https://widegita.com) · [Sanskrit Glossary](https://widegita.com) · [API Search Endpoint](https://widegita.com/developers/)

## Widget Options

All widget types share these common attributes:

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-widegita` | `verse`, `chapter`, `compare`, `votd`, `search` | required | Widget type |
| `data-ref` | `"chapter:verse"` e.g. `2:47` | — | Shloka or adhyaya reference |
| `data-a` | shloka reference | — | First shloka for comparison |
| `data-b` | shloka reference | — | Second shloka for comparison |
| `data-theme` | `light`, `dark`, `sepia` | `light` | Visual theme |
| `data-size` | `default`, `compact` | `default` | Compact suits sidebars under 300px |
| `data-translation` | `prabhupada`, `sivananda`, `tilak`, `gandhi`, `vivekananda`, `sridhar`, `chinmayananda`, `purohit`, `yogananda` | `prabhupada` | Commentator/translation |
| `data-show-original` | `true`, `false` | `false` | Show Sanskrit Devanagari + IAST transliteration |
| `data-placeholder` | any string | `"Search Bhagavad Gita…"` | Placeholder for search widget |

## Themes

WideGita widgets support 3 themes:

```html
<!-- Light — white background, dark text, amber/saffron accent -->
<div data-widegita="votd" data-theme="light"></div>

<!-- Dark — dark background, light text, amber accent -->
<div data-widegita="votd" data-theme="dark"></div>

<!-- Sepia — warm saffron-parchment tone — evokes traditional Sanskrit manuscripts -->
<div data-widegita="votd" data-theme="sepia"></div>
```

All themes are self-contained inside Shadow DOM — they never affect or inherit from your site's CSS.

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

Pin to a specific version for production stability:

```html
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1.0.1/dist/embed.min.js"></script>
```

### R2 CDN (widegita.com hosted)

```html
<script src="https://cdn.widegita.com/embed.min.js"></script>
```

### npm (for bundlers — Webpack, Vite, Rollup)

```bash
npm install widegita-embed
```

```javascript
import 'widegita-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site. Widgets are fully encapsulated.
- **Zero dependencies**: No jQuery, React, Vue, or any external library. Pure browser APIs only.
- **Devanagari rendering**: Sanskrit text renders with proper Devanagari ligatures using system fonts (Noto Sans Devanagari fallback).
- **System fonts**: No Google Fonts request — widgets use the system font stack and load instantly.
- **CORS**: WideGita API has CORS enabled for all origins — no proxy needed.
- **Caching**: Verse of the Day cached in localStorage, refreshes daily at midnight UTC.
- **MutationObserver**: Works with dynamically added elements (React, Vue, Angular SPAs).
- **Bundle size**: ~5KB gzipped.
- **Accent color**: Amber/saffron (`#F59E0B`) — matches the WideGita brand.
- **API base**: `https://widegita.com/api/v1/` — free, no authentication required.

## Learn More About the Bhagavad Gita

- **Browse**: [All 18 Chapters (Adhyayas) — widegita.com](https://widegita.com) · [Chapter Summaries](https://widegita.com) · [Yoga Paths Guide](https://widegita.com)
- **Commentators**: [Prabhupada Commentary](https://widegita.com) · [Sivananda Commentary](https://widegita.com) · [All 9 Commentators](https://widegita.com)
- **Related Texts**: [Yoga Sutras of Patanjali — 196 sutras](https://widegita.com) · [Principal Upanishads — 12 texts](https://widegita.com) · [Sanskrit Glossary](https://widegita.com)
- **Tools**: [Shloka Lookup](https://widegita.com) · [Commentator Comparison Tool](https://widegita.com) · [Widget Builder](https://widget.widegita.com)
- **API**: [REST API Docs](https://widegita.com/developers/) · [OpenAPI Spec](https://widegita.com/api/openapi.json)

## WideHoly Scripture Family

Part of [WideHoly](https://wideholy.com) — Scripture for everyone.

| Site | Domain | Scripture |
|------|--------|-----------|
| WideBible | [widebible.com](https://widebible.com) | 66 books, 31,102 verses, KJV/ASV/BBE/YLT, 1,833 people |
| WideQuran | [widequran.com](https://widequran.com) | 114 surahs, 6,236 ayahs, Arabic Uthmani + 5 translations |
| WideTorah | [widetorah.com](https://widetorah.com) | 24 books, 23,145 verses, Hebrew Masoretic + English, 54 parashot |
| **WideGita** | [widegita.com](https://widegita.com) | **18 chapters, 700 shlokas, Sanskrit Devanagari + 9 commentators, 196 Yoga Sutras** |
| WideSutra | [widesutra.com](https://widesutra.com) | 5 collections, 5,326 texts, Pali + English |
| WideHoly | [wideholy.com](https://wideholy.com) | 5 religions, 236,000+ scripture records, cross-religion comparison |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [WideHoly](https://wideholy.com).
