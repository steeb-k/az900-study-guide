# azure/az-900 visual design spec — blue-tinted dark pastel, IBM Plex

The Security+ kit's calm dark-pastel design with every neutral tinted blue. Dark is the designed default; light uses the same
hues on blue-gray paper. No gradients, no glassmorphism (the frosted header is the one blur), no emoji, no drop-shadow stacks.

## Fonts — self-hosted IBM Plex, zero CDN
- Files live at the repo root so other projects can share them: `/home/steeb/steeb-k.github.io/fonts/ibm-plex/`
  - `IBMPlexSans-Regular.woff2`, `IBMPlexSans-Italic.woff2`, `IBMPlexSans-Medium.woff2`, `IBMPlexSans-SemiBold.woff2`
  - `IBMPlexMono-Regular.woff2`, `IBMPlexMono-Medium.woff2`
  - `plex.css` with the `@font-face` rules (`font-display: swap`, latin + latin-ext only), `OFL.txt` (license).
- `azure/az-900/index.html` links `../../fonts/ibm-plex/plex.css`; `guide/index.html` and `tests/dev.html` link `../../../fonts/ibm-plex/plex.css`;
  the hub page `azure/index.html` links `../fonts/ibm-plex/plex.css`.
  Each page preloads Sans-Regular and Sans-SemiBold (`<link rel="preload" as="font" type="font/woff2" crossorigin>`, skipped on file://).
- Stacks: `--font-sans: "IBM Plex Sans", system-ui, sans-serif;` `--font-mono: "IBM Plex Mono", ui-monospace, monospace;`
- Hard rule: no `http://` / `https://` in link, script or preload tags, no `@import`, no `fonts.googleapis`, no `cdn`. The only external
  URLs are the GitHub links (header, home "Source", guide footer). `tests/smoke.sh` enforces this.

## Palette (the Security+ kit's structure, neutrals tinted blue)
Dark (default)
```
--bg-0:#060b14  --bg-1:#0e1622  --bg-2:#172232  --bg-3:#213044   --hdr-bg: rgba(14,22,34,.45)
--line:#1f2c3f  --line-strong:#33455e
--ink:#eaf1fb   --ink-2:#b3c2d6  --ink-3:#8fa0b8
--accent:#6cb4f5  --accent-hi:#93c8f8  --accent-ink:#060b14  --accent-tint:rgba(108,180,245,.14)
--ok:#8fe0a6  --bad:#f29aa1  --warn:#f2d383  (tints at .14)   --info = accent   --shadow: none
```
Light (blue-gray paper, same structure; `[data-theme="light"]` or `prefers-color-scheme: light` without a stored theme)
```
--bg-0:#edf2f8  --bg-1:#f8fafd  --bg-2:#e6edf5  --bg-3:#d9e3ee   --hdr-bg: rgba(248,250,253,.5)
--line:#d5dfea  --line-strong:#b9c7d8
--ink:#0d1726   --ink-2:#43536a  --ink-3:#536279
--accent:#0f6cbd  --accent-hi:#0c5aa0  --accent-ink:#ffffff  --accent-tint:rgba(15,108,189,.10)
--ok:#2b7a45  --bad:#a8404b  --warn:#7d5f0a  (tints .10–.12)   --shadow: 0 1px 2px rgba(20,40,70,.07)
```
Print always uses a white-paper light palette (`@media print`, accent `#0b4f8a`), whatever the screen theme, and hides the header
and actions.
Rationale: every neutral carries the same blue hue so the kit reads as "the Azure one" next to the gray Security+ kit; near-black
navy depth and bright ink for separation; status colors (ok / bad / warn) are unchanged so right and wrong look the same in both kits.
The guide adds highlight tokens `--hl`, `--hl-ink`, `--hl-tint` in guide.css (see GUIDE-SITE.md "Highlights").

## Type scale
Base 16px / line-height 1.55, body color `--ink`. h1 26px/600 letter-spacing -0.01em (22px under 560px); h2 20px/600; h3 16px/600;
small/meta 13.5px `--ink-2`; uppercase labels 11.5px/500, letter-spacing .07em, `--ink-3`.
Mono (`--font-mono`): timer, question counter, keyboard number chips, acronym keys, scores in tables, the pill's exam code.

## Shape, surface, spacing
Radii: `--r-card` 10px, `--r-btn` 8px (buttons, inputs, selects, fieldsets), `--r-chip` 6px (chips, grid cells). Borders 1px `--line`;
hover `--line-strong`. Cards and panels = `--bg-1` on page `--bg-0`; inputs/options = `--bg-2`.
Spacing scale `--s1…--s7` = 4/8/12/16/24/32/48px.
Layout tokens: `--page-w` 1240px (header grid and guide layout), `--side-w` 280px (sidebar column), `--col-w` 820px (reading column on
every page: `main` on practice pages, the content column of the guide). Gutters 24px; 16px below 900px.
Focus: `:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px }` everywhere; outlines are never removed.
Motion: `.opt, .btn, .card, .cell` transition border/background .12s only under `prefers-reduced-motion: no-preference`.

## Site header (shared by the practice page, the guide and tests/dev.html)
Markup on every page: `header.site-header > div.hwrap > a.brand + div.hnav > nav`, followed directly by `<script src="js/header.js">`
(`../js/header.js` from guide/ and tests/). The header is sticky (z-index 5), `--bg-1` with a 1px bottom `--line`; where
backdrop-filter is supported it is `--hdr-bg` with `blur(14px) saturate(1.15)` so content slides beneath it.
- `.hwrap` is a `--page-w` grid of `--side-w` + content column; the pill sits 16px into the first column; the nav is right-aligned
  inside a `--col-w` box centered in the content column. The practice page has no sidebar but uses the same grid, so pill and links
  sit at identical pixel positions on every page (guide-ui.test.js checks 1280, 1000 and 390). Below 900px the wrapper is a flex row
  with 16px gutters and the nav gap tightens to `--s3`.
- Nav links: Guide, Practice (same tab; `aria-current="page"` marks the section you are in, underlined in `--accent`), GitHub (study-guide
  repo, new tab, inline external-link icon). Links are `--ink-2` → `--ink` on hover, weight 500. History and Settings live on the
  practice home page only.
- The pill links to `#/` on both pages: the practice home on the practice page, the Exam Overview on the guide. It never switches sections.

### Header wordmark
- The brand is a single two-segment pill reading **"Azure Fundamentals | AZ-900"**. The pages' `<title>` strings stay short: "AZ-900",
  "AZ-900 Guide", "<section> · AZ-900 Guide".
- Markup: `<a class="brand" href="#/" aria-label="Azure Fundamentals AZ-900 home"><span class="brand-pill"><span class="brand-l"><span class="brand-full">Azure Fundamentals</span><span class="brand-abbr">Azure</span></span><span class="brand-r"><span class="brand-full">AZ-900</span><span class="brand-abbr">900</span></span></span></a>`.
- Fit: the pill shows "Azure Fundamentals | AZ-900" whenever it fits. "Fits" means the nav neither runs into the pill nor past the header's
  right edge. When it does not, `js/header.js` steps the header's `data-brand` down only as far as needed: `short` → "Azure | AZ-900",
  then `tiny` → "Azure | 900" (narrow phones). CSS toggles the `.brand-full` / `.brand-abbr` spans inside each segment; `.brand-pill`
  and the nav are `white-space: nowrap` so nothing ever wraps to a second line. Measured on load, on resize and on
  `document.fonts.ready`; both pages load the same script, so their pills always agree.
- `.brand-pill`: inline-flex, border-radius 999px, a 1.5px outline in `--ink` drawn as a spread box-shadow (Chromium snaps border widths
  to whole pixels), background `--ink`, 1.5px margin, overflow hidden so the segments clip to the pill shape, font-weight 600, 14px,
  line-height 1, letter-spacing .01em. In light theme the same tokens give a dark/paper inversion with the same structure. Under
  `forced-colors` the shadow becomes a 1px CanvasText border.
- `.brand-l` ("Azure Fundamentals" / "Azure"): background `--ink`, text `--bg-0`, padding 5px 10px 5px 12px.
- `.brand-r` ("AZ-900" / "900"): background `--bg-0`, text `--ink`, padding 5px 12px 5px 10px, font-family `--font-mono`.
- The outline runs around the whole pill; there is no inner divider beyond the color change. No hover color change; the whole link gets
  the standard focus ring. The practice home's h1 "Azure Fundamentals AZ-900 practice" is visually hidden (`.sr`) and kept for screen readers.

## Favicon
`icons/favicon.svg` (plus `favicon.ico` 16/32/48, `favicon-32.png`, `favicon-192.png`, `favicon-512.png`, `apple-touch-icon.png`),
regenerated by `python3 icons/make-favicon.py [outline] [divider-y] [AZ-height] [900-height]` (defaults 30 262 150 130) followed by
rsvg-convert / magick (commands in the script's docstring). Shape: the Security+ favicon turned on its side: a 512px squircle
(rx 133) in `#eaf1fb` with an inset ink (`#060b14`) segment across the bottom (clipped to the inner rounded rect), "AZ" in Plex Sans
SemiBold on the paper half, "900" in paper on the ink half. Same idea as the header pill: the paper outline and the "AZ" segment
are a single shape. Glyph outlines come from the self-hosted font. The hub page uses the same icon until a second exam exists.

## Hub page (`azure/index.html`)
One card per exam (code in mono, name, one-line summary, Practice and Study guide buttons), using `az-900/css/style.css` and the same
header markup with a static "Azure | Exams" pill (no header.js: nothing to shorten). Adding an exam = adding a card.

## Components (practice page)
- Buttons: primary = `--accent` bg, `--accent-ink` text, hover `--accent-hi`; secondary = transparent, 1px `--line-strong`, `--ink`;
  danger = transparent with `--bad` border/text; disabled 45% opacity. Min height 40px, 44px on touch widths.
- Domain cards: title 600, meta line `--ink-2`, readiness badge = pastel chip (`--ok-tint`/`--ok`, `--warn-tint`/`--warn`,
  `--bad-tint`/`--bad`, neutral `--bg-3`/`--ink-2`). Final Exam card gets a 3px top rule in `--accent` (not a full border).
- Home footer nav: History, Settings, Source (GitHub, new tab) as secondary buttons. A "Resume in-progress …" banner (`.banner`,
  accent tint and border) appears above the cards while a session exists.
- Question card: stem 17px; options are full-width rows on `--bg-2`, 1px `--line`; hover `--line-strong`; keyboard chip (mono,
  `--bg-3`, `--ink-2`) left; selected = `--accent` border + `--accent-tint` bg; correct = `--ok` border + `--ok-tint`; incorrect =
  `--bad` border + `--bad-tint`; correct/incorrect marks are inline SVG in the matching color at the right.
- Feedback panel: left 3px rule in `--ok` or `--bad`, bg = matching tint, "Correct"/"Incorrect" 600 in the hue, explanation `--ink`,
  objective line `--ink-2` linking into the guide, acronym block: uppercase label, keys in mono 600 `--ink`, expansions `--ink-2`.
- Review grid: 36px cells, mono numbers; answered = `--accent-tint` bg + `--accent` border; unanswered = dashed `--line-strong`;
  flagged = `--warn` border + small corner triangle in `--warn`; current = 2px `--accent` ring. Legend chips reuse the same styles.
- Timer: mono 18px; `.low` (`--warn`) under 10 minutes, `.crit` (`--bad`) under 2 minutes; the class is applied on route render and
  every 500ms tick. Pause button secondary; while paused the question is hidden behind a "Paused" panel.
- Results: big score in mono 40px/500; pass pill `--ok-tint`/`--ok`, fail pill `--bad-tint`/`--bad`; per-domain table: thin rules,
  right-aligned mono numbers, a 6px bar in `--accent` on a `--bg-3` track (bars hidden under 560px); weakest objectives table the same.
- History: table rows with `--line` separators, readiness chips, bars as above, no chart library. Tables sit in `.table-wrap`
  (horizontal scroll inside the card when needed).
- Settings: grouped panels, checkboxes/radios use `accent-color: var(--accent)`.
- Interactive items (the PBQ engine; `pbq` in code and class names): match selects and config dropdowns styled as inputs (`--bg-2`, 1px `--line`, `--r-btn`). Config items are stacked rows
  (`.pbq-rows`) whose fields wrap, so every dropdown is visible at any width. Ordering items are a numbered list of rows (`.pbq-order li`,
  `--bg-2`, 1px `--line`, 54px min height, the position number in a `--bg-3` chip) with Up/Down secondary buttons that wrap under the
  text on phones.
- Theme: default setting `dark` (settings offer auto / light / dark); `body` has an explicit background in both themes. The guide reads
  the same `az900.settings` theme before first paint.
- Scrolling: moving to the previous/next question (or jumping from the review grid) scrolls the window back to the top smoothly
  (`behavior: 'smooth'`, instant under `prefers-reduced-motion: reduce`). Opening a different page (`paint()` on a route change) starts
  at the top instantly, since the content under the reader is new.

### Ordering items: swap animation
Pressing Up or Down re-renders the question, but `animateSwap()` in app.js measures the rows' tops before the re-render and afterwards
plays the difference on the two rows that changed places (Web Animations API, 240ms, `cubic-bezier(.2,.7,.2,1)`, translateY only), so
the two items visibly slide past each other. The moved row carries `.swapped` for 450ms: accent border (`border-color .3s` transition
under `prefers-reduced-motion: no-preference`) and `z-index: 1` so it passes over the other row. With reduced motion the slide is skipped
and only the tint shows. Focus follows the moved row's button (`po<pos>u` / `po<pos>d`).
