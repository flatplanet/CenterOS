# Dashboard Page Template - CONTEXT

## Purpose

Template for creating workflow dashboard pages that load inside the CenterOS dashboard iframe shell.

## Contents

- `CONTEXT.md` - this file.
- `page.html` - standalone iframe page template with a page-owned topbar and content area.
- `README.md` - usage instructions for future AI sessions.

## Usage / Trigger Conditions

Use this template when Benjamin Richter asks for a workflow dashboard page, a workflow run dashboard page, or a visual dashboard surface tied to a CenterOS workflow. Prefer `dashboard/create-dashboard-page.py` when Python is available; use this template manually when it is not.

## Inputs

- Workflow name.
- Page title.
- Breadcrumb labels.
- Page-specific dashboard content.

## Outputs

- A standalone HTML page under `dashboard/workflows/<workflow-name>/index.html` or `dashboard/workflows/<workflow-name>/runs/<run-name>.html`.
- A sidebar link in `dashboard/index.html` if the page should appear in the main dashboard navigation.

## Steps

1. Run `python dashboard/create-dashboard-page.py <workflow-name> "<Workflow Name>" "<description>"` when Python is available.
2. If Python is unavailable, copy `page.html` to the target dashboard page path.
3. Replace every `{{PLACEHOLDER}}` token.
4. Keep the page's topbar and breadcrumbs inside the copied page.
5. Do not add sidebar markup to the copied page.
6. Link the copied page from `dashboard/index.html` if it belongs in the sidebar.
7. Document the dashboard page in the parent workflow's `CONTEXT.md` Outputs and Related sections.

## Dependencies

- Runtime: Browser; Python 3 for the helper script.
- Python packages: stdlib only.
- Node / npm packages: N/A.
- System binaries on PATH: None.
- API keys / env vars: None.
- External accounts / services: None.
- Internal (CenterOS): `dashboard/create-dashboard-page.py`, `dashboard/index.html`, `dashboard/styles.css`, and the related workflow directory.

## Known Issues / Gotchas

- Dashboard pages are designed to load inside `dashboard/index.html`. They can open directly, but the sidebar will not be visible when opened alone.
- Use shared classes from `dashboard/styles.css` first. Add page-local CSS only when the shared design system cannot express the page.

## Related

- `../../dashboard/` - dashboard shell and shared styling.
- `../workflow/` - workflow template that can request a dashboard page.

## Revision History

- 2026-08-31 - Created dashboard page template.
- 2026-08-31 - Documented deterministic helper script usage.
