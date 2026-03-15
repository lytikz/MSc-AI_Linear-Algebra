# Session Handover
**Project:** MSc-AI Linear Algebra
**Brand:** lytikz.ai
**Handover from:** Week 2 session (2026-03-12)
**Picks up at:** Week 3, Lesson 1

---

## Where We Are

Week 2 is complete. All four notebooks are built, reviewed jointly with
ChatGPT o3, iterated, and approved. The project structure is clean and
ready for Week 3.

---

## What Was Built This Session

| File | Location | Status |
|---|---|---|
| `Week-02_Lesson-01_What-You-Can-Do-With-Vectors.ipynb` | `01-Code\Week-02\` | Complete |
| `Week-02_Lesson-02_Comparing-Vectors.ipynb` | `01-Code\Week-02\` | Complete |
| `Week-02_Lesson-03_Weighted-Profiles-and-Normalisation.ipynb` | `01-Code\Week-02\` | Complete |
| `Week-02_QandA_Operations-Distance-and-Normalisation.ipynb` | `01-Code\Week-02\` | Complete |

---

## Key Lessons Learned This Session

### Notebook assembly — read a completed notebook first
Before building any notebook, read a completed one from the same project.
The spec documents describe the design system. The built notebooks show
exactly how it is implemented. These are not the same thing. The Week 02
Lesson 01 first build had seven structural deviations that required a full
rebuild, all of which would have been caught by reading Week 01 Lesson 01
before starting. This rule is non-negotiable going forward.

### Specific structural patterns to carry forward
- Cell 1 stylesheet: comments stripped for lesson notebooks, full comments
  retained for Q&A notebooks — match the Week 01 pattern exactly
- All content divs in Cells 3, 5, and 7 wrapped in `<div class="lesson-shell">`
- Section labels and rules use `<div>` not `<span>` or `<hr>`
- Lesson title uses `<div class="lesson-title">` not `<h1>`
- Inner card labels use `<div class="inner-*-label">` not `<p>`
- No sec-row inside the title panel — only `.wk`, `.lesson-title`, `.title-rule`

---

## Locked Decisions (carried forward from Week 2)

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

- Imports on separate lines, aligned on `as`
- Assignments aligned within related blocks
- f-string labels aligned within print blocks
- Keyword arguments one per line, `=` aligned within each call
- `set_aspect('equal', adjustable='box')` on all 2D vector plots
- No `mpl.rcParams` font setting until a shared theme cell is in place
- Challenge cells fully self-contained (Rule 9 in the style guide)
- Shape validation and zero-vector guard in every challenge cell
- Helper functions kept untyped at Week 2 level
- `dtype = float` on all NumPy arrays

### Cosine similarity helper — standard form:
```python
def cosine_similarity(a, b):
    return np.dot(a, b) / (np.linalg.norm(a) * np.linalg.norm(b))
```

### Min-max normalisation helper — standard form:
```python
def minmax_normalise(v, v_min, v_max):
    return (v - v_min) / (v_max - v_min)
```

### Variable naming
- `v` for simple geometric vectors in maths examples
- Descriptive names (`employee_a`, `candidate_p`, `norm_a`) for applied examples
- `calc_a`, `calc_b` for Q&A scratch cell vectors that would otherwise
  collide with other named variables in the same cell

### Notebook structure
- Full seven-cell structure for Lessons 1, 2, 3
- Five-cell structure for Q&A sessions

---

## Week 2 Content Summary

**Anchor concept:** Vector operations and comparison
**Supporting idea:** Magnitude, distance, and normalisation

| Session | Title | Key idea introduced |
|---|---|---|
| L1 | What You Can Do With Vectors | Scalar multiplication, vector addition, vector subtraction, linear combinations |
| L2 | Comparing Vectors | Euclidean distance as magnitude of difference vector, distance vs cosine similarity |
| L3 | Weighted Profiles and Normalisation | Min-max normalisation, unit vector normalisation, element-wise weighting, composite scores |
| Q&A | Operations, Distance, and Normalisation | Full consolidation across all four question types |

---

## Week 3 — What Comes Next

**Anchor concept:** What a matrix is and how to operate on it
**Supporting idea:** Transpose

| Session | Title | Context |
|---|---|---|
| L1 | From Vectors to Matrices | A workforce dataset as a matrix |
| L2 | Operating on Matrices | Addition, scalar multiplication, headcount tables |
| L3 | Reshaping Data with Transpose | Transposing workforce data, practical applications |
| Q&A | Week 3 Consolidation | Matrix structure, operations, transpose, shape |

The process for Week 3 is the same as Weeks 1 and 2:
1. Read a completed notebook before building
2. Draft the full lesson content for review
3. Present the code separately before building the notebook
4. Review with ChatGPT
5. Incorporate agreed changes
6. Build the notebook
7. Commit to Git

---

## Pinned Documents

- `Notebook_Design-Spec.md`
- `Python_Code-Style-Guide.md`
- `Learning-Model-Spec.md`
- `Curriculum-Map.md`
- `Handover_Week-03-Start.md`

---

## Communication Rules (carry forward always)

- UK English throughout
- First person voice
- No en or em dashes used as separators — ever
- Prose over bullet points
- Token usage reported at the end of every response
- Code follows the locked Python Code Style Guide
- No speculative folder or file creation
- Read a completed notebook before building any new one
- One change at a time — present before implementing
