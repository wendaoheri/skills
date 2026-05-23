---
name: decision-matrix
description: >
  Systematically compare multiple options against weighted criteria to
  support objective decision‑making. Use this skill to prioritise features,
  select vendors, evaluate technical solutions, or choose among strategic
  alternatives.
version: 1.0.0
tags:
  - decision-making
  - analysis
  - prioritisation
requires:
  - issue-tree-builder
---

# Decision Matrix

## Overview

A decision matrix helps you compare diverse options against a set of criteria.
By assigning weights to criteria and scoring each option, you make transparent
trade‑offs and avoid gut‑feel decisions. This skill guides you to define
criteria, set weights, evaluate options, and interpret results.

## When to Use

Use this skill when:

- You must choose between several viable options (e.g. different suppliers,
  technical stacks, product features).
- The choice involves multiple factors with different levels of importance.
- Stakeholders need a rational, documented rationale for the decision.
- You want to highlight trade‑offs and opportunity costs explicitly.

## Process

### Step 1 – Identify options and criteria

1. List the options you are comparing (e.g. Option A, Option B, Option C).
2. Identify evaluation criteria relevant to the decision (e.g. cost, impact,
   risk, effort).
3. For each criterion, briefly define what high and low scores represent.

### Step 2 – Assign weights

1. Allocate a weight to each criterion based on relative importance. Weights
   should sum to 1.0 (or 100%).
2. Involve stakeholders to ensure alignment on what matters most.

### Step 3 – Score options

1. For each option and criterion, assign a score (e.g. on a 1–5 or 1–10 scale).
2. Use consistent interpretation (e.g. higher score = better performance).
3. Provide a short justification for each score, referencing evidence or
   assumptions.

### Step 4 – Calculate weighted scores

1. Multiply each score by its criterion weight to obtain weighted scores.
2. Sum weighted scores per option to get a total score.
3. Present the scores in a table for transparency.

### Step 5 – Interpret results

1. Identify the top‑scoring option(s) and note how close the scores are.
2. Discuss any criteria where a low score could be a deal breaker despite
   higher total scores.
3. Consider sensitivity analysis: How would slight weight changes affect the
   ranking?

### Step 6 – Recommend and note trade‑offs

1. Recommend the option with the highest justified score, acknowledging the
   trade‑offs.
2. Document any assumptions and potential risks for follow‑up.

## Output Format

Return:

1. **Criteria & Weights** – A table listing each criterion, its definition,
   weight, and rationale for the weight.
2. **Scoring Table** – A matrix showing scores for each option against each
   criterion, plus weighted scores and totals.
3. **Recommendation** – A paragraph summarising the recommended option and
   the key drivers.
4. **Trade‑Off Analysis** – Notes on significant compromises and any
   sensitivity analysis.

Example scoring table:

| Option | Cost (0.3) | Impact (0.4) | Risk (0.2) | Effort (0.1) | Total |
|-------|------------|-------------|-----------|-------------|-------|
| A     | 4→1.2      | 5→2.0      | 3→0.6     | 2→0.2      | 4.0   |
| B     | 3→0.9      | 4→1.6      | 5→1.0     | 4→0.4      | 3.9   |
| C     | 5→1.5      | 3→1.2      | 4→0.8     | 5→0.5      | 4.0   |

## Example

**User Input:** “We need to decide between three AI frameworks for our agent
platform.”

**Skill Output (abridged):**

1. **Criteria & Weights:**  
   - *Maturity (0.3):* How stable and proven is the framework?  
   - *Extensibility (0.3):* How easily can we build custom tools on top?  
   - *Community Support (0.2):* How active and helpful is the developer
     community?  
   - *Cost (0.2):* Licensing and operational costs.
2. **Scoring Table:** Provide scores and weighted scores for Framework A,
   Framework B, and Framework C with justifications.
3. **Recommendation:** Recommend Framework B due to a strong community and
   balance of maturity and extensibility, despite slightly higher cost.
4. **Trade‑Off Analysis:** Note that Framework C offers better extensibility
   but suffers from immaturity and higher risk.

## Notes

- Use weights and scoring scales consistently across options.
- Be transparent about subjective judgments; list any assumptions.
- Combine this skill with `jtbd-analysis` to ensure criteria reflect user jobs.
