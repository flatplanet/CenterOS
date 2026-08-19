# {{WORKFLOW_NAME}} - CONTEXT

## Purpose

{{ONE_LINE_PURPOSE}}

## Contents

- `CONTEXT.md` - this file.
- `LOG.md` - append-only journal of actions and runs for this workflow.
- If applicable, `<skill-name>/` - workflow-scoped skill directory. Each skill directory contains its own `SKILL.md`.

## Usage / Trigger Conditions

When to run this workflow, and who or what triggers it.

## Inputs

What this workflow needs to run: files, parameters, context, prerequisite state.

## Outputs

What this workflow produces: files, side effects, status, downstream state changes.

## Steps

1. First step.
2. Next step.
3. Continue as needed.
4. Append an entry to `LOG.md`.

## Dependencies

List everything a fresh machine needs to run this workflow. Explicitly say "None" for a category if it does not apply so cold-start readers know the question was considered, not skipped. Pip installs, npm packages, and system binaries do not ride with synced files; a new machine must reinstall them.

- **Runtime**: Python / Node / Bun version required, or "N/A" for pure text workflows.
- **Python packages**: exact install command, "stdlib only", or "N/A".
- **Node / npm packages**: exact install command or "N/A".
- **System binaries on PATH**: for example `ffmpeg`, `ffprobe`, `git`, or "None".
- **API keys / env vars**: name, purpose, source URL, approximate cost, or "None".
- **External accounts / services**: services requiring signup, or "None".
- **Internal ([OS_NAME])**: other workflows, wikis, skills, templates, or MCPs this relies on. List each with relative path and a short note, or "None".

## Known Issues / Gotchas

- Things that have broken before or that future sessions should watch out for. Start empty; append as issues arise.

## Related

- Pointers to related workflows, wikis, or parent directories.

## Revision History

- **{{DATE}}** - Created. Initial version.
