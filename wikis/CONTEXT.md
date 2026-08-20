# wikis/ - CONTEXT

## Purpose

Container for all wikis in CenterOS. A wiki is a structured knowledge base with immutable source files in `raw/` and maintained Markdown pages in `wiki/`.

## Contents

- `CONTEXT.md` - this file.
- `LOG.md` - append-only log for structural changes to the wikis directory.
- Future wiki directories, one per wiki.

## Usage / Trigger Conditions

Use this directory whenever [PRINCIPAL] asks [AI_NAME] to create, inspect, ingest into, lint, modify, or archive a wiki.

## Inputs

- A wiki request from [PRINCIPAL].
- Wiki scaffolding from `templates/wiki/`.
- Source files placed inside a wiki's `raw/` directory.

## Outputs

- New or modified wiki directories under `wikis/`.
- Updated wiki pages under each wiki's `wiki/` folder.
- Updated `LOG.md` files for the affected wiki and this container when structural changes occur.

## Steps

This directory is a container, not a runnable workflow. For structural wiki changes:

1. Read this file and the relevant wiki's `CONTEXT.md`.
2. Make the requested wiki change.
3. Update the affected wiki's `CONTEXT.md` if behavior changed.
4. Update root `SYSTEM_INDEX.md` if a wiki was added, removed, renamed, archived, or significantly changed.
5. Append an entry to root `LOG.md`.
6. Append an entry to `wikis/LOG.md`.

## Dependencies

- `../templates/wiki/` - scaffolding for new wikis.
- `../workflows/create-wiki/` - workflow that creates wiki directories.
- `../CLAUDE.md` - project-level operating rules.
- `../AGENTS.md` - project-level operating rules.
- `../SYSTEM_INDEX.md` - system index updated for wiki changes.

## Known Issues / Gotchas

- Do not modify files inside a wiki's `raw/` folder after creation. Source files are immutable.
- Each wiki uses one root `LOG.md`. Do not create `wiki/log.md`.

## Related

- `../templates/wiki/` - wiki scaffolding.
- `../workflows/create-wiki/` - wiki creation workflow.
- `../SYSTEM_INDEX.md` - root system index.

## Revision History

- **2026-08-18** - Added wikis container context for template completeness.
