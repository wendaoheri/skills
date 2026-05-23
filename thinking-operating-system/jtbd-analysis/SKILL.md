---
name: jtbd-analysis
description: >
  Apply the Jobs to be Done (JTBD) framework to discover the underlying tasks,
  contexts, and desired outcomes that drive user behaviour. This skill helps
  you move beyond feature lists to understand why users “hire” a product or
  service and what success looks like for them.
version: 1.0.0
tags:
  - user-research
  - product-design
  - analysis
requires:
  - scqa-problem-definition
---

# JTBD Analysis

## Overview

Jobs to be Done is a framework that focuses on the progress a user seeks to
make in a particular situation. Instead of asking “What features do users
want?” it asks “What job are they hiring this product to perform?” This
perspective reveals latent needs and aligns product design with real user
outcomes.

## When to Use

Use this skill when:

- You need to understand user motivations behind a request or behaviour.
- Prioritising features based on user value.
- Designing new products or AI agents.
- Assessing whether a proposed solution aligns with user goals.

## Process

### Step 1 – Identify the user and context

1. Define the user persona or segment.
2. Describe the circumstances or situation in which the job arises (time,
   place, triggers, constraints).

### Step 2 – Define the desired progress or goal

1. Ask what the user is trying to accomplish (the “job”).
2. Distinguish between functional goals (tasks) and emotional or social jobs
   (feelings or perceptions).

### Step 3 – Map the steps and obstacles

1. List the sequence of actions the user currently takes to complete the job.
2. Note pain points, friction, or anxieties at each step.
3. Identify any workaround solutions or hacks the user employs.

### Step 4 – Articulate success criteria

1. Capture how the user measures success (e.g. speed, accuracy, confidence).
2. Include both functional outcomes (e.g. “I bought the right stock”) and
   emotional outcomes (e.g. “I feel confident and informed”).

### Step 5 – Extract job statements

1. Combine the context, trigger, job, and outcome into a concise JTBD statement.
   A common pattern is:

   > “When [context], I want to [job], so I can [desired outcome].”

2. Create separate statements for functional and emotional jobs if necessary.

### Step 6 – Derive implications

1. For each job, brainstorm how your product or AI agent can better support it.
2. Identify gaps where current solutions fail or create new pain.
3. Prioritise jobs based on importance and satisfaction (high importance,
   low satisfaction jobs are high‑impact opportunities).

## Output Format

Provide a structured output with these sections:

1. **User & Context** – Persona/segment and situation description.
2. **Jobs** – A list of job statements, distinguishing between functional,
   emotional, and social jobs.
3. **Steps & Pain Points** – A brief outline of current steps and
   corresponding obstacles.
4. **Success Criteria** – How the user judges a successful outcome.
5. **Opportunities** – Potential improvements or new features to better serve
   the jobs.

## Example

**User Input:** “Users say they want a notification feature for price alerts.”

**Skill Output (abridged):**

1. **User & Context:** A retail investor monitoring several volatile stocks
   during work hours, often multitasking and unable to watch charts.
2. **Jobs:**
   - Functional: “When I’m busy at work, I want to know immediately when a
     stock I own crosses a threshold so I can decide whether to act.”
   - Emotional: “I want to feel confident that I won’t miss critical market
     movements and will avoid regret.”
3. **Steps & Pain Points:** Currently sets manual reminders and refreshes
   the app; often misses rapid price swings. Uncertainty about whether alerts
   are reliable.
4. **Success Criteria:** Receives timely, actionable alerts with clear context
   (e.g. reason for movement) and feels in control of decisions.
5. **Opportunities:** Provide context‑aware AI alerts with concise
   explanations, snooze options, and integration into the user’s workflow.

## Notes

- JTBD complements `issue-tree-builder` by clarifying user needs behind each
  branch.
- Avoid describing jobs solely in product terms; focus on the user’s progress.
- Consider emotional and social dimensions, not just functional tasks.
