# CenterOS Template - System Index

This repo is a reusable starter template for building a personalized AI operating system. After cloning, run `STARTUP.md` once to turn the generic template into CenterOS.

Every workflow, wiki, or major component gets a short entry here so [PRINCIPAL] can review the system at a glance.

**Maintained by:** [AI_NAME]
**Framework:** CenterOS
**Instance name:** CenterOS

---

## First-Run Setup

Start here after cloning:

- `STARTUP.md` - one-time setup. Asks the user a short questionnaire and replaces identity placeholders.
- `BOOTSTRAP.md` - every-session startup. Use this after first-run setup is complete.

## Workflows

### create-wiki

Scaffolds a new wiki in `wikis/<name>/` with `raw/`, `wiki/`, a customized `CONTEXT.md`, and logs. Follows the Karpathy LLM Wiki pattern.

**Path:** `workflows/create-wiki/`
**Status:** active
**Last updated:** 2026-08-18

<!-- Format:
### <workflow-name>
One short sentence describing what it does.
**Path:** `workflows/<workflow-name>/`
**Status:** active | experimental | archived
**Last updated:** YYYY-MM-DD
-->

---

## Wikis

<!-- Format:
### <wiki-name>
One short sentence describing what it covers.
**Path:** `wikis/<wiki-name>/`
**Status:** active | experimental | archived
**Last updated:** YYYY-MM-DD
-->

---

## Other Components

### Templates

Scaffolding for new workflows and wikis. [AI_NAME] uses these to bootstrap new components.

**Path:** `templates/`
**Status:** active
**Last updated:** 2026-08-18

### Images

Public visual assets for the CenterOS template, including the initial SVG logo and standalone mark.

**Path:** `images/`
**Status:** active
**Last updated:** 2026-08-18

<!-- For anything that is not a workflow or wiki: templates, tools, data sets, apps, etc. Same format. -->

---

## Core System Files

### STARTUP.md

One-time first-run setup instructions for cloning the CenterOS template and personalizing it.

**Path:** `STARTUP.md`

### BOOTSTRAP.md

Every-session orientation file. Tells a fresh AI session what to read and what to say after loading context.

**Path:** `BOOTSTRAP.md`

### CLAUDE.md

Root instructions for Claude or compatible harnesses when operating inside this project. Must stay identical to `AGENTS.md`.

**Path:** `CLAUDE.md`

### AGENTS.md

Root instructions for ChatGPT Codex or compatible harnesses when operating inside this project. Must stay identical to `CLAUDE.md`.

**Path:** `AGENTS.md`

### SOUL.md

[AI_NAME]'s identity, purpose, disposition, operating principles, and production output rules.

**Path:** `SOUL.md`

### PRINCIPAL.md

Concise profile for [PRINCIPAL]: identity, work/life context, patterns, and collaboration style.

**Path:** `PRINCIPAL.md`

### memory/

Durable, cross-session memory for CenterOS.

**Path:** `memory/`

---

## Changelog

- **2026-04-15** - Initialized CenterOS template: created `CLAUDE.md`, `AGENTS.md`, `SOUL.md`, and `README.md`.
