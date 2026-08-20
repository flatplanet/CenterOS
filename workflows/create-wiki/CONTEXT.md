# create-wiki - CONTEXT

## Purpose

Scaffolds a new wiki inside `wikis/<wiki-name>/` following the CenterOS wiki pattern based on Andrej Karpathy's LLM Wiki. Produces a ready-to-use directory with an immutable `raw/` folder for sources and a maintained `wiki/` folder for pages.

## Contents

- `CONTEXT.md` - this file.
- `LOG.md` - append-only log of this workflow's runs.

## Usage / Trigger Conditions

Run when [PRINCIPAL] says something like:

- "Create a wiki on X"
- "Build me a wiki for Y"
- "Start a new wiki about Z"

Before scaffolding, [AI_NAME] confirms two things with [PRINCIPAL]:

1. **Wiki name** - short kebab-case directory name, such as `llm`, `tax-law`, or `codemy-ops`.
2. **Wiki topic** - one sentence describing the subject, used to fill the `{{WIKI_TOPIC}}` placeholder.

## Inputs

- `{{WIKI_NAME}}` - short display name, such as "LLM" or "Tax Law".
- `{{WIKI_DIR_NAME}}` - kebab-case directory name for `wikis/<wiki-dir-name>/`.
- `{{WIKI_TOPIC}}` - sentence-length topic description.

## Outputs

A new directory at `wikis/<wiki-dir-name>/` with this structure:

```text
wikis/<wiki-dir-name>/
  CONTEXT.md
  LOG.md
  raw/
    .gitkeep
  wiki/
    index.md
```

Plus log entries and a `SYSTEM_INDEX.md` update.

## Steps

1. Append a `ran-start` entry to this workflow's `LOG.md` with the wiki name.
2. Confirm inputs with [PRINCIPAL] if not already provided: wiki display name, directory name, and one-sentence topic.
3. Create the wiki directory at `wikis/<wiki-dir-name>/`.
4. Copy `templates/wiki/CONTEXT.md` into `wikis/<wiki-dir-name>/CONTEXT.md` and replace `{{WIKI_NAME}}` and `{{WIKI_TOPIC}}`.
5. Create `wikis/<wiki-dir-name>/LOG.md` with an initial `created` entry.
6. Create `wikis/<wiki-dir-name>/raw/` with a `.gitkeep` file.
7. Create `wikis/<wiki-dir-name>/wiki/`.
8. Create `wikis/<wiki-dir-name>/wiki/index.md` with a minimal stub.
9. Update `wikis/LOG.md` if it exists with a `modified` entry noting the new wiki was added.
10. Update root `SYSTEM_INDEX.md` with a wiki entry.
11. Update root `LOG.md` with a `created` entry noting the new wiki.
12. Append a `ran-complete` entry to this workflow's `LOG.md`, or `ran-failed` if anything above errored.

## Dependencies

- `../../templates/wiki/CONTEXT.md` - the template this workflow copies and fills in.
- `../../templates/wiki/README.md` - reference for placeholder meanings.
- `../../wikis/` - destination directory.
- `../../CLAUDE.md` - rules for `CONTEXT.md` schema, `LOG.md` format, and path conventions.

## Known Issues / Gotchas

- The top-level directory is plural: `wikis/`. Each wiki contains a singular `wiki/` subfolder.
- Do not touch `raw/` after creation. Source files are immutable.
- Wikis use one `LOG.md` at the wiki root. Do not scaffold `wiki/log.md`.
- If the wiki directory already exists, stop and ask [PRINCIPAL] whether to overwrite, append, or pick a different name.

## Related

- `../../templates/wiki/` - template source.
- `../../wikis/` - where output goes.
- `../../SYSTEM_INDEX.md` - updated on each run.

## Revision History

- **2026-04-15** - Created. Initial version.
- **2026-04-15** - Dropped `wiki/log.md` scaffolding. Wikis now use a single `LOG.md` at the root.
- **2026-08-18** - Converted instance-specific references to first-run placeholders.
