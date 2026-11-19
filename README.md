# Gemini & Agent Configurations

A curated collection of `gemini.md` and `skills.md` configuration files for AI-assisted software development across multiple tech stacks.

Use these templates to give your AI coding assistant consistent architectural context, coding standards, and repeatable workflows from the start of a project.

## File Roles

* **`gemini.md`** — Project context, architectural constraints, coding standards, environment details, and "do/don't" guardrails.
* **`skills.md`** — Reusable, step-by-step workflows and task instructions (e.g., scaffolding endpoints, writing table-driven tests, running security audits).

## Repository Structure

```text
.
├── global/                 # Shared baseline rules and universal skills
│   ├── gemini.md
│   └── skills.md
├── stacks/                 # Language and framework-specific configurations
│   ├── flask/
│   ├── golang/
│   └── php/
└── scripts/                # Utility scripts for bootstrapping projects
