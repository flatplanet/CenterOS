# templates/ - CONTEXT

## Purpose

Central home for all scaffolding templates used to bootstrap new components in [OS_NAME]. Using templates keeps every workflow, wiki, and skill structurally consistent so future sessions can navigate any directory without surprises.

## Contents

- `workflow/` - template files for creating a new workflow directory. Contains a template `CONTEXT.md`, `LOG.md`, and a short `README.md` explaining usage.
- `wiki/` - template files for creating a new wiki directory. Contains a template `CONTEXT.md` and a `README.md` describing placeholders. Used by `workflows/create-wiki/`.
- Future `skill/` - templates for a new skill directory.

## Usage / Trigger Conditions

[AI_NAME] uses these templates whenever [PRINCIPAL] asks to create a new workflow, wiki, or skill. [AI_NAME] copies the appropriate template files into the new directory and replaces all `{{PLACEHOLDER}}` tokens with real values.

## Inputs

- The name of the new component, such as `daily-standup` or `product-catalog`.
- A one-line purpose from [PRINCIPAL].
- Any additional detail [PRINCIPAL] provides: inputs, outputs, steps, constraints, or dependencies.

## Outputs

A fully scaffolded new directory with its own `CONTEXT.md` and `LOG.md`, ready to be filled in.

## Steps

This directory is a container, not a runnable workflow. The procedure for using a template:

1. Identify which template applies: workflow, wiki, or skill.
2. Copy the template files into the new directory.
3. Replace every `{{PLACEHOLDER}}` token with real content.
4. Update the root `SYSTEM_INDEX.md` to list the new component.
5. Append an entry to the root `LOG.md` noting the new component.
6. Append an entry to this directory's `LOG.md` noting the template was used.

## Dependencies

- `../CLAUDE.md` - defines the `CONTEXT.md` schema and `LOG.md` format the templates follow.
- `../AGENTS.md` - defines the `CONTEXT.md` schema and `LOG.md` format the templates follow.

## Known Issues / Gotchas

- If the `CONTEXT.md` schema in root `CLAUDE.md` or `AGENTS.md` changes, the templates here must be updated to match.

## Related

- `../CLAUDE.md` - project-level operating rules.
- `../AGENTS.md` - project-level operating rules.
- `../workflows/` - where scaffolded workflows end up.
- `../wikis/` - where scaffolded wikis end up.

## Revision History

- **2026-04-15** - Created. Initial version with workflow template.
- **2026-04-15** - Added wiki template at `templates/wiki/`.
- **2026-08-18** - Converted instance-specific references to first-run placeholders for template distribution.
