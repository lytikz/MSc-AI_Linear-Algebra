# Python Code Style Guide
**Project:** MSc-AI Linear Algebra
**Brand:** lytikz.ai
**Status:** Locked
**Last updated:** 2026-03-09

---

## Overview

This guide defines the visual alignment style for all Python code in this project.
It is a deliberate house style for a solo, educational, single-author notebook
environment where readability for a human reader takes priority over PEP 8 edit-time
convenience. Where this guide conflicts with PEP 8, this guide wins — knowingly and
with good reason.

---

## Rule 1 — Section Dividers

Every logical section of code opens with a box-drawing divider line. The character
is U+2500 (─), not a hyphen.

```python
# ── Section Label ─────────────────────────────────────────────────────────────
```

**Live Templates (DataSpell):**

| Abbreviation | Expands to |
|---|---|
| `#sec` | `# ── $END$ ────────────────────────────────────────────────────────────────` |
| `#todo` | `# ── TODO: $END$ ───────────────────────────────────────────────────────────` |
| `#note` | `# ── NOTE: $END$ ───────────────────────────────────────────────────────────` |

---

## Rule 2 — Import Alignment

Within a block of related imports, align the `as` keyword.
The longest module name sets the column.

```python
# Correct
import numpy             as np
import matplotlib.pyplot as plt

# Incorrect
import numpy as np
import matplotlib.pyplot as plt
```

---

## Rule 3 — Assignment Alignment

Within a block of related assignments, pad variable names with spaces so every
`=` sits in the same column. The longest variable name sets the column.

```python
# Correct
age              = 34
engagement_score = 72

# Incorrect
age = 34
engagement_score = 72
```

Solitary assignments (not part of a related block) do not need padding.

---

## Rule 4 — f-string Label Alignment

Within a block of related print or display statements, pad the label text inside
the f-string with spaces so that the opening `{` aligns vertically across all
lines. The longest label in the block sets the column.

```python
# Correct
print(f"Employee vector:      {employee_vector}")
print(f"Number of dimensions: {employee_vector.shape[0]}")
print(f"Raw magnitude:        {np.linalg.norm(employee_vector):.4f}")

# Incorrect
print(f"Employee vector: {employee_vector}")
print(f"Number of dimensions: {employee_vector.shape[0]}")
print(f"Raw magnitude: {np.linalg.norm(employee_vector):.4f}")
```

**Edge case — label contains `=`:**
Where the label itself uses `=` as part of its meaning, align the `=` across
the block rather than the `{`. The `{` follows naturally.

```python
print(f"\nGeometric vector v = {v}")
print(f"Magnitude |v|      = {np.linalg.norm(v):.4f}")
```

---

## Rule 5 — Keyword Argument Alignment

In any multi-line function call, place one keyword argument per line and align
the `=` to the longest keyword name in that specific call.
Each call is its own independent alignment block.

```python
# Correct
ax.quiver(
    0, 0, v[0], v[1],
    angles      = 'xy',
    scale_units = 'xy',
    scale       = 1,
    color       = '#c4f042',
    width       = 0.015
)

ax.set_title(
    "Vector v = [3, 2] as an arrow in 2D space",
    color    = '#e8e4de',
    fontsize = 11,
    pad      = 14
)

# Incorrect
ax.quiver(0, 0, v[0], v[1], angles='xy', scale_units='xy', scale=1)
```

---

## Rule 6 — Inline Keyword Arguments

For calls that stay on a single line, keyword arguments use spaces around `=`
consistently with the multi-line style.

```python
# Correct
ax.axhline(0, color = '#3a3a38', linewidth = 0.8)
ax.set_xlabel("x", color = '#b5b0a8')

# Incorrect
ax.axhline(0, color='#3a3a38', linewidth=0.8)
ax.set_xlabel("x", color='#b5b0a8')
```

---

## Rule 7 — Subordinate Print Lines

An indented note or clarification printed below a related output line uses two
leading spaces inside the f-string. This visually subordinates it beneath the
line above in the console output.

```python
print(f"Raw magnitude:        {np.linalg.norm(employee_vector):.4f}")
print(f"  (note: dominated by engagement_score at scale 0-100)")
```

The two spaces are intentional content inside the string — not code indentation.

---

## Rule 8 — Block Grouping

Related statements form a block. Blocks are separated by a single blank line.
A section divider line (Rule 1) separates major sections.

```python
# ── Scalars ───────────────────────────────────────────────────────────────────
age              = 34
engagement_score = 72

print(f"Age (scalar):              {age}")
print(f"Engagement score (scalar): {engagement_score}")

# ── Employee profile as a vector ──────────────────────────────────────────────
employee_vector = np.array([34, 5, 72, 4])
```

---

## Rule 9 — Challenge Cells Are Self-Contained

Every challenge code cell (Cell 6) must be fully self-contained and safe to
rerun independently of the worked example cell. This means:

- Re-import all packages needed
- Re-define any vectors or variables referenced from the worked example
- Do not assume the kernel has retained state from Cell 4

This rule ensures the challenge cell can be reset and retried without
requiring the full notebook to be re-executed from the top.

---

## Relationship to PEP 8

This guide intentionally departs from PEP 8 in the following areas:

| Area | PEP 8 | This guide | Reason |
|---|---|---|---|
| Assignment alignment | Discouraged | Required within related blocks | Readability in educational notebooks |
| Spaces around `=` in kwargs | Discouraged | Required | Consistency with alignment style |
| Import alignment | No rule | Align on `as` | Visual clarity |

All other PEP 8 rules apply. This guide only overrides the above.
