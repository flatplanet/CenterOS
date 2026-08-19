# memory/ - CONTEXT

## Purpose

Durable, cross-session memory for [OS_NAME]. This folder lives inside the repo so it travels with the project and remains visible to future AI sessions.

This is where [AI_NAME] writes and reads durable information about working with [PRINCIPAL]: feedback, references, user profile details, project context, decisions, and why-we-did-it notes.

## Contents

```text
CONTEXT.md       -- this file
LOG.md           -- append-only log of memory changes
MEMORY.md        -- the index. Always load this at session start.

feedback_*.md    -- corrections and validated approaches [PRINCIPAL] has given [AI_NAME]
reference_*.md   -- facts, canonical spellings, and pointers to external systems
user_*.md        -- information about [PRINCIPAL]'s role, goals, preferences, and knowledge
project_*.md     -- ongoing initiatives, decisions, deadlines, and motivations
```

Not every memory type needs to exist immediately. The naming pattern makes it simple to add files later.

## Usage / Trigger Conditions

Read `MEMORY.md` at the start of every session in this repo. Pull individual memory files only when their topics become relevant.

Write a new memory when:

- [PRINCIPAL] gives corrective feedback, especially repeated feedback.
- [PRINCIPAL] confirms a non-obvious approach worked.
- A durable fact about [PRINCIPAL], their work, family, tools, or preferences surfaces.
- A durable project decision is made that would be non-obvious to future sessions.

Do not write a memory for:

- Ephemeral task state.
- Something derivable from current files or logs.
- Duplicates of existing memories.
- Secrets, credentials, API keys, private addresses, or sensitive personal material.

## Inputs

- [AI_NAME]'s running conversation with [PRINCIPAL].
- [AI_NAME]'s observation of what [PRINCIPAL] corrects, validates, or leaves in place.

## Outputs

- New memory files in this folder.
- Updated `MEMORY.md` index with a new one-line pointer per file.
- Appended `LOG.md` entry documenting the change.

## Steps For Writing A Memory

1. Check for duplicates in `MEMORY.md` and this folder.
2. Write or update the relevant memory file with the correct type in frontmatter.
3. Update `MEMORY.md` with one line: `- [Title](file.md) -- one-line hook under 150 chars.`
4. Append an entry to `LOG.md`.

## Dependencies

- `../CLAUDE.md` - project-level operating rules.
- `../AGENTS.md` - project-level operating rules.
- `../BOOTSTRAP.md` - session-start reading order.
- `../PRINCIPAL.md` - durable user profile.
- `../SYSTEM_INDEX.md` - system index for workflows, wikis, and major components.

## Known Issues / Gotchas

- Do not write to per-user cache locations outside this repo. New memories belong in `memory/`.
- Treat this folder as synced project data. Do not store secrets or sensitive material here.
- `MEMORY.md` is the index, not the content. Keep individual memories in their own files.

## Related

- `../CLAUDE.md` - project-level instructions.
- `../AGENTS.md` - project-level instructions.
- `../BOOTSTRAP.md` - session-start reading order.
- `../PRINCIPAL.md` - profile for [PRINCIPAL].

## Revision History

- **2026-08-18** - Converted personal and machine-specific references into template placeholders.
