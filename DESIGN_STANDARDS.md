# Design standards

Canonical rules for every site, tool, app, README and writeup published under
[github.com/lyhjeremy](https://github.com/lyhjeremy).

The purpose is narrow: nothing published should read as though a model designed it.
The list below is the set of visual and copy patterns that currently signal machine
authorship to a reader who has seen a lot of them. Most are not bad ideas in isolation.
They are banned because they cluster, and the cluster is the tell.

This file is the source of truth. Where it conflicts with an older document, this file
wins. Published copy lives at
`https://github.com/lyhjeremy/lyhjeremy/blob/main/DESIGN_STANDARDS.md`.

Status: adopted 2026-08-18. Supersedes the cream/navy/gold Georgia house style
recorded in `PROJECTS_SUMMARY.md`.

## Exceptions

The portfolio root site, [lyhjeremy/lyhjeremy.github.io](https://github.com/lyhjeremy/lyhjeremy.github.io), follows apple.com conventions instead of Ledger (owner's decision, 2026-08-23): system sans, white and `#f5f5f7` surfaces with an opt-in dark theme, rounded white-matted cards, six category tints, standard hover motion. `designcheck.py` is not run against that repo. Every individual project site remains under this standard, so the hub and the projects look deliberately different.


---

## 1. The rejection list

Thirty patterns. Every one of these is a hard no. The right-hand column is the
replacement, not a suggestion.

### Color and surface

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Harsh gradients | Two saturated hues blended across a hero is the single most common generated-site signature. | Flat fields of one color. If a surface must separate from its neighbour, change its value, not its hue. |
| Pure white background (`#fff`) | Default that nobody chose. | `--paper`, a tinted off-white. Never `#ffffff`. |
| Purple and black | The default accent pair of every scaffolded template. | The oxide and pine accents in section 2. No purple at any value. |
| Rainbow coloring | More than two accent hues on one page reads as decoration with no meaning. | Two accents total, each with a fixed job. A third hue requires a data reason. |
| Neon colors | Saturation above roughly 70% in a UI context. | Muted, earth-shifted values. Every accent below 60% saturation. |
| Basic pastel colors | Tinted pastels signal a color picker set to 90% lightness. | Muted values at mid lightness, warm-neutral rather than tinted. |
| Radial orbs | Blurred colored circles behind a hero. | Nothing behind the hero. The page ground is the background. |
| Dot grids | Decorative dotted or gridded backdrops. | Empty ground. Structure comes from rules and alignment. |
| Liquid glass | Frosted translucency, `backdrop-filter`, layered blur panels. | Opaque surfaces with a hairline border. `backdrop-filter` is banned outright. |
| Drop shadows | Fake depth. | Depth is expressed by border weight and surface value only. `box-shadow` is banned outright, including on focus states. |

### Geometry and layout

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Soft corner radius | The 8px to 16px rounded rectangle on every card, button and input. | `border-radius: 0` everywhere, with no exceptions. |
| Three feature cards in a row | The canonical generated layout. | A bordered table, a definition list, or prose. If three things must be enumerated, enumerate them in a list. |
| Bento grids | Mixed-span tile mosaics. | One column for prose. An asymmetric two-column for reference material. Nothing else. |
| Colored left stripe | The 4px accent border on callouts and quotes. | A full hairline border on all four sides, or no border and an indent. |
| Terminal window chrome | Fake title bars and traffic-light dots framing code. | A plain bordered `<pre>` with a caption naming what produced the output. |
| Lucide icons | Recognizable at a glance, and recognizably the default. | No icon library of any kind. Text labels. Where a mark is genuinely required, hand-author the SVG. |
| Sparkle icons | The AI-feature glyph. | Nothing. Do not mark a feature as AI-powered with a symbol. Say what it does. |
| Emojis | In headings, bullets, section markers, README titles, commit messages, anywhere. | Words. |

### Motion

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Hover animations | Lift, scale, glow, and any `transition` on an interactive state. | Instant state change on color and border only. No `transition` property on hover, focus or active states. |
| Animated arrows | Bouncing, sliding or pulsing directional glyphs. | A static text link. If direction matters, the words carry it. An arrow character in prose, an ASCII diagram or linguistic notation is typography and stays legal. Only motion attached to an arrow is banned. |

Motion is permitted in exactly two places: skeleton loaders (section 4) and genuine data
animation where the movement is the information, such as a simulation replaying. Both must
respect `prefers-reduced-motion: reduce` and stop entirely under it. Scroll-triggered
reveals, parallax, marquees and entrance animations are banned.

### Typography

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Inter, Geist, Space Grotesk | The three default faces of generated interfaces. | The stack in section 2. These three faces must not appear in any stylesheet, including as a fallback. |
| Em dashes | The strongest text-level signal, and the reason the exception in `~/.claude/CLAUDE.md` was removed on 2026-08-18. | A colon, a comma, parentheses, or a period. No em dash in body copy, headings, titles, alt text, captions, commit messages, repo descriptions or UI strings. The en dash stays legal for numeric ranges only (`2014-2024`). |

### Copy and content

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Checkmark bullets | Tick glyphs standing in for list markers. | A plain bullet, a number, or a table. |
| "It's not X, it's Y" | Negative parallelism, along with "not just X but also Y". | State the claim once, positively. |
| Fake testimonials | Invented names, invented quotes, invented job titles. | Real attributed feedback, or no testimonial section. Silence is honest. |
| Three pricing tiers | The Free / Pro / Enterprise ladder on a project with no pricing. | No pricing section. These tools are free. If running cost is relevant, state the number in a sentence. |

### Absences that are themselves the tell

These four items appear on the list because their absence signals a project that was
generated and never operated. Each becomes a requirement. Section 4 has the detail.

| Requirement | Rule |
|---|---|
| Real product demos | Every tool links to a working instance, or shows captured real output with a caption stating what produced it and when. A mockup presented as a product is banned. |
| Skeleton loaders | Any async state that can exceed roughly 200ms renders a skeleton. A bare spinner or an empty container is not acceptable. |
| Privacy policy | Required for anything that collects, stores or transmits user input, including analytics and third-party API calls. |
| Terms of service | Required for anything with a live backend, an account, or user-submitted content. |

---

## 2. The identity

Named "Ledger" for reference in commits. The reference point is a technical document:
ink on paper, hairline rules, real typographic hierarchy, no ornament. It replaces the
cream and gold Georgia style across the whole portfolio.

### Palette

Every value below was checked against WCAG 2.1 on 2026-08-18. Ratios are stated because
a palette that has not been measured is a guess.

Light:

```css
:root {
  --paper:    #EDEDE7;  /* page ground, tinted off-white */
  --panel:    #F5F5F0;  /* inset surfaces, tables, pre blocks */
  --ink:      #1C1E1B;  /* primary text        14.28:1 on paper  AAA */
  --ink-2:    #52564E;  /* secondary text       6.38:1 on paper  AA  */
  --rule:     #C6C7BF;  /* decorative hairline separators only */
  --edge:     #767A70;  /* interactive boundary 3.73:1 on paper  1.4.11 */
  --signal:   #8C3A1E;  /* oxide, primary accent 6.52:1 on paper AA  */
  --signal-2: #2C5852;  /* pine, secondary accent 6.81:1 on paper AA */
}
```

Dark:

```css
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --paper:    #191B18;  /* never #000 */
    --panel:    #212420;
    --ink:      #E6E6DE;  /* 13.82:1 */
    --ink-2:    #A2A69B;  /*  6.99:1 */
    --rule:     #3B3F38;
    --edge:     #6A6F66;  /*  3.37:1 */
    --signal:   #D8825C;  /*  6.00:1 */
    --signal-2: #74AFA5;  /*  6.95:1 */
  }
}
```

Rules of use:

1. `--rule` is for separators that carry no interaction. It sits below 3:1 by design and
   must never be the only boundary of a control.
2. `--edge` is for anything a user can click, type into or focus. It clears 3:1 in both
   themes.
3. A filled button takes `--signal` as its background and the current theme's `--paper`
   as its label. That pairing measures 6.52:1 in light and 6.00:1 in dark. Never use
   `--ink` on `--signal`, which falls to 2.19:1.
4. `--signal` carries emphasis, links and primary actions. `--signal-2` carries a second
   data series or a secondary state. Nothing else gets a hue.
5. Define the full light palette on bare `:root`. Redefine only what changes in the dark
   block. Never give a color its only definition inside a media query.

### Type

Self-hosted. No third-party request is made for any asset, which keeps claims like
"runs entirely in your browser, nothing is uploaded" literally true. The bundle lives at
`_ai-projects-tooling/ledger/fonts/` and is copied into each repo under
`assets/ledger/fonts/`.

```css
--font-head: "Source Serif 4", "Iowan Old Style", "Palatino Linotype", Palatino, serif;
--font-body: "IBM Plex Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
--font-mono: "IBM Plex Mono", "SF Mono", Menlo, Consolas, monospace;
```

Five files, two weights per proportional face, latin plus the punctuation and math signs
the data pages actually use. Measured 2026-08-18:

| Face | Upstream TTF | Subset woff2 |
|---|---|---|
| Source Serif 4 400 | 190 KB | 19.7 KB |
| Source Serif 4 600 | 190 KB | 21.0 KB |
| IBM Plex Sans 400 | 200 KB | 15.7 KB |
| IBM Plex Sans 600 | 200 KB | 17.4 KB |
| IBM Plex Mono 400 | 126 KB | 8.7 KB |
| Total | 907 KB | 82.6 KB |

Rebuild with `python3 _ai-projects-tooling/ledger/build_fonts.py`. Two traps are recorded
in that script and must not be undone:

1. Subset with `--layout-features=*`. Passing an explicit feature list silently drops
   `tnum` even when `tnum` is named in the list. The wildcard costs under 1 KB per face.
2. Google's IBM Plex builds contain no `tnum` at all, confirmed against the upstream
   files. Numeric columns therefore have to use IBM Plex Mono, which is monospaced and so
   inherently tabular. Setting `font-variant-numeric: tabular-nums` on IBM Plex Sans does
   nothing. Source Serif 4 does carry `tnum`.

Source Serif 4 sets every heading. IBM Plex Sans sets interface text, table cells,
captions and labels. IBM Plex Mono sets numerals in data tables, code, and captured
output. Long-form writeup pages may set body copy in Source Serif 4 at 1.05rem; app
interfaces always use IBM Plex Sans.

Monospace type is not the same thing as terminal window chrome. Mono is encouraged for
figures and data. The fake window frame around it is what is banned.

Scale, on a 1.25 ratio from a 16px base: 3.05rem, 2.44rem, 1.95rem, 1.56rem, 1.25rem,
1rem, 0.8rem. Prose measure caps at 68 characters. Body line height 1.6, headings 1.15.

### Geometry and layout

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Soft corner radius | The 8px to 16px rounded rectangle on every card, button and input. | `border-radius: 0` everywhere, with no exceptions. |
| Three feature cards in a row | The canonical generated layout. | A bordered table, a definition list, or prose. If three things must be enumerated, enumerate them in a list. |
| Bento grids | Mixed-span tile mosaics. | One column for prose. An asymmetric two-column for reference material. Nothing else. |
| Colored left stripe | The 4px accent border on callouts and quotes. | A full hairline border on all four sides, or no border and an indent. |
| Terminal window chrome | Fake title bars and traffic-light dots framing code. | A plain bordered `<pre>` with a caption naming what produced the output. |
| Lucide icons | Recognizable at a glance, and recognizably the default. | No icon library of any kind. Text labels. Where a mark is genuinely required, hand-author the SVG. |
| Sparkle icons | The AI-feature glyph. | Nothing. Do not mark a feature as AI-powered with a symbol. Say what it does. |
| Emojis | In headings, bullets, section markers, README titles, commit messages, anywhere. | Words. |

### Motion

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Hover animations | Lift, scale, glow, and any `transition` on an interactive state. | Instant state change on color and border only. No `transition` property on hover, focus or active states. |
| Animated arrows | Bouncing, sliding or pulsing directional glyphs. | A static text link. If direction matters, the words carry it. An arrow character in prose, an ASCII diagram or linguistic notation is typography and stays legal. Only motion attached to an arrow is banned. |

Motion is permitted in exactly two places: skeleton loaders (section 4) and genuine data
animation where the movement is the information, such as a simulation replaying. Both must
respect `prefers-reduced-motion: reduce` and stop entirely under it. Scroll-triggered
reveals, parallax, marquees and entrance animations are banned.

### Typography

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Inter, Geist, Space Grotesk | The three default faces of generated interfaces. | The stack in section 2. These three faces must not appear in any stylesheet, including as a fallback. |
| Em dashes | The strongest text-level signal, and the reason the exception in `~/.claude/CLAUDE.md` was removed on 2026-08-18. | A colon, a comma, parentheses, or a period. No em dash in body copy, headings, titles, alt text, captions, commit messages, repo descriptions or UI strings. The en dash stays legal for numeric ranges only (`2014-2024`). |

### Copy and content

| Rejected | Why it reads as generated | Use instead |
|---|---|---|
| Checkmark bullets | Tick glyphs standing in for list markers. | A plain bullet, a number, or a table. |
| "It's not X, it's Y" | Negative parallelism, along with "not just X but also Y". | State the claim once, positively. |
| Fake testimonials | Invented names, invented quotes, invented job titles. | Real attributed feedback, or no testimonial section. Silence is honest. |
| Three pricing tiers | The Free / Pro / Enterprise ladder on a project with no pricing. | No pricing section. These tools are free. If running cost is relevant, state the number in a sentence. |

### Absences that are themselves the tell

These four items appear on the list because their absence signals a project that was
generated and never operated. Each becomes a requirement. Section 4 has the detail.

| Requirement | Rule |
|---|---|
| Real product demos | Every tool links to a working instance, or shows captured real output with a caption stating what produced it and when. A mockup presented as a product is banned. |
| Skeleton loaders | Any async state that can exceed roughly 200ms renders a skeleton. A bare spinner or an empty container is not acceptable. |
| Privacy policy | Required for anything that collects, stores or transmits user input, including analytics and third-party API calls. |
| Terms of service | Required for anything with a live backend, an account, or user-submitted content. |

---

## 2. The identity

Named "Ledger" for reference in commits. The reference point is a technical document:
ink on paper, hairline rules, real typographic hierarchy, no ornament. It replaces the
cream and gold Georgia style across the whole portfolio.

### Palette

Every value below was checked against WCAG 2.1 on 2026-08-18. Ratios are stated because
a palette that has not been measured is a guess.

Light:

```css
:root {
  --paper:    #EDEDE7;  /* page ground, tinted off-white */
  --panel:    #F5F5F0;  /* inset surfaces, tables, pre blocks */
  --ink:      #1C1E1B;  /* primary text        14.28:1 on paper  AAA */
  --ink-2:    #52564E;  /* secondary text       6.38:1 on paper  AA  */
  --rule:     #C6C7BF;  /* decorative hairline separators only */
  --edge:     #767A70;  /* interactive boundary 3.73:1 on paper  1.4.11 */
  --signal:   #8C3A1E;  /* oxide, primary accent 6.52:1 on paper AA  */
  --signal-2: #2C5852;  /* pine, secondary accent 6.81:1 on paper AA */
}
```

Dark:

```css
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --paper:    #191B18;  /* never #000 */
    --panel:    #212420;
    --ink:      #E6E6DE;  /* 13.82:1 */
    --ink-2:    #A2A69B;  /*  6.99:1 */
    --rule:     #3B3F38;
    --edge:     #6A6F66;  /*  3.37:1 */
    --signal:   #D8825C;  /*  6.00:1 */
    --signal-2: #74AFA5;  /*  6.95:1 */
  }
}
```

Rules of use:

1. `--rule` is for separators that carry no interaction. It sits below 3:1 by design and
   must never be the only boundary of a control.
2. `--edge` is for anything a user can click, type into or focus. It clears 3:1 in both
   themes.
3. A filled button takes `--signal` as its background and the current theme's `--paper`
   as its label. That pairing measures 6.52:1 in light and 6.00:1 in dark. Never use
   `--ink` on `--signal`, which falls to 2.19:1.
4. `--signal` carries emphasis, links and primary actions. `--signal-2` carries a second
   data series or a secondary state. Nothing else gets a hue.
5. Define the full light palette on bare `:root`. Redefine only what changes in the dark
   block. Never give a color its only definition inside a media query.

### Type

```css
--font-head: "Source Serif 4", "Iowan Old Style", "Palatino Linotype", Palatino, serif;
--font-body: "IBM Plex Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
--font-mono: "IBM Plex Mono", "SF Mono", Menlo, Consolas, monospace;
```

Source Serif 4 sets every heading. IBM Plex Sans sets interface text, table cells,
captions and labels. IBM Plex Mono sets numerals in data tables, code, and captured
output. Long-form writeup pages may set body copy in Source Serif 4 at 1.05rem; app
interfaces always use IBM Plex Sans.

Monospace type is not the same thing as terminal window chrome. Mono is encouraged for
figures and data. The fake window frame around it is what is banned.

Scale, on a 1.25 ratio from a 16px base: 3.05rem, 2.44rem, 1.95rem, 1.56rem, 1.25rem,
1rem, 0.8rem. Prose measure caps at 68 characters. Body line height 1.6, headings 1.15.

### Geometry

- `border-radius: 0` on every element. A stylesheet containing any non-zero radius fails review.
- Borders are 1px solid `--rule` for separation and 1px solid `--edge` for controls.
  Emphasis uses 2px solid `--ink`.
- No `box-shadow` anywhere, including focus rings.
- Focus is a 2px solid `--signal` outline at 2px offset. Measured 6.52:1 light and
  6.00:1 dark, so it satisfies 2.4.7 and 1.4.11 without a shadow.
- Spacing on an 8px scale: 8, 16, 24, 40, 64, 96.

### Layout

One column for prose at 68ch. Reference material may use an asymmetric two-column at
roughly 2:1, never an even three. Figures run the full measure with the caption below in
IBM Plex Sans at 0.8rem in `--ink-2`, and the caption states what the figure shows and
what produced it.

Wide content (tables, code, diagrams) scrolls inside its own `overflow-x: auto` container.
The page body never scrolls horizontally. Every layout holds at 390px.

---

## 3. Component specifications

**Button.** Square. 1px `--edge` border, `--panel` background, `--ink` label. Primary
variant fills with `--signal` and labels in `--paper`. Hover changes background and border
value instantly with no `transition`. Focus draws the outline described above.

**Input.** Square, 1px `--edge`, `--panel` ground. Label sits above, never as placeholder
text alone. Error state changes the border to 2px `--signal` and adds text below stating
what is wrong.

**Table.** 1px `--rule` between rows, no vertical rules, no zebra striping, no rounded
container. Header row in IBM Plex Sans at 0.8rem, uppercase, letter-spaced 0.06em, with a
2px `--ink` bottom border. Numerals in IBM Plex Mono, right-aligned, tabular figures.

**Callout.** Full 1px `--edge` border on all four sides. No colored left stripe, no
background tint, no icon. A bold lead word carries the type.

**Code and captured output.** `<pre>` in `--panel` with a 1px `--rule` border, IBM Plex
Mono at 0.85rem, and a caption naming the command or process that produced it plus the
date. No window chrome, no traffic lights, no fake tab bar.

**Figure.** Image at `max-width: 100%`, 1px `--rule` border, caption below. Alt text
describes what the chart shows and its finding, not the phrase "chart" or "figure".

**Link.** `--signal`, underlined with a 1px offset. Hover changes to `--ink` instantly.
No underline animation.

---

## 4. Required elements

### Skeleton loaders

Required on any async state that can exceed roughly 200ms. Specification:

```css
.skeleton {
  background: var(--rule);   /* flat fill, never a gradient sweep */
  border-radius: 0;
}
@media (prefers-reduced-motion: no-preference) {
  .skeleton { animation: sk 1.6s ease-in-out infinite; }
  @keyframes sk { 0%,100% { opacity: 1 } 50% { opacity: 0.55 } }
}
```

The shimmer sweep found in most component libraries is a moving gradient and is therefore
banned twice over. A flat block with an opacity pulse carries the same meaning. The
skeleton mirrors the shape of the content it replaces so the layout does not shift when
real data arrives.

### Privacy policy

Required wherever user input is collected, stored or transmitted, including to a
third-party API. Lives at `/privacy/`. States, in plain sentences: what is collected, where
it goes, what third parties receive it, how long it is kept, and how to request deletion.
For a browser-only tool that uploads nothing, the policy says exactly that and names the
absence of a server.

### Terms of service

Required wherever there is a live backend, an account, or user-submitted content. Lives at
`/terms/`. Covers acceptable use, the absence of warranty, limitation of liability, and the
fact that a free service may change or stop.

Both pages carry a "last updated" date and are linked from the site footer.

### Real demonstrations

Every tool links to a working instance, or presents captured real output with a caption
naming the source and date. Where a demonstration cannot be captured, the page says so in
its own words rather than substituting a mockup. `epub-to-audiobook` already does this
correctly by using real CLI output and stating that the GUI could not be captured.

---

## 5. Copy rules

These extend `~/.claude/CLAUDE.md` and apply to READMEs, writeups, repo descriptions, UI
strings, alt text, captions and commit messages.

1. No em dash. The title-separator exception was removed on 2026-08-18. One exemption:
   an em dash that is functional code rather than prose, such as a character inside a
   regex class or a parser's terminator table, stays. Three exist in the portfolio, in
   the Mandarin segmenter and the Cantonese year-range parser. Mark them
   `ledger-allow: emdash` so the checker skips them and nobody strips them later.
2. No emoji.
3. No negative parallelism.
4. No checkmark glyphs as list markers.
5. No invented quotes, users, or numbers. Every figure traces to data in the repo.
6. Sentence case headings.
7. State what a thing does before stating why it matters. Cut any sentence that only
   restates the previous one.
8. Name limitations directly. A writeup that claims no weakness is not believable.

---

## 6. Review checklist

Run before publishing anything.

1. Stylesheet contains no `box-shadow`, no `backdrop-filter`, no non-zero `border-radius`,
   no `linear-gradient` or `radial-gradient` outside a data scale, and no `transition` on a
   hover or focus state.
2. Stylesheet contains no reference to Inter, Geist or Space Grotesk, including fallbacks.
3. No `#fff`, `#ffffff`, `#000` or `#000000` as a surface or text color.
4. No emoji and no em dash in any file that ships, including the README and the GitHub
   repo description.
5. Page holds at 390px with no horizontal body scroll.
6. Both themes render correctly, and every color token is defined on bare `:root` first.
7. Every focusable element shows the outline focus state.
8. Privacy and terms pages exist where section 4 requires them, and the footer links them.
9. Every figure has alt text describing the finding.
10. Every stated number is reproducible from code in the repo.

An automated checker for items 1 through 5 lives at
`_ai-projects-tooling/ledger/designcheck.py`. Run it as
`python3 designcheck.py <repo>`; it exits non-zero on any violation. Inside a git repo it
scans tracked files only, so gitignored material is never read or rewritten. That matters:
`leave-time-optimizer` keeps 17 superseded builds in a gitignored folder because they
contain old API keys.

Two false positives it is built to avoid, both found the hard way: a banned face is only
matched inside a `font-family` or `--font-*` declaration, so the word "interface" does not
trip it, and arrow characters are not treated as emoji. Items 6 through 10 need a person.

---

## 7. Known gaps, deferred

Recorded here rather than fixed, on the principle that a documented gap beats a fabricated
solution.

| Gap | Status |
|---|---|
| Real interactive demos for the four LoRA apps | Deferred. Each needs a hosted inference endpoint, which has a real running cost. Captured real output with dated captions is used in the interim. |
| `epub-to-audiobook` GUI screenshots | Blocked on a macOS screen-recording permission dialog that a person has to accept. Recorded in `PROJECTS_SUMMARY.md`. |
| Skeleton loaders in the three live apps | To be added during the app pass, after the static pages. |
| Dependabot alerts | Disabled on all 33 public repos. Unrelated to design, tracked in `PROJECTS_SUMMARY.md`. |

---

## 8. How this file is referenced

Every repo README carries one line under its title:

```markdown
Design and copy follow [these standards](https://github.com/lyhjeremy/lyhjeremy/blob/main/DESIGN_STANDARDS.md).
```

The overview-page builder in `_ai-projects-tooling/overview-pages/` holds the single copy of
the CSS implementing section 2. Editing a published `overview/index.html` directly is
overwritten on the next rebuild. Change the shell, then rebuild.
