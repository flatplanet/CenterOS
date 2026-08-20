# Wiki Template

Scaffolding for a new wiki in CenterOS. Used by the `create-wiki` workflow.

## Files In This Template

- `CONTEXT.md` - the wiki's top-level context file. It describes structure, ingest workflow, page format, citation rules, and operating rules.

## Placeholders

- `{{WIKI_NAME}}` - short display name for the wiki header, such as "LLM", "Tax Law", or "Codemy Operations".
- `{{WIKI_TOPIC}}` - a sentence-ready description of the topic, such as "large language models and their training" or "US federal tax law for small businesses".

## What The `create-wiki` Workflow Builds

For a new wiki named `<wiki-name>`:

```
wikis/<wiki-name>/
  CONTEXT.md          <- copy of this template, placeholders filled in
  LOG.md              <- append-only log
  raw/                <- empty, for immutable source files
  wiki/               <- empty, to be populated during ingest
    index.md          <- empty table of contents
```

As of 2026-04-15, CenterOS uses a single `LOG.md` per wiki at the wiki root, not a separate `wiki/log.md`. Both structural changes and operational events go in the same log.

See `workflows/create-wiki/CONTEXT.md` for the full procedure.
