# mohamedmhafify.github.io

Personal portfolio — Mohamed Mostafa Hassan Afify, Data Analyst & AI Engineer.

Static single page. No build step, no dependencies.

```
├── index.html          the whole site (HTML + CSS + JS inline)
└── assets/
    ├── img/            project screenshots + portrait-cut.png / .webp
    ├── logos/          training-provider logos
    └── cv/             downloadable CVs
```

## Publishing

1. Public repo named exactly `mohamedmhafify.github.io`
2. Push to `main`
3. Settings → Pages → Source: `Deploy from a branch` → `main` / `root`
4. Live at **https://mohamedmhafify.github.io**

## Page structure

Cover · 01 About · 02 Services · 03 Selected work · 04 In action · 05 All projects ·
06 Achievements · 07 Skills & tools · 08 Experience · 09 Education & credentials · Contact

A commented-out **Testimonials** block sits between sections 06 and 07, ready to fill in.

## Updating

- **Add a project** — copy a `<tr>` inside `#idxTable`, set `data-cat` to `analytics`,
  `genai`, `vision`, or a space-separated mix, and set `data-href` to the repo URL
  (that is what makes the whole row clickable). Filter counts read from the DOM — never
  edit a count by hand.
- **Promote a project to a case** — add an `<article class="case rv" id="case-…">`, add the
  matching `<a class="star" href="#case-…">CASE ↑</a>` to its index row, and add an entry to
  the `ITEMS` array in the script so it appears in ⌘K.
- **Replace a CV** — drop the PDF into `assets/cv/` under the same filename.
- **Replace the portrait** — export a transparent PNG, keep the subject cropped flush to the
  bottom edge, and update the `width`/`height` attributes plus the `aspect-ratio` on
  `.figure-wrap` to match.

## Components worth knowing about

| Component | Where | Note |
| :--- | :--- | :--- |
| Intro curtain | `.intro` + the inline `<head>` script | Plays once per browser session; skipped entirely under `prefers-reduced-motion`. The head script sets `js-intro` synchronously so there is no flash. |
| Space backdrop | `.space` + `#stars` | Two fixed layers behind everything. Gradient `#05070D → #0B1733`, blue glow via `--glow-a` / `--glow-b`, 236 static stars. |
| Star fade | `onScroll` in the script | Stars fade on a smoothstep curve over 1.15 viewports; the glow lifts from `0.9` to `1.15` as they go. |
| Scrim | `.scrim` | Horizontal gradient over the portrait so cover text keeps contrast. Worst measured contrast on the page is 5.36:1 (AA needs 4.5). |
| Portrait box | `.figure-wrap` | Needs the explicit `aspect-ratio`; without it shrink-to-fit sizes the box from the image's intrinsic width and it comes out ~130px too wide. |
| Scroll progress | `.progress` | The ledger rule, filling as the page is read. |
| Count-up stats | `[data-count]` | `data-prefix`, `data-suffix`, `data-dec` control formatting. |
| Data figures | `.fig` | Hand-written SVG. Bars animate via `transform:scaleX`, arcs via `stroke-dashoffset`. |
| Arc maths | `--circ` / `--off` | `--off = circumference × (1 − value)`. r=44 → 276.5, r=28 → 175.9. |
| Command palette | `⌘K` / `Ctrl+K` | Items live in the `ITEMS` array at the bottom of the script. |
| Engineering notes | `<details class="note">` | The section that matters most, on the site and not only in the READMEs. |

Everything still renders with JavaScript disabled except the filters, the palette and the
star fade. All motion is disabled under `prefers-reduced-motion`.
