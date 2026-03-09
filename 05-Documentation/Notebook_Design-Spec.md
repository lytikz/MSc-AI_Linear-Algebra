# Notebook Design Spec
**Project:** MSc-AI Linear Algebra
**Brand:** lytikz.ai
**Design:** Concept A — Refined Warm
**Status:** Locked
**Last updated:** 2026-03-09

---

## Overview

Every lesson notebook in this project follows the Concept A — Refined Warm design.
This document is the single source of truth for the design system. Any deviation
requires this document to be updated first.

---

## Fonts

| Role | Font | Weights |
|---|---|---|
| Headings | Sora | 600, 700, 800 |
| Body, code, labels | JetBrains Mono | 300, 400, 500, 700 |

No other fonts are permitted.

---

## Colour Palette

| Role | Value |
|---|---|
| Page background | `#0a0a0c` |
| Panel background | `#111110` (opaque — never transparent) |
| Green | `#c4f042` |
| Amber | `#f0a830` |
| Red | `#e8453c` |
| Heading text | `#e8e4de` |
| Body text | `#c5c0b8` |
| Sub text | `#b5b0a8` |
| Muted text | `#a09a92` |
| Muted label | `rgba(228,224,218,0.22)` |

---

## Panel Structure

Every content block is a `.panel` element with:

- `border-radius: 6px`
- Opaque `#111110` background
- `box-shadow: inset 0 0 0 1px rgba(255,255,255,0.07)` frame
- No `border-top` on the same element as the frame

---

## Accent Strips

Accent strips are real child `<div>` elements placed as the first child inside a
panel. Never use `border-top`, `::before`, or `::after` for accent lines.

| Accent colour | Panels |
|---|---|
| Green `#c4f042` | Title, Concept, Worked Example |
| Amber `#f0a830` | AI Connection, Workforce Analytics, Challenge |
| None | Orientation/Recap, Reflection, Next Lesson |

---

## Section Labels

Each panel opens with a `.sec-row` containing the section label and a full-width
hairline rule. Labels are small-caps uppercase, coloured to match the panel accent.

| Class | Colour | Used for |
|---|---|---|
| `.sec-label.green` | `rgba(196,240,66,0.55)` | Green panels |
| `.sec-label.amber` | `rgba(240,168,48,0.55)` | Amber panels |
| `.sec-label.muted` | `rgba(228,224,218,0.22)` | No-accent panels |

---

## Nested Cards

Three card types sit inside panels as supporting content.

| Type | Class | Left border | Background |
|---|---|---|---|
| Perspective | `.inner-card` | `rgba(240,168,48,0.35)` | `rgba(240,168,48,0.03)` |
| Professional Note | `.inner-note` | `rgba(232,69,60,0.35)` | `rgba(232,69,60,0.025)` |
| Formal Notation | `.inner-formal` | `rgba(196,240,66,0.20)` | `rgba(196,240,66,0.02)` |

---

## Key Terms

Use class `term` — not `kt`. DataSpell injects underlines on the `kt` class via
its own editor styling. An aggressive selector stack in the stylesheet suppresses
this for `term`.

```html
<span class="term">vector</span>
```

---

## Notebook Cell Structure

Every lesson notebook uses exactly seven cells in this order:

| Cell | Type | Content |
|---|---|---|
| 1 | Markdown | Stylesheet only — full contents of `lytikz_Lesson-Stylesheet.css` inside `<style>` tags |
| 2 | Markdown | Header strip — sacrificial cell that absorbs DataSpell's first-cell clip |
| 3 | Markdown | Full lesson content — Title, Recap/Orientation, Concept, AI Connection, Workforce Analytics |
| 4 | Code | Worked example Python |
| 5 | Markdown | Challenge panel |
| 6 | Code | Blank challenge starter code |
| 7 | Markdown | Reflection and Next Lesson teaser |

---

## DataSpell Rendering Rules

These rules were established through trial and error. Violating any of them causes
rendering failures.

1. All HTML in markdown cells must be flush left — zero indentation on every line.
   Four or more leading spaces trigger Markdown's code block parser.

2. Every styled markdown cell must be pure HTML from top to bottom. No Markdown
   syntax inside styled cells. No loose text. No fenced code blocks.

3. All prose must be wrapped in explicit `<p>` tags.

4. Accent strips must be real child `<div>` elements — never `::before` or
   `::after` pseudo-elements, which DataSpell strips silently.

5. Do not use `border-top` on the same element as the panel frame border. It
   produces visible corner seams on rounded boxes. Use the accent strip div.

6. Use `.term` not `.kt` for key term highlighting.

7. Do not use multi-byte Unicode emojis anywhere in markdown cells. They cause
   the entire cell to fail to render.

8. The first visible rendered cell is clipped by DataSpell at the top-left corner.
   Cell 2 (the header strip) is deliberately expendable — it absorbs this clip.

9. Panel backgrounds must be opaque (`#111110`) — not semi-transparent.
   Transparency causes colour bleed in layered designs.

10. Left-align panels — do not centre with `margin: 0 auto`. Code cells are
    full-width and left-aligned by the IDE; panels must match.

11. `inset box-shadow` is used for the panel frame (not a border) to avoid
    mixed border-thickness corner artefacts on rounded boxes.

12. Do not mix `border-top` with `border` on the same rounded element.

13. Increasing margin between panels (20px) visually separates them from
    DataSpell's own inter-cell separator lines.

---

## Header Strip Template

```html
<div class="header-strip">
<span class="brand">lytikz.ai</span>
<span class="sep">·</span>
<span class="meta">MSc AI Preparation</span>
<span class="sep">·</span>
<span class="meta">Linear Algebra</span>
<span class="sep">·</span>
<span class="meta">12 Week Programme</span>
</div>
```

---

## Source Files

| File | Location | Purpose |
|---|---|---|
| `lytikz_Lesson-Stylesheet.css` | `02-Design/Brand-Assets/` | Master stylesheet — copy into Cell 1 of every notebook |
| `Lesson_Template.ipynb` | `01-Code/` | Blank template notebook with all seven cells pre-built |
| `Notebook_Design-Spec.md` | `05-Documentation/Project-Specs/` | This document |
| `Python_Code-Style-Guide.md` | `05-Documentation/Project-Specs/` | Python visual alignment rules |
