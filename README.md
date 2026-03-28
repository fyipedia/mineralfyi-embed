# mineralfyi-embed

[![npm](https://img.shields.io/npm/v/mineralfyi-embed)](https://www.npmjs.com/package/mineralfyi-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/mineralfyi-embed)

Embed **MineralFYI** widgets — minerals, glossary terms, interactive tools, and inline elements — on any website. **10 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), 2 styles (modern, technical), and live data from the [MineralFYI](https://mineralfyi.com) database.

Every widget includes a "Powered by MineralFYI" backlink directing readers to the full reference.

> **Try the interactive widget builder at [widget.mineralfyi.com](https://widget.mineralfyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-mineralfyi="entity" data-slug="minerals" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the MineralFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `entity` | `<div data-mineralfyi="entity" data-slug="..."></div>` | Entity detail card — element, alloy, gem, star, or mineral |
| `glossary` | `<div data-mineralfyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `guide` | `<div data-mineralfyi="guide" data-slug="..."></div>` | Guide summary card with key takeaways |
| `compare` | `<div data-mineralfyi="compare" data-slug="..."></div>` | Side-by-side entity comparison |
| `search` | `<div data-mineralfyi="search" data-slug="..."></div>` | Search box linking to the full database |
| `crystal-badge` | `<div data-mineralfyi="crystal-badge" data-slug="..."></div>` | Crystal system display badge with SVG geometry |
| `mineral-formula` | `<div data-mineralfyi="mineral-formula" data-slug="..."></div>` | Chemical formula display with subscripts |
| `mohs-inline` | `<div data-mineralfyi="mohs-inline" data-slug="..."></div>` | Inline Mohs hardness dot + number |
| `formula-inline` | `<div data-mineralfyi="formula-inline" data-slug="..."></div>` | Inline chemical formula with subscripts |
| `crystal-inline` | `<div data-mineralfyi="crystal-inline" data-slug="..."></div>` | Crystal system icon + name inline |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-mineralfyi` | entity, compare, glossary, guide, search, [tools] | required | Widget type |
| `data-slug` | e.g. "minerals" | — | Entity slug from the MineralFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-styleVariant` | modern, technical | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Minerals..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-mineralfyi="entity" data-slug="minerals" data-theme="light"></div>

<!-- Dark -->
<div data-mineralfyi="entity" data-slug="minerals" data-theme="dark"></div>

<!-- Sepia -->
<div data-mineralfyi="entity" data-slug="minerals" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-mineralfyi="entity" data-slug="minerals" data-theme="auto"></div>
```

## Styles

```html
<!-- Modern (default) — clean lines, rounded corners, accent gradients -->
<div data-mineralfyi="entity" data-slug="minerals" data-styleVariant="modern"></div>

<!-- Technical — monospace type, grid overlays, laboratory aesthetic -->
<div data-mineralfyi="entity" data-slug="minerals" data-styleVariant="technical"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<mineralfyi-entity slug="minerals" theme="light"></mineralfyi-entity>
<mineralfyi-compare slugs="minerals,other-slug"></mineralfyi-compare>
<mineralfyi-search placeholder="Search Minerals..."></mineralfyi-search>

<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Entity Card

```html
<div data-mineralfyi="entity" data-slug="minerals" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

### Side-by-Side Comparison

```html
<div data-mineralfyi="compare" data-slugs="minerals,other-slug"></div>
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-mineralfyi="search" data-placeholder="Search Minerals..."></div>
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-mineralfyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/mineralfyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install mineralfyi-embed
```

```javascript
import 'mineralfyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **2 styles**: Modern (accent gradients) and Technical (monospace, lab aesthetic)
- **4 themes**: Light, Dark, Sepia, Auto (OS preference detection)
- **CORS**: MineralFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Rich Snippets**: DefinedTerm JSON-LD injected for glossary widgets
- **Bundle size**: Tree-shaken per site — only includes tools available on MineralFYI

## Learn More About Minerals

Visit [mineralfyi.com](https://mineralfyi.com) — MineralFYI is a comprehensive minerals reference with interactive tools, guides, and developer resources.

- **API docs**: [mineralfyi.com/developers/](https://mineralfyi.com/developers/)
- **Widget builder**: [widget.mineralfyi.com](https://widget.mineralfyi.com)
- **npm package**: [npmjs.com/package/mineralfyi-embed](https://www.npmjs.com/package/mineralfyi-embed)
- **GitHub**: [github.com/fyipedia/mineralfyi-embed](https://github.com/fyipedia/mineralfyi-embed)

## Science FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Science FYI covers chemistry, geology, astronomy, and materials science. Hub: [labfyi.com](https://labfyi.com).

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| ChemFYI | [chemfyi.com](https://chemfyi.com) | Periodic table, elements, compounds, reactions | [npm](https://www.npmjs.com/package/chemfyi-embed) |
| AlloyFYI | [alloyfyi.com](https://alloyfyi.com) | Metal alloys, compositions, properties, 6-axis ratings | [npm](https://www.npmjs.com/package/alloyfyi-embed) |
| GemFYI | [gemfyi.com](https://gemfyi.com) | Gemstones, Mohs hardness, optical properties, origins | [npm](https://www.npmjs.com/package/gemfyi-embed) |
| StarFYI | [starfyi.com](https://starfyi.com) | Stars, constellations, spectral classification, magnitudes | [npm](https://www.npmjs.com/package/starfyi-embed) |
| **MineralFYI** | [mineralfyi.com](https://mineralfyi.com) | 6,215 minerals, crystal systems, Mohs hardness | **[npm](https://www.npmjs.com/package/mineralfyi-embed)** |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
