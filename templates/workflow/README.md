# Workflow Template

Scaffolding for a new workflow in CenterOS.

## Files In This Template

- `CONTEXT.md` - template for the workflow's main context file.
- `LOG.md` - template for the workflow's append-only journal.
- Optional dashboard pages should use `../dashboard-page/page.html`.

## How James Uses This Template

When Benjamin Richter asks for a new workflow named `<workflow-name>`:

1. Create `workflows/<workflow-name>/`.
2. Copy `CONTEXT.md` and `LOG.md` from this template into that new directory.
3. Replace every `{{PLACEHOLDER}}` token. Current placeholders:
   - `{{WORKFLOW_NAME}}` - the workflow's kebab-case name.
   - `{{ONE_LINE_PURPOSE}}` - a single sentence describing what the workflow does.
   - `{{DATE}}` - today's date in `YYYY-MM-DD` format.
   - `{{TIMESTAMP}}` - full ISO 8601 timestamp with timezone offset.
4. Fill in the real steps, inputs, outputs, dependencies, and known issues sections.
5. If the user requests a dashboard page, use `dashboard/create-dashboard-page.py` when Python is available. Otherwise copy `templates/dashboard-page/page.html` to `dashboard/workflows/<workflow-name>/index.html`, replace placeholders, add or update the sidebar link in `dashboard/index.html` with `target="dashboard-frame"`, and document the dashboard page in the workflow's `CONTEXT.md`.
6. Dashboard pages own their own topbar and breadcrumbs, but must not include sidebar markup, logo markup, or a second dashboard shell.
7. Ensure the final step of every workflow is: `Append an entry to LOG.md.`
8. Update the root `SYSTEM_INDEX.md` with a one-line entry for the new workflow.
9. Append entries to the root `LOG.md` and to `workflows/LOG.md` if that file exists.
