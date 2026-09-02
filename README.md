# pinc000.github.io

Interactive API reference for the Pinc000 Pinnacle API, rendered with
[Redoc](https://github.com/Redocly/redoc) and published via GitHub Pages.

The site is a single page (`index.html`) that renders `openapi.json` —
production docs by default, and the stage environment at
[`/?env=stage`](https://pinc000.github.io/?env=stage) (same page, rendering
`openapi-stage.json`; an in-page switcher sits above the credential form).
Each spec's `servers[0]` and curl samples carry that environment's base URL,
so the try-it playground always runs against the environment being viewed.
Credentials are stored per environment — stage and production accounts are
separate.

The committed `openapi.json` / `openapi-stage.json` are only fallbacks: on
every deploy, the Pages workflow (`.github/workflows/pages.yml`) re-fetches
the current specs from <https://api.pinc000.com/openapi.json> and
<https://api-stage.pinc000.com/openapi.json> and publishes those instead. If a
fetch fails, returns invalid JSON, or the spec does not advertise its own
environment's URL in `servers[0]`, that environment's committed copy is used.

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
