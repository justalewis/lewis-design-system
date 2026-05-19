# Lewis Design System

A small, portable set of CSS design tokens — colors, typography,
spacing, radii, shadows — shared across Justin's projects so they
all carry the same visual identity without depending on a JS
framework or a build step.

The aesthetic is editorial: warm cream base, near-black text, a
single deep-forest-green accent, four muted tinted surfaces for
section panels, two type families (Cormorant Garamond display +
Inter body), and pill-shaped interactive elements.

**Live tokens (CDN):**
<https://justalewis.github.io/lewis-design-system/v1/tokens.css>

**Live showcase** (palette + typography + components in use):
<https://justalewis.github.io/lewis-design-system/>

---

## Using it in a project

Add one `<link>` to the project's HTML `<head>` before any
project-specific stylesheet:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet"
      href="https://justalewis.github.io/lewis-design-system/v1/tokens.css">
<link rel="stylesheet" href="/your/project/style.css">
```

Then reference the tokens from your project's stylesheet:

```css
.card {
  background: var(--paper);
  color: var(--ink);
  border: 1px solid var(--rule);
  border-radius: var(--radius);
  padding: var(--space-6) var(--space-8);
  font-family: var(--font-body);
}

.card h2 {
  font-family: var(--font-display);
  color: var(--accent);
  font-size: var(--text-2xl);
}
```

When the design system updates, every project that links the same
versioned URL picks up the change automatically. Versioning policy is
below.

---

## What's in v1

`v1/tokens.css` defines, as CSS custom properties on `:root`:

### Colors
- **Neutrals**: `--bg` (warm cream), `--paper` (white), `--ink`,
  `--muted`, `--muted-2`, `--rule`, `--rule-strong`
- **Tinted surfaces** (for full-width section panels):
  `--surface-slate`, `--surface-taupe`, `--surface-sage`,
  `--surface-blush`, each with a `-soft` variant
- **Accent**: `--accent` (deep forest green), `--accent-hover`,
  `--accent-soft`
- **Status** (rating chips, alerts): `--status-good-*`,
  `--status-warn-*`, `--status-error-*`, `--status-neutral-*`

### Typography
- `--font-display`: Cormorant Garamond, with Georgia fallback
- `--font-body`: Inter, with system fallbacks
- `--font-mono`: ui-monospace, with system fallbacks
- Type scale: `--text-xs` through `--text-4xl`
- Leading: `--leading-tight`, `--leading-snug`, `--leading-base`
- Tracking: `--tracking-wide`, `--tracking-base`, `--tracking-tight`

### Spacing
4-pixel base, ramping through `--space-1` (4px) to `--space-24`
(96px). Use these for padding, margin, and gap throughout.

### Radii
- `--radius-sm` (4px), `--radius` (12px), `--radius-lg` (20px),
  `--radius-pill` (999px)

### Shadows
- `--shadow-sm`, `--shadow`, `--shadow-lg` — subtle by default; the
  editorial aesthetic is mostly flat.

### Layout
- `--container-narrow` (720px), `--container-base` (960px),
  `--container-wide` (1240px)

Plus minimal element resets: typographic baseline for `<h1>`-`<h6>`,
`<p>`, `<a>`, `<code>`, `<button>`, and `::placeholder`. The reset is
deliberately thin so it doesn't fight project-specific component
styles.

---

## Versioning

URLs use a path prefix (`v1/...`) so that any change to existing
tokens that would break consumers gets a new prefix (`v2/...`)
rather than mutating v1.

- **Patch changes** (new tokens, value tweaks that won't break
  consumers): edit `v1/tokens.css` in place; consumers pick up the
  change on next cache miss.
- **Breaking changes** (renaming or removing tokens, changing
  component semantics): copy `v1/` to `v2/`, edit `v2/`, leave `v1/`
  frozen so older projects keep working until they're explicitly
  migrated.

See [CHANGELOG.md](CHANGELOG.md) for what's changed.

---

## License

MIT. Use it, fork it, vendor it — no obligation back to this repo.
