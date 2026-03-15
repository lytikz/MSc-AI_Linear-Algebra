# Session Handover
**Project:** MSc-AI Linear Algebra
**Brand:** lytikz.ai
**Handover from:** Session 3 (2026-03-09)
**Picks up at:** Week 2, Lesson 1

---

## Where We Are

Week 1 is complete. All four notebooks are built, reviewed jointly with
ChatGPT o3, iterated, and approved. The project structure is clean and
committed to Git.

---

## What Was Built This Session

| File | Location | Status |
|---|---|---|
| `Week-01_Lesson-01_Scalars-and-Vectors.ipynb` | `01-Code\Week-01\` | Complete — code rewritten to locked style |
| `Week-01_Lesson-02_Vectors-in-a-Different-Light.ipynb` | `01-Code\Week-01\` | Complete |
| `Week-01_Lesson-03_Vectors-in-the-Wild.ipynb` | `01-Code\Week-01\` | Complete |
| `Week-01_QandA_Scalars-Vectors-and-Comparison.ipynb` | `01-Code\Week-01\` | Complete |
| `Lesson_Template.ipynb` | `01-Code\` | Complete |
| `lytikz_Lesson-Stylesheet.css` | `02-Design\` | Locked |
| `Notebook_Design-Spec.md` | `05-Documentation\` | Locked |
| `Python_Code-Style-Guide.md` | `05-Documentation\` | Locked — Rule 9 added |
| `Learning-Model-Spec.md` | `05-Documentation\` | Locked |
| `Curriculum-Map.md` | `05-Documentation\` | Draft — pending sign off |

---

## Locked Decisions

### Code style
All Python code cells follow these rules without exception:

- Colour constants at the top of every plotting cell, in this exact form
  and order:

```python
BG    = '#0a0a0c'
TEXT  = '#e8e4de'
SUB   = '#b5b0a8'
MUTED = '#6a6560'
GRID  = '#2a2a28'
AXIS  = '#3a3a38'
GRN   = '#c4f042'
AMB   = '#f0a830'
RED   = '#e8453c'
```

- Imports on separate lines, aligned on `as` per the style guide
- Assignments aligned within related blocks
- f-string labels aligned within print blocks
- Keyword arguments one per line, `=` aligned within each call
- `set_aspect('equal', adjustable='box')` on all 2D vector plots
- No `mpl.rcParams` font setting until a shared theme cell is in place
- Challenge cells are fully self-contained (Rule 9 in the style guide)
- Shape validation and zero-vector guard in every challenge cell
- Helper functions kept untyped at Week 1 level

### Cosine similarity helper — standard form for Week 2 onwards:
```python
def cosine_similarity(a, b):
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))
```

### Variable naming
- `v` for simple geometric vectors in maths examples
- Descriptive names (`employee_vector`, `role`, `dept_a`) for applied examples

### Notebook structure
- Full seven-cell structure for Lessons 1, 2, 3
- Five-cell structure for Q&A sessions (no worked example code cell,
  no challenge code cell)

---

## Week 1 Content Summary

**Anchor concept:** Scalars and vectors
**Supporting idea:** Vector magnitude

| Session | Title | Key idea introduced |
|---|---|---|
| L1 | Scalars, Vectors, and Two Ways of Seeing Them | What a vector is, magnitude, NumPy arrays |
| L2 | Vectors in a Different Light | Dot product as a first similarity measure, 2D comparison |
| L3 | Vectors in the Wild | Cosine similarity, 12D absence pattern vectors, line chart |
| Q&A | Scalars, Vectors, and Comparison | Full consolidation across all four question types |

---

## Week 2 — What Comes Next

**Anchor concept:** Vector operations and comparison
**Supporting idea:** Magnitude, distance, and normalisation

| Session | Title | Context |
|---|---|---|
| L1 | What You Can Do With Vectors | Basic operations on a single employee vector |
| L2 | Comparing Vectors | Distance between two employee profiles |
| L3 | Weighted Profiles and Normalisation | Scoring systems and scale-aware comparison |
| Q&A | Week 2 Consolidation | Operations, magnitude, distance, normalisation |

The process for Week 2 is the same as Week 1:
1. Draft the full lesson content for review
2. Present the code separately before building the notebook
3. Review with ChatGPT
4. Incorporate agreed changes
5. Build the notebook
6. Commit to Git

---

## Pinned Documents

All four spec documents should be pinned to the Claude project:

- `Notebook_Design-Spec.md`
- `Python_Code-Style-Guide.md`
- `Learning-Model-Spec.md`
- `Curriculum-Map.md`

---

## Communication Rules (carry forward always)

- UK English throughout
- First person voice
- No en or em dashes used as separators — ever
- Prose over bullet points
- Token usage reported at the end of every response
- Code follows the locked Python Code Style Guide
- No speculative folder or file creation
- One change at a time — present before implementing
