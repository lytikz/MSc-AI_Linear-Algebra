# Learning Model Spec
**Project:** MSc-AI Linear Algebra
**Brand:** lytikz.ai
**Status:** Locked — any material change to lesson cadence, progression, or session structure must be reflected here before implementation
**Last updated:** 2026-03-09
**Authored with:** Claude Sonnet 4 and ChatGPT o3

---

## Overview

This document defines the pedagogical structure for every week of the
MSc-AI Linear Algebra programme. It is the single source of truth for
how lessons are designed, sequenced, and progressed. Any deviation
requires this document to be updated first.

---

## The Core Principle

Seeing a concept once is not learning it. Familiarity is not understanding.
Understanding is not fluency. This programme is structured to build all three
through deliberate repetition across varied contexts, with difficulty increasing
progressively across each week.

---

## The Weekly Arc

A standard week consists of three lesson sessions and one Q&A session. Each standard week centres on one anchor concept. That concept is revisited
across three lessons in different applied contexts, with each lesson becoming
slightly more technical, interpretive, or computationally demanding. A fourth
session is reserved for Q&A and consolidation, with no new material introduced.

Some topics naturally come in pairs — vectors and vector operations, eigenvalues
and eigenvectors. The rule is one anchor concept per week with room for one
tightly related supporting idea where needed. The anchor concept is never
diluted by rushing to the next topic.

---

## Session Structure

### Session 1 — Foundation

- Introduce the anchor concept
- Plain English explanation first, formal notation second
- Simple worked example in Python
- First applied context — accessible and clearly framed
- Goal: I understand what the concept is

### Session 2 — Variation

- Same anchor concept
- Different people analytics or business context
- Slightly harder mathematics or code
- More interpretation required
- Goal: I can recognise the same concept in a different setting

### Session 3 — Extension

- Same anchor concept pushed further
- More technically demanding or more realistic application
- Less scaffolded code — more independent thinking required
- Stronger AI or workforce analytics framing
- More open-ended challenge
- Goal: I can use the concept, not just repeat it

### Session 4 — Q&A and Consolidation

- No new material introduced
- Short conceptual questions
- Small calculation questions
- Interpretation questions
- One or two "why does this matter?" prompts
- Goal: I can explain, compute, and interpret the week's idea without being
  carried by a worked example

---

## The Four Progression Dimensions

Each of the three lessons must increase along all four dimensions:

| Dimension | Session 1 | Session 2 | Session 3 |
|---|---|---|---|
| Context complexity | Simple, clearly framed | More realistic scenario | Real-world analytical problem |
| Mathematical complexity | Basic manipulation | Slightly more demanding | More technical, less guided |
| Code complexity | Fully scaffolded | Partial scaffolding | Largely independent |
| Interpretation complexity | What is this? | What does this mean? | What should I conclude? |

Sessions 2 and 3 are not the same notebook with different numbers. Each must
add something — an extra dimension, a second vector to compare, a new
visualisation, a new interpretation question, or a less guided code task.
Repetition without progression is not this model.

---

## Notebook Structure Per Session

Sessions 1, 2, and 3 follow the full seven-cell notebook structure defined in Notebook_Design-Spec.md. Session 4 (Q&A) uses a lighter structure — no worked example code cell, no challenge code cell — just the questions and a reflection panel.

---

## Assessment Philosophy

Challenges and Q&A sessions are diagnostic, not performative. Their purpose
is to surface misunderstanding early, not to simulate formal testing. A question
that exposes a gap is more valuable than one that confirms what is already known.

---

## What This Is Not

This is not a lecture course where each week introduces a new topic and
moves on. It is a mastery-based programme where each concept is owned
before the next one is introduced. The cadence may feel slower than
expected in early weeks. That is intentional.

---

## Source Files

| File | Location | Purpose |
|---|---|---|
| `Learning-Model-Spec.md` | `05-Documentation\` | This document |
| `Curriculum-Map.md` | `05-Documentation\` | Full 12-week lesson map |
| `Notebook_Design-Spec.md` | `05-Documentation\` | Notebook design system |
| `Python_Code-Style-Guide.md` | `05-Documentation\` | Python alignment rules |
