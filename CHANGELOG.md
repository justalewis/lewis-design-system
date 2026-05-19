# Changelog

Versioned by URL path prefix (`v1/`, `v2/`, ...). Patch changes happen
in place; breaking changes create a new prefix and leave the old
frozen.

---

## v1 — 2026-05-19

Initial release. Extracted from the stylometric-compare project as a
portable design-token file.

- **Neutrals**: warm cream base, white paper, near-black ink, four
  greys (`--bg`, `--paper`, `--ink`, `--muted`, `--muted-2`, `--rule`,
  `--rule-strong`).
- **Tinted surfaces**: four muted section colors (slate, taupe, sage,
  blush) plus softer `-soft` variants for cards on cream.
- **Accent**: deep forest green (`#2C4A3A`) as the single primary
  action color, with hover and softer variants.
- **Status colors**: four pairs (`--status-good-*`, `-warn-*`,
  `-error-*`, `-neutral-*`) for rating chips and alerts.
- **Typography**: two-family system — Cormorant Garamond for display
  (h1, h2), Inter for body and UI. Mono falls back to system
  ui-monospace. Type scale `--text-xs` through `--text-4xl`. Leading
  and tracking tokens.
- **Spacing**: 4px-base scale from `--space-1` (4px) to `--space-24`
  (96px).
- **Radii**: `--radius-sm` (4px), `--radius` (12px), `--radius-lg`
  (20px), `--radius-pill` (999px).
- **Shadows**: three subtle steps.
- **Containers**: `--container-narrow` (720px), `--container-base`
  (960px), `--container-wide` (1240px).
- **Element resets**: typographic baseline for headings, paragraphs,
  links, code, buttons, placeholders. Intentionally thin to avoid
  fighting consumer styles.
- **Fonts**: Cormorant Garamond and Inter imported via Google Fonts
  with `display=swap`.
