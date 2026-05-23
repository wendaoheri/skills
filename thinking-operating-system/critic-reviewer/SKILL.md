---
name: critic-reviewer
description: >
  Evaluate arguments, reports, or proposed solutions by identifying logical
  flaws, unsupported assumptions, missing evidence, and alternative viewpoints.
  Use this skill to ensure outputs are robust, balanced, and tailored to the
  audience before finalising decisions or presentations.
version: 1.0.0
tags:
  - critique
  - quality-assurance
  - analysis
requires:
  - pyramid-structure
---

# Critic Reviewer

## Overview

The critic reviewer acts as an impartial editor that scrutinises the logic and
evidence behind a proposed argument or solution. It tests whether conclusions
are over‑stated, whether evidence truly supports claims, whether assumptions
are explicit and valid, and whether important counterarguments have been
considered. This skill helps avoid groupthink and self‑delusion.

## When to Use

Use this skill:

- After crafting a pyramid structure or decision matrix, to catch weak links.
- When reviewing a draft PRD, strategy paper, or presentation.
- Before presenting recommendations to senior stakeholders.
- To challenge AI‑generated outputs that may hallucinate or gloss over gaps.

## Process

### Step 1 – Summarise the argument

1. Identify the main conclusion or recommendation.
2. List the primary supporting reasons and evidence used.

### Step 2 – Check conclusion appropriateness

1. Is the conclusion proportionate to the evidence provided?
2. Are there any leaps of logic (e.g. assuming causation from correlation)?
3. Is the scope of the conclusion clearly defined (avoid over‑generalisation)?

### Step 3 – Evaluate supporting reasons

1. For each reason, assess whether the evidence directly supports it.
2. Identify any missing links or additional evidence needed.
3. Check if any assumptions are unstated; make them explicit.

### Step 4 – Examine evidence quality

1. Is the evidence factual, or is it opinion presented as fact?
2. Are data sources credible and up to date?
3. Are there contrary data points or examples that were ignored?

### Step 5 – Identify alternative perspectives

1. Note any plausible counterarguments or different viewpoints.
2. Consider whether the audience might have different incentives or concerns.
3. Assess whether the argument addresses or pre‑empts these perspectives.

### Step 6 – Check audience relevance

1. Is the argument tailored to the decision maker’s needs and context?
2. Are there unnecessary details or jargon that could obscure the message?

### Step 7 – Provide recommendations

1. Summarise the main issues found (logical flaws, missing evidence, etc.).
2. Suggest concrete improvements: gather data, rephrase conclusions, add
   counterarguments, adjust scope, simplify language.
3. If the argument is sound, provide a brief validation and note any minor
   enhancements.

## Output Format

Your review should include:

1. **Summary of Argument** – Concise restatement of the main conclusion and
   supporting reasons.
2. **Issues Identified** – Bullet list of problems grouped by category
   (e.g. Logic, Evidence, Assumptions, Counterarguments, Audience).
3. **Recommended Actions** – Specific steps to address each issue.
4. **Overall Assessment** – A short paragraph rating the argument’s strength
   (e.g. Strong, Adequate, Weak) and suitability for the intended audience.

## Example

**Input:** A draft argument advocating for an AI chat feature instead of a
task‑oriented app.

**Critic Output (abridged):**

1. **Summary of Argument:** The proposal claims that adding a chat box will
   differentiate our app quickly because competitors have one and users enjoy
   conversation.
2. **Issues Identified:**
   - *Logic:* Assumes that competitor adoption implies success; no evidence of
     user satisfaction or retention impact.  
   - *Evidence:* No data on user preference for chat vs. integrated workflows.
   - *Assumptions:* Assumes adding chat is low effort and can be bolted on
     without technical debt.  
   - *Counterarguments:* Ignores regulatory complexities of giving advice via
     chat; fails to address alternative of embedding AI into existing flows.
3. **Recommended Actions:** Conduct user research on preferred interaction
   modes; benchmark competitor outcomes; clarify technical integration costs;
   address compliance requirements; consider hybrid designs.
4. **Overall Assessment:** Weak – the conclusion is not supported by evidence
   and overlooks key constraints; significant revision needed.

## Notes

- The critic reviewer should maintain a neutral tone; avoid dismissive language.
- Use this skill iteratively throughout development, not just at the end.
- Encourage authors to pre‑empt criticism by using `first-principles` and
  `pyramid-structure` beforehand.
