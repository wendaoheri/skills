# AGENTS.md

This file provides guidance to Codex (Codex.ai/code) when working with code in this repository.

## Purpose

This repo is a practical skills collection for AI agents — not limited to Codex. Skills may include SKILL.md instruction files, Python utilities, TypeScript/JavaScript scripts, and shell scripts.

## Directory Structure

Skills are grouped by category:

```
skills/
├── <category>/          # e.g., dev/, data/, ops/, git/, writing/
│   ├── <skill-name>/
│   │   ├── SKILL.md     # Main skill instructions with frontmatter
│   │   └── ...          # Optional supporting scripts or files
│   └── ...
└── AGENTS.md
```

When adding a new skill, create a category directory if it doesn't exist, then create a subdirectory for the skill containing at minimum a `SKILL.md`.

## Skill Format

Every `SKILL.md` must begin with YAML frontmatter:

```yaml
---
name: <skill-name>
description: <one-line summary of what the skill does and when to invoke it>
---
```

Optional frontmatter fields: `trigger` (auto-invoke condition), `disable-model-invocation: true` (user-only trigger), `$ARGUMENTS` (accept input when invoked).

## Languages

Skills may use Python, TypeScript/JavaScript, Bash, or pure Markdown. Use the language most natural for the task. Shell scripts should be POSIX-compatible unless zsh features are needed.

## Working in This Repo

- To add a skill: pick or create a category, create `<category>/<skill-name>/SKILL.md`, fill in frontmatter and instructions
- To test a Codex skill: invoke it with `/<skill-name>` in a Codex session
- No build or test pipeline is configured yet
