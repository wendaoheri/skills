---
name: first-principles
description: >
  Challenge default assumptions and define problems from basic facts before solving
  them. Use this skill when you suspect the problem itself is framed incorrectly,
  stakeholders are relying on hidden assumptions or industry conventions, or when
  you need to break free from path‑dependence to find novel solutions.
version: 1.0.0
tags:
  - problem-definition
  - innovation
  - research
---

# First‑Principles Analysis

## Overview

The **First‑Principles Analysis** skill helps you rethink a problem from the
ground up. Instead of accepting conventional solutions or
industry defaults, you identify the underlying facts, separate assumptions,
and reframe the question. This often reveals that defining the problem is
more important than jumping straight into a solution.

## When to Use

Use this skill when:

- You suspect the current problem definition is flawed or too narrow.
- The team is stuck in “we’ve always done it this way” thinking.
- You need to innovate beyond incremental improvements.
- A stakeholder asks for an existing solution (e.g. “add a chat box”) but you
  want to ensure the real need is addressed.
- You are designing AI or software systems where requirements are ambiguous.

## Process

Follow these steps to perform a first‑principles analysis. Each step should
produce explicit lists of facts, assumptions, and conclusions to avoid
hand‑waving.

### Step 1 – Identify mainstream solutions and default assumptions

1. Summarise the conventional way the problem is currently solved.
2. List the explicit and implicit assumptions behind this conventional approach.
3. Note which assumptions are well‑supported and which are merely industry
   habits or constraints born of legacy technology.

### Step 2 – Distinguish facts from assumptions

1. For each assumption, ask: “Is this a verifiable fact, or just an inference?”
2. Create two lists:
   - **Facts** – statements that can be observed or verified (e.g. user behaviour,
     regulations, physical laws, resource constraints).
   - **Assumptions** – beliefs, preferences, or patterns that could change.
3. Identify which assumptions could be relaxed or eliminated.

### Step 3 – Identify non‑negotiable constraints

1. List any hard constraints that cannot be changed (e.g. legal requirements,
   safety standards, immutable physical limitations).
2. Separate these from soft constraints (e.g. budget limits, legacy systems),
   which might be negotiable.
3. Make sure not to confuse soft constraints with facts; soft constraints often
   drive inertia but can be overcome.

### Step 4 – Reframe the problem using basic facts

1. Using only the facts and non‑negotiable constraints, restate the core
   question. Focus on the underlying job or outcome rather than the existing
   solution (“How can we help users make investment decisions?” vs.
   “Where should we place the AI chat?”).
2. Write the new problem statement in plain language. It should be independent
   of a specific solution.
3. Check that the restated problem aligns with stakeholder goals.

### Step 5 – Derive new solution paths

1. Brainstorm alternative ways to address the reframed problem. Encourage
   diverse ideas without immediately judging them.
2. For each idea, connect it back to the basic facts and constraints: Does it
   actually solve the reframed problem? Does it violate any non‑negotiable
   constraint?
3. Document at least two viable solution concepts that are materially different
   from the conventional approach.

### Step 6 – Validate and iterate

1. Share the reframed problem and proposed solution paths with stakeholders.
2. Ask for evidence to support or refute your listed facts and assumptions.
3. Update your lists and problem statement as new information emerges.
4. If an idea seems “insightful” but has no supporting evidence, mark it as
   speculative. Do not treat speculation as fact.

## Output Format

When this skill is invoked, produce a structured report with these sections:

1. **Conventional Solution & Assumptions** – A brief description of the current
   or requested solution and a bullet list of its underlying assumptions.
2. **Facts vs. Assumptions** – Two lists separating verifiable facts from
   assumptions. Note any assumptions that could be relaxed.
3. **Non‑Negotiable Constraints** – Hard constraints that must be respected.
4. **Reframed Problem Statement** – A single sentence capturing the core
   objective without referencing a specific implementation.
5. **Alternative Solution Paths** – Two or more high‑level solution concepts
   derived from the basic facts, with notes on why they may succeed.
6. **Open Questions & Next Steps** – Items that require further evidence,
   experiments, or stakeholder alignment.

## Example

**User Input:** “We should add an AI chat box to our securities trading app
because everyone else is doing it.”

**Skill Output (abridged):**

1. **Conventional Solution & Assumptions**
   - Proposed solution: Add a universal AI chat interface.
   - Assumptions:
     - Users want to chat with an agent rather than complete tasks.
     - A generic chat solves investment decision needs.
     - Existing app structure cannot change.
2. **Facts vs. Assumptions**
   - Facts:
     - Investors must research, monitor markets, make trades, and review outcomes.
     - The app has access to accounts, holdings, market data and transaction flows.
     - Regulatory constraints require risk disclosures and audit trails.
   - Assumptions:
     - Chat is the best interface; investors prefer conversation.
     - The current menu‑driven UI cannot be refactored.
     - Users will trust AI advice without context.
3. **Non‑Negotiable Constraints**
   - Securities regulations mandate accurate risk prompts and audit logs.
   - Real trades must be authorised using existing secure flows.
4. **Reframed Problem Statement**
   > “How can we help investors complete end‑to‑end investment tasks (research,
   > trade, review) in a more seamless, context‑aware manner while complying
   > with regulatory requirements?”
5. **Alternative Solution Paths**
   - **Task‑Driven Flow:** Integrate AI into each step of the investment journey
     (pre‑trade research, trade execution, post‑trade analysis) rather than a
     single chat entry point.
   - **Agent Orchestrator:** Use AI to orchestrate tools and data sources behind
     the scenes, surfacing contextual recommendations within existing screens.
6. **Open Questions & Next Steps**
   - Validate whether investors prefer guided task flows over free‑form chat.
   - Determine technical feasibility of embedding AI within secure trade flows.
   - Align stakeholders on refactoring the app’s information architecture.

## Notes

- Avoid overusing abstract statements like “the essence is…” without evidence.
- Always document the reasoning path and list any speculative ideas separately.
- Combine this skill with `scqa-problem-definition` and `issue-tree-builder`
  for a complete problem‑framing workflow within the thinking‑operating‑system.
