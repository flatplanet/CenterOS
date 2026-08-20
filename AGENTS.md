# [OS_NAME] AI Operating System Instructions

> Fresh harness session? If this repo has not been initialized yet, read `STARTUP.md` first. If it has already been initialized, read `BOOTSTRAP.md` first.

This directory is the root of an AI operating system: a structured collection of folders that house workflows, wikis, templates, memory, and other modular components [AI_NAME] can operate on.

## CLAUDE.md / AGENTS.md Synchronization

`CLAUDE.md` and `AGENTS.md` are synchronized copies of the same instruction file and must remain identical at all times.

If you add, remove, edit, or reorganize content in either file, make the identical change to the other file during the same operation.

Never update one without updating the other.

Before finishing any operation involving either file, compare them and confirm that their contents are identical.

## Public Template Versus Personalized Instance

This repo starts as the public CenterOS template. After `STARTUP.md` runs once, it becomes a personalized AI operating system.

- Use `CenterOS` when referring to the public template/framework.
- Use `[OS_NAME]` when referring to the user's personalized operating system.
- Use `[AI_NAME]`, `[AI_NICKNAME]`, `[PRINCIPAL]`, and `[PRINCIPAL_NICKNAME]` for user-specific identity values until startup replaces them.

## Directory Structure

### `workflows/`

All workflows live here. A workflow is a self-contained, runnable procedure: steps, prompts, scripts, or skills that accomplish a defined task. When creating a new workflow:

- Place it in its own subdirectory under `workflows/<workflow-name>/`.
- Every workflow directory must contain a `CONTEXT.md` file.
- Every active workflow directory must contain a `LOG.md` file.
- Keep each workflow self-contained. Inputs, outputs, dependencies, and steps should be documented inside its folder.

### Workflow-Scoped Skills

A skill is a directory named after the skill, with `SKILL.md` at its root. The directory's name is the skill's identifier. Supporting files such as scripts, references, and seed assets live inside the same directory alongside `SKILL.md`.

Skills live directly inside their parent workflow directory. Do not use a `skills/` grouping wrapper.

Example single-skill workflow:

```text
workflows/writing/
  CONTEXT.md
  LOG.md
  writing/
    SKILL.md
```

Example multi-skill workflow:

```text
workflows/youtube-builder/
  CONTEXT.md
  LOG.md
  scripts/
  projects/
  hook/
    SKILL.md
  title/
    SKILL.md
  script/
    SKILL.md
```

Rules:

- Skill folders are exempt from the universal `CONTEXT.md` rule. The parent workflow's `CONTEXT.md` documents every bundled skill in its Contents section and Dependencies section.
- Workflows are self-contained. No cross-workflow skill references. If two workflows need the same capability, each carries its own copy or inlines the guidance.

### `wikis/`

All wikis live here. A wiki is a knowledge base: reference material, domain notes, standard operating procedures, or persistent documentation. When creating a new wiki:

- Place it in its own subdirectory under `wikis/<wiki-name>/`.
- Every wiki directory must contain a `CONTEXT.md` file.
- Every active wiki directory must contain a `LOG.md` file.

### `templates/`

Scaffolding templates for new workflows, wikis, and skills. [AI_NAME] must use these templates when creating new components so every directory stays structurally consistent.

If the `CONTEXT.md` schema changes in this file, update the templates in the same session.

### `memory/`

Durable, cross-session memory [AI_NAME] keeps about this project: feedback, references, user profile, project context, and decisions. Lives inside the repo so it travels with the project.

Read `memory/MEMORY.md` at the start of every session. Write new memories here, not to any per-user cache outside the repo.

### Other Directories

Additional top-level folders may be added over time, such as `data/`, `tools/`, or `skills/`. Every new directory must get its own `CONTEXT.md`.

## The `CONTEXT.md` Rule

Every directory [AI_NAME] creates or works in should contain a `CONTEXT.md` file. This is non-negotiable for workflow and wiki directories and strongly required everywhere else.

`CONTEXT.md` explains the purpose of the directory so future sessions and humans can understand the folder without reading every file inside it.

Required sections:

1. **Purpose** - one or two sentences stating what this directory is for.
2. **Contents** - what lives here: files, subfolders, and their roles.
3. **Usage / Trigger Conditions** - how this directory is meant to be used or invoked.
4. **Inputs** - what the workflow/component needs to run.
5. **Outputs** - what it produces.
6. **Steps** - numbered list of steps. The final step of every workflow must be: `Append an entry to LOG.md.`
7. **Dependencies** - workflows, wikis, skills, MCPs, external tools, runtime packages, accounts, and env vars.
8. **Known Issues / Gotchas** - anything that has broken before or future sessions should watch out for.
9. **Related** - pointers to related workflows, wikis, parent directories, or child directories.
10. **Revision History** - dated one-line entries describing changes to this `CONTEXT.md` or the component it documents.

Whenever [AI_NAME] modifies a workflow, wiki, or active component, update the relevant `CONTEXT.md` in the same session and add a Revision History entry.

## The `LOG.md` Rule

Every directory that houses a workflow or active component must contain a `LOG.md` file. This is an append-only journal of actions taken in that directory.

Log entry format:

```text
## YYYY-MM-DDTHH:MM:SS+/-HH:MM -- <action-type> -- <actor>
<one-line description of what happened, including inputs/outputs or error if relevant>
```

Action types: `created`, `modified`, `ran-start`, `ran-complete`, `ran-failed`, `note`.

Logging rules:

1. The last step of every workflow is to append an entry to `LOG.md`.
2. Log both ends of a run: `ran-start` and `ran-complete`, or `ran-failed`.
3. Log failures. Do not silently discard errors.
4. Log structural changes. Creating, renaming, or significantly modifying files gets a `modified` or `created` entry.
5. Append-only. Never edit or delete past log entries.
6. Newest entries go at the bottom.

The root `LOG.md` is for system-wide events: new workflows, new wikis, major restructures, and other top-level changes. Individual workflow runs stay in their own directory's log.

## Operating Rules

When working in this repo:

1. New workflows go under `workflows/<name>/` with `CONTEXT.md` and `LOG.md`.
2. New wikis go under `wikis/<name>/` with `CONTEXT.md` and `LOG.md`.
3. Any new directory gets a `CONTEXT.md` before adding other files.
4. When asked to run or extend a workflow, first read its `CONTEXT.md`.
5. Keep structure consistent: one concept per directory, clearly named, documented via `CONTEXT.md`.
6. Document external dependencies explicitly. Include runtime, package installs, system binaries, API keys/env vars, external accounts, and internal dependencies. Say "None" for categories that do not apply.

## SYSTEM_INDEX.md - System Index

The root `SYSTEM_INDEX.md` is the living index of [OS_NAME]. It is [PRINCIPAL]'s at-a-glance view of what this system does.

[AI_NAME] must update `SYSTEM_INDEX.md` whenever:

1. A new workflow is added.
2. A new wiki is added.
3. Any other major component is added.
4. An existing workflow, wiki, or component is significantly changed, renamed, or archived.

Whenever any of the above happens, append a dated one-line entry to the `SYSTEM_INDEX.md` Changelog.

Keep entries short. The system index is a map, not a manual. Detailed docs live in each directory's `CONTEXT.md`.

## Path Rules

When creating skills, apps, workflows, wikis, or code anywhere in this project, always write paths relative to the repo root. Do not put absolute paths in project files.

## The 90-10 Protocol

When building anything in [OS_NAME], especially workflows, default to the 90-10 Protocol: aim to do about 90 percent of deterministic work programmatically and reserve AI judgment for the 10 percent that genuinely needs it.

Code handles:

- File parsing, reading, writing, moving, and renaming.
- Text extraction, formatting, and regex work.
- Data handling in any form: Markdown, logs, JSON, CSV, text files, folders, spreadsheets, APIs, or databases. Use deterministic code for parsing, validation, normalization, import/export, deduplication, indexing, migrations, backups, and other rule-based data operations.
- API calls, batch operations, and data transforms.
- Deterministic, repetitive, or rule-based tasks.

AI handles:

- Summarization and nuanced classification.
- Writing prose.
- Interpreting ambiguous input.
- Decisions that require context or judgment.

Storage hierarchy:

1. Plain Markdown, logs, text files, or folders.
2. Flat files such as JSON or CSV.
3. Spreadsheets when tabular editing, formulas, or human review are useful.
4. A database only when the task requires larger scale, relational queries, concurrent updates, indexing, performance, or long-term structured application state.

### Scope

- Primary target: workflows. When scoping a new workflow, the first question is "what part of this can a script do?"
- Also applies to skills, apps, wikis, data handling, and anything else built inside [OS_NAME].
- If possible: do not force 90-10 onto inherently AI-heavy tasks such as pure writing, synthesis, strategy, or judgment. Use it as the default mindset, not a mandate.

Use this protocol as the default mindset, not as a rigid rule for inherently AI-heavy work.
