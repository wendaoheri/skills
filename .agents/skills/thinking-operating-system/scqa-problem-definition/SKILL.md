---
name: scqa-problem-definition
description: >
  Use the Situation–Complication–Question–Answer (SCQA) framework to clearly
  define a problem before proposing solutions. This skill helps you summarise
  context, pinpoint the trigger, articulate the key question, and provide a
  concise answer or recommendation.
version: 1.0.0
tags:
  - problem-definition
  - communication
  - writing
requires:
  - pyramid-structure
---

# SCQA – Problem Definition

## Overview

SCQA is a structured narrative framework that clarifies the situation and
highlights why the status quo is no longer sufficient. By explicitly stating
the **Situation**, describing the **Complication** or change, posing the
resulting **Question**, and summarising the **Answer**, you ensure that
everyone shares the same understanding of the problem before diving into
solutions.

## When to Use

Use this skill when you need to open a report, PRD, or presentation by
clarifying the problem. It is especially helpful:

- At the start of any document where context matters (e.g. executive summary).
- When stakeholders disagree on what the real issue is.
- To frame a new initiative or proposal.
- When converting raw research or brainstorming into a focused problem
  statement.

## Process

Follow these steps to build an SCQA narrative:

### Step 1 – Situation

1. Summarise the current state of affairs relevant to the topic.
2. Include factual background information; avoid judgmental language.
3. Keep it concise (2–3 sentences).

### Step 2 – Complication

1. Identify what has changed or what new challenge has arisen.
2. Explain why the existing approach no longer works or is suboptimal.
3. Highlight the tension or opportunity that demands action.

### Step 3 – Question

1. Frame the single most important question that must be answered.
2. Make it specific and actionable (avoid vague questions).
3. Ensure it logically follows from the complication.

### Step 4 – Answer

1. Provide a concise statement that resolves the question.
2. This should be your thesis or recommendation; more detail can follow later.
3. It should directly address the complication and be testable.

## Output Format

Structure your response into four labelled sections:

- **Situation:** (2–3 sentences summarising the current context)
- **Complication:** (1–2 sentences explaining the change or conflict)
- **Question:** (One clear, actionable question)
- **Answer:** (One sentence summarising your proposal or thesis)

Optionally, include a short commentary after the Answer to preview the
supporting arguments that will follow.

## Example

**User Input:** “We are considering launching a new AI‑powered research tool
for retail investors.”

**Skill Output:**

- **Situation:** Over the past two years, retail investors using our platform
  have relied on manual research via forums and third‑party sites to make
  investment decisions.
- **Complication:** A surge in market volatility and the proliferation of
  complex products have made it difficult for ordinary investors to sift
  through data quickly, leading to decision fatigue and missed opportunities.
- **Question:** How can we help retail investors perform accurate, timely
  research within our platform so they can make confident investment decisions?
- **Answer:** We should develop an AI‑powered research assistant that
  aggregates market data, personalises insights to the user’s portfolio, and
  provides clear risk disclosures.

## Notes

- SCQA works best when combined with `issue-tree-builder` to break down the
  resulting question into sub‑questions.
- Keep the situation neutral; the complication introduces the tension.
- The question should not implicitly contain the answer.
