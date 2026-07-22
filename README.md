# pinc000.github.io

Interactive API reference for the Pinc000 Pinnacle API, rendered with
[Stoplight Elements](https://github.com/stoplightio/elements) and published via GitHub Pages.

The site is a single page (`index.html`) that renders `openapi.json`. The
committed `openapi.json` is only a fallback: on every deploy, the Pages
workflow (`.github/workflows/pages.yml`) re-fetches the current spec from
<https://api.pinc000.com/openapi.json> and publishes that instead. If the
fetch fails or returns invalid JSON, the committed copy is used.

## Triggering a rebuild

The site redeploys on any of:

- a push to `main`
- manual run via **Actions → Deploy API docs to GitHub Pages → Run workflow**
  (`workflow_dispatch`)
- a `repository_dispatch` event with type `openapi-updated`, sent by the
  reverse-api CI when the spec changes
- a scheduled refresh every 6 hours

`404.html` redirects all old (deleted) URLs to the root; `docs/index.html`
does the same for the legacy Redoc location.
