<p align="center">
  <img src="./assets/agent-skills-hero.png" alt="Abstract layers and connected nodes representing reusable AI agent skills" width="100%">
</p>

<h1 align="center">Agent Skills</h1>

<p align="center">
  Portable, source-grounded workflows for AI coding agents.
</p>

<p align="center">
  <a href="https://skills.sh/fr13dman/skills"><img src="https://skills.sh/b/fr13dman/skills" alt="skills.sh installs"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-8b5cf6.svg" alt="MIT License"></a>
  <img src="https://img.shields.io/badge/format-Agent%20Skills-22d3ee.svg" alt="Agent Skills format">
</p>

This repository contains reusable skills for AI coding tools that support the open Agent Skills format, including Codex, Claude Code, Cursor, and other agents supported by the [`skills`](https://github.com/vercel-labs/skills) CLI.

## Install

Browse the available skills and choose an agent interactively:

```bash
npx skills@latest add fr13dman/skills
```

Install one skill directly:

```bash
npx skills@latest add fr13dman/skills --skill code-walkthrough
```

Install it for a specific agent:

```bash
# Codex
npx skills@latest add fr13dman/skills --skill code-walkthrough -a codex

# Claude Code
npx skills@latest add fr13dman/skills --skill code-walkthrough -a claude-code

# Cursor
npx skills@latest add fr13dman/skills --skill code-walkthrough -a cursor
```

Add `-g` for a global installation available across projects. Add `-y` to skip confirmation prompts:

```bash
npx skills@latest add fr13dman/skills --skill code-walkthrough -a codex -g -y
```

## Available skills

| Skill | What it does | Install |
| --- | --- | --- |
| [`code-walkthrough`](./skills/code-walkthrough/) | Maps an unfamiliar codebase through verified architecture, design patterns, diagrams, entity glossaries, real use-case traces, and security and performance analysis. | `npx skills@latest add fr13dman/skills --skill code-walkthrough` |

### Code Walkthrough

`code-walkthrough` creates an evidence-based guide to a local project, source archive, checkout, or repository URL. It:

- Builds a source-linked architecture and component map
- Explains design patterns using their actual implementations and callers
- Produces an editable Excalidraw visual when supported, with Mermaid or SVG fallbacks
- Defines the important classes, interfaces, entities, events, and data models
- Traces at least three real use cases with signatures, parameters, and inputs and outputs
- Reviews authentication, authorization, security controls, performance mechanisms, and algorithms
- Ends with up to three focused comprehension questions

The workflow is read-only by default. It does not install dependencies, run untrusted repository scripts, start services, or modify the codebase being explained.

Example request:

```text
Walk me through this repository's architecture and trace three important use cases.
```

Agents that support explicit invocation may expose it as `$code-walkthrough` in Codex or `/code-walkthrough` in Claude Code.

## Manage installed skills

```bash
# List installed skills
npx skills@latest list

# Check for updates
npx skills@latest check

# Update this skill
npx skills@latest update code-walkthrough

# Remove this skill
npx skills@latest remove code-walkthrough
```

## Repository structure

```text
.
├── assets/
│   └── agent-skills-hero.png
├── skills/
│   └── code-walkthrough/
│       ├── SKILL.md
│       ├── agents/
│       │   └── openai.yaml
│       └── references/
│           ├── source-links.md
│           └── visuals.md
├── LICENSE
└── README.md
```

Every installable skill has a `SKILL.md` with portable instructions and may include supporting references, scripts, or assets. `agents/openai.yaml` provides optional OpenAI interface metadata; other compatible agents can use the core skill without it.

## License

Released under the [MIT License](./LICENSE).
