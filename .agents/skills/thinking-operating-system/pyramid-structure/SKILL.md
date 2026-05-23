---
name: pyramid-structure
description: >
  Arrange ideas in a hierarchical pyramid that leads with the main message,
  supports it with logically grouped reasons, and underpins each reason with
  evidence or detail. Use this skill to craft clear arguments in reports,
  PRDs, presentations, and memos.
version: 1.0.0
tags:
  - communication
  - writing
  - structure
requires:
  - scqa-problem-definition
  - issue-tree-builder
---

# Pyramid Structure

## Overview

The Pyramid Principle (also known as Minto’s Pyramid) helps you present
information clearly by starting with a single key message and supporting it
with layers of reasons and evidence. This structure ensures that readers grasp
your conclusion immediately, then see the logic behind it. A good pyramid is
MECE at each level and maintains consistent vertical logic.

## When to Use

Use this skill when:

- Writing executive summaries, reports, or PRDs that must be understood quickly.
- Preparing presentation storylines (e.g. slide decks).
- Organising research findings into a narrative.
- Translating a complex issue tree into a persuasive argument.

## Process

### Step 1 – Define the main message

1. Summarise the core conclusion or recommendation in one sentence.
2. Ensure it is specific, action‑oriented, and relevant to the audience.
3. Test the main message: If the reader remembers only this, will they act
   appropriately?

### Step 2 – Identify top‑level supporting points

1. Determine 2–5 reasons that collectively support the main message.
2. Use MECE principles: reasons should not overlap and together should fully
   justify the main message.
3. Phrase each reason as a statement; avoid questions.

### Step 3 – Gather evidence for each point

1. Under each supporting reason, list data, facts, case studies, or analysis
   that substantiate it.
2. Distinguish between evidence and inference; label any assumptions.
3. Remove extraneous details that do not directly support the reason.

### Step 4 – Check vertical logic

1. Verify that each layer’s content truly supports the layer above it.
2. Use “Why? Therefore?” tests: reasons should answer “Why?” for the main
   message; evidence should answer “So what?” for each reason.
3. If the logic is weak, adjust the structure or gather stronger evidence.

### Step 5 – Order horizontally

1. Decide the best sequence for reasons: by importance, chronology, process,
   or some other logical order.
2. Ensure the flow is intuitive; you can preface the structure in one sentence
   (e.g. “There are three reasons…”).
3. Avoid jarring jumps between unrelated points.

## Output Format

Present the pyramid as an indented outline or bullet list:

```
Main Message: [Your conclusion]
├── Reason A: [Statement]
│   ├── Evidence A1: [Fact or data]
│   ├── Evidence A2: [Example or analysis]
│   └── …
├── Reason B: [Statement]
│   ├── Evidence B1
│   └── Evidence B2
└── Reason C: [Statement]
    ├── Evidence C1
    └── Evidence C2
```

Include a short introduction that restates the main message and previews the
supporting reasons (e.g. “Our recommendation is X for three reasons: …”).

## Example

**User Input:** “Explain why our company should build an AI‑native securities
app rather than adding a chat feature to the existing app.”

**Skill Output (abridged):**

```
Main Message: We should build an AI‑native securities app instead of adding a
chat feature because it better serves investors’ end‑to‑end tasks, creates a
competitive advantage, and ensures compliance.
├── Reason 1: Investors’ core job is completing investment tasks, not chatting.
│   ├── Evidence: Users research stocks, place trades, and review performance; chat
│       does not integrate seamlessly with these steps.
│   ├── Evidence: Surveys show users abandon chat when forced to switch to
│       transaction screens.
├── Reason 2: An AI‑native app can orchestrate data and tools contextually.
│   ├── Evidence: AI can pre‑fill orders based on portfolio data and market
│       conditions, reducing errors.
│   ├── Evidence: Competitors using chat overlays lack deep integration with
│       account information.
└── Reason 3: A dedicated architecture improves compliance and auditability.
    ├── Evidence: Regulations require transparent disclosure of recommendations.
    ├── Evidence: An integrated design allows for logging all AI suggestions and
        user actions.
```

## Notes

- The pyramid should be concise; do not exceed five top‑level reasons.
- Use `critic-reviewer` to check the strength of your vertical and horizontal
  logic.
- This skill is the backbone of many other skills in the thinking‑operating‑system.
