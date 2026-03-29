# widegita-embed

[![npm](https://img.shields.io/npm/v/widegita-embed)](https://www.npmjs.com/package/widegita-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/widegita-embed)
[![Size](https://img.shields.io/badge/size-~5KB-green)](https://bundlephobia.com/package/widegita-embed)

Embed WideGita scripture widgets on any website. **Zero dependencies**, Shadow DOM style isolation, 3 built-in themes (light, dark, sepia), and automatic daily verse updates. Each widget includes a "Powered by WideGita" backlink.

> **Try the interactive widget builder at [widget.widegita.com](https://widget.widegita.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-widegita="verse" data-ref="2:47" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

That's it. The widget will load, fetch the verse from the WideGita API, and render it with full style isolation.

## Widget Types

| Type | Usage |
|------|-------|
| Verse Card | `<div data-widegita="verse" data-ref="..." data-theme="light"></div>` |
| Chapter Card | `<div data-widegita="chapter" data-ref="..."></div>` |
| Comparison Card | `<div data-widegita="compare" data-a="..." data-b="..."></div>` |
| Verse of the Day | `<div data-widegita="votd" data-theme="light"></div>` |
| Search Box | `<div data-widegita="search" data-placeholder="..."></div>` |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-widegita` | verse, chapter, person, compare, votd, search | required | Widget type |
| `data-ref` | "2:255" | — | Verse/chapter reference |
| `data-slug` | "moses", "paul" | — | Person slug (person widget only) |
| `data-a` | verse ref | — | First verse for comparison |
| `data-b` | verse ref | — | Second verse for comparison |
| `data-theme` | light, dark, sepia | light | Visual theme |
| `data-size` | default, compact | default | Widget size |
| `data-translation` | prabhupada, etc. | prabhupada | Translation code |
| `data-show-original` | true, false | false | Show original language text |
| `data-placeholder` | any string | "Search Bhagavad Gita…" | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-widegita="votd" data-theme="light"></div>

<!-- Dark -->
<div data-widegita="votd" data-theme="dark"></div>

<!-- Sepia (warm, book-like) -->
<div data-widegita="votd" data-theme="sepia"></div>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

### R2 CDN (widegita.com hosted)

```html
<script src="https://cdn.widegita.com/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install widegita-embed
```

```javascript
import 'widegita-embed';
```

## Examples

### Verse of the Day

```html
<div data-widegita="votd" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

### Verse with Original Language

```html
<div data-widegita="verse"
  data-ref="1:1"
  data-show-original="true"
  data-theme="sepia">
</div>
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

### Compact Verse of the Day (sidebar use)

```html
<div data-widegita="votd" data-theme="light" data-size="compact"></div>
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-widegita="search" data-placeholder="Search Bhagavad Gita…"></div>
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **System fonts**: No Google Fonts request — loads instantly
- **CORS**: WideGita API has CORS enabled for all origins
- **Caching**: Verse of the Day cached in localStorage (refreshes daily)
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **Bundle size**: ~5KB gzipped

## Learn More About Bhagavad Gita

Visit [widegita.com](https://widegita.com) — WideGita is a comprehensive Bhagavad Gita reference with full text, translations, and study tools.

- **API docs**: [widegita.com/developers/](https://widegita.com/developers/)
- **Widget builder**: [widget.widegita.com](https://widget.widegita.com)
- **npm package**: [npmjs.com/package/widegita-embed](https://www.npmjs.com/package/widegita-embed)

## WideHoly Scripture Family

Part of [WideHoly](https://wideholy.com) — Scripture for everyone.

| Site | Domain | Scripture |
|------|--------|-----------|
| **WideBible** | [widebible.com](https://widebible.com) | Bible verses, chapters, people |
| **WideQuran** | [widequran.com](https://widequran.com) | Quran verses, surahs |
| **WideTorah** | [widetorah.com](https://widetorah.com) | Torah verses, portions |
| **WideGita** | [widegita.com](https://widegita.com) | Bhagavad Gita verses |
| **WideSutra** | [widesutra.com](https://widesutra.com) | Buddhist sutras, teachings |
| **WideHoly** | [wideholy.com](https://wideholy.com) | Multi-religion scripture hub |

## Embed Widget

Embed [WideGita](https://widegita.com) widgets on any website with [widegita-embed](https://widget.widegita.com):

```html
<script src="https://cdn.jsdelivr.net/npm/widegita-embed@1/dist/embed.min.js"></script>
<div data-widegita="entity" data-slug="example"></div>
```

Zero dependencies · Shadow DOM · 4 themes (light/dark/sepia/auto) · [Widget docs](https://widget.widegita.com)

## License

MIT — see [LICENSE](./LICENSE).

Built with ❤️ by [WideHoly](https://wideholy.com).
