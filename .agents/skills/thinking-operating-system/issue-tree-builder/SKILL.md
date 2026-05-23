---
name: issue-tree-builder
description: >
  Decompose complex problems into a hierarchy of mutually exclusive,
  collectively exhaustive (MECE) questions. Use this skill to plan research,
  allocate analysis tasks, and ensure you have covered all relevant aspects of
  a problem before deciding.
version: 1.0.0
tags:
  - problem-decomposition
  - analysis
  - research
requires:
  - scqa-problem-definition
---

# Issue Tree Builder

## Overview

An **issue tree** breaks a high‑level question into smaller questions until each
branch is specific enough to be analysed or acted upon. It helps teams avoid
missing critical factors and reveals the structure of a problem. Each level of
the tree must be MECE – sub‑issues should not overlap and together they
should cover the whole of the parent issue.

## When to Use

Use this skill when:

- You have defined a high‑level question using SCQA or first‑principles analysis.
- You need to structure research or analysis for a complex project.
- Multiple stakeholders or teams will work in parallel on different parts of the
  problem.
- You want to surface implicit assumptions by making sub‑issues explicit.

## Process

### Step 1 – Define the root question

1. Start with a single, well‑formed question (ideally produced by
   `scqa-problem-definition` or `first-principles`).
2. Ensure the question is open‑ended and not loaded with assumptions.

### Step 2 – Generate first‑level sub‑questions

1. Brainstorm major factors that determine the answer to the root question.
2. Group these factors into 3–5 categories that are mutually exclusive and
   collectively exhaustive (MECE).
3. For each category, formulate a sub‑question that, if answered, helps answer
   the root question.

### Step 3 – Expand branches

1. For each sub‑question, repeat the process: identify sub‑factors and break
   them into MECE sub‑questions.
2. Continue decomposing until each leaf node is specific enough to be researched,
   analysed, or assigned as a task.
3. Avoid going more than 3–4 levels deep; combine similar branches where
   appropriate.

### Step 4 – Validate MECE criteria

1. For each level, check that sub‑questions do not overlap (no double counting).
2. Ensure that if all sub‑questions were answered, they would collectively answer
   the parent question.
3. If overlap or gaps exist, reorganise or add missing branches.

### Step 5 – Assign or plan analysis

1. For each leaf question, decide on the method to answer it (e.g. data analysis,
   user interviews, technical investigation).
2. Assign ownership and deadlines for each branch if working in a team.

## Output Format

Return a hierarchical outline of the issue tree. Use indented bullet points or
arrow characters to show levels. For example:

```
Root Question: How can we increase adoption of our AI research tool?
├── Target Users
│   ├── Who are the primary user segments?
│   ├── What are their unmet needs?
│   └── How do they currently perform research?
├── Value Proposition
│   ├── What unique benefits does our tool offer?
│   ├── How does it compare to competitors?
│   └── How do we communicate its value?
└── Go‑to‑Market Strategy
    ├── Which channels reach our target users?
    ├── What messaging resonates with them?
    └── What partnerships can accelerate adoption?
```

Include notes on any assumptions and highlight if additional data is needed.

## Example

**User Input:** “How should we prioritise features for our next release?”

**Skill Output (abridged):**

```
Root Question: How should we prioritise features for the next release?
├── User Impact
│   ├── Which features address critical user jobs?
│   ├── What evidence do we have of user demand?
│   └── How will each feature improve user retention?
├── Business Value
│   ├── Which features drive revenue or cost savings?
│   ├── Are there regulatory or contractual deadlines?
│   └── How do features support our strategic goals?
└── Effort & Risk
    ├── What is the estimated development effort?
    ├── What are the technical risks or dependencies?
    └── What is the opportunity cost of delaying other work?
```

## Notes

- Keep sub‑questions at each level conceptually similar (e.g. all about users, all
  about value) to maintain MECE.
- Combine this skill with `decision-matrix` to evaluate the resulting options.
- Document sources and evidence when answering leaf questions.
