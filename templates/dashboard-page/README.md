# Dashboard Page Template

Scaffolding for a workflow dashboard page in CenterOS.

## Files In This Template

- `page.html` - full standalone HTML page intended to load inside the `dashboard/index.html` iframe.

## How James Uses This Template

When Benjamin Richter asks for a dashboard page for `<workflow-name>`:

1. Prefer the deterministic helper when Python is available:
   ```bash
   python dashboard/create-dashboard-page.py <workflow-name> "<Workflow Name>" "<description>"
   ```
2. If Python is unavailable, create `dashboard/workflows/<workflow-name>/` if it does not exist.
3. Copy `page.html` to `dashboard/workflows/<workflow-name>/index.html`.
4. Replace every `{{PLACEHOLDER}}` token. Current placeholders:
   - `{{PAGE_TITLE}}` - the browser title and visible page title.
   - `{{WORKFLOW_NAME}}` - the workflow's display name.
   - `{{WORKFLOW_SLUG}}` - the workflow's kebab-case directory name.
   - `{{PAGE_DESCRIPTION}}` - one sentence describing what this dashboard page shows.
   - `{{BREADCRUMB_CURRENT}}` - the final breadcrumb label for this page.
5. Keep the page's topbar inside the page.
6. Do not add sidebar markup to the page. The sidebar belongs only in `dashboard/index.html`.
7. Add or update the sidebar link in `dashboard/index.html` so it targets `dashboard-frame`.
8. Reuse classes from `dashboard/styles.css` before adding local CSS.
