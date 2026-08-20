# workflows/ - CONTEXT

## Purpose

Container for all runnable workflows in CenterOS. A workflow is a self-contained procedure with documented inputs, outputs, dependencies, steps, and logs.

## Contents

- `CONTEXT.md` - this file.
- `LOG.md` - append-only log for structural changes to the workflows directory.
- `create-wiki/` - workflow for scaffolding new wiki directories.
- Future workflow directories, one per workflow.

## Usage / Trigger Conditions

Use this directory whenever [PRINCIPAL] asks [AI_NAME] to create, inspect, run, modify, or archive a workflow.

## Inputs

- A workflow request from [PRINCIPAL].
- Existing workflow templates from `templates/workflow/`.
- Any task-specific files, parameters, or dependencies documented in the selected workflow.

## Outputs

- New or modified workflow directories under `workflows/`.
- Updated workflow `CONTEXT.md` and `LOG.md` files.
- Updated root `SYSTEM_INDEX.md` and root `LOG.md` when workflows are added, removed, renamed, or significantly changed.

## Steps

This directory is a container, not a runnable workflow. For structural workflow changes:

1. Read this file and the relevant workflow's `CONTEXT.md`.
2. Make the requested workflow change.
3. Update the affected workflow's `CONTEXT.md` if behavior changed.
4. Update root `SYSTEM_INDEX.md` if the workflow was added, removed, renamed, archived, or significantly changed.
5. Append an entry to root `LOG.md`.
6. Append an entry to `workflows/LOG.md`.

## Dependencies

- `../templates/workflow/` - scaffolding for new workflows.
- `../CLAUDE.md` - project-level operating rules.
- `../AGENTS.md` - project-level operating rules.
- `../SYSTEM_INDEX.md` - system index updated for workflow changes.

## Known Issues / Gotchas

- Workflow-scoped skills live directly inside their parent workflow directory. Do not create a `skills/` wrapper.
- Keep workflows self-contained. Do not reference skills across workflow boundaries.

## Related

- `../templates/workflow/` - workflow scaffolding.
- `../SYSTEM_INDEX.md` - root system index.
- `create-wiki/` - currently bundled workflow.

## Revision History

- **2026-08-18** - Added workflows container context for template completeness.
