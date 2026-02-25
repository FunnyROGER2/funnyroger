## Cursor Cloud specific instructions

This is **FunnyROGER** — a static HTML/CSS personal portfolio site with zero build dependencies.

### Running the dev server

```sh
cd /workspace/src && python3 -m http.server 8080
```

The site is served from `src/` on `http://localhost:8080`. Favicon paths use absolute URLs (`/favicon/...`), so opening HTML files directly via `file://` will break asset resolution — always use an HTTP server.

### Project notes

- **No package manager, build step, linter, or test framework** — the project is plain HTML + CSS.
- **Deployment** is handled by GitHub Actions (`.github/workflows/deploy.yml`) via `rsync` over SSH to an external server. It is triggered on pushes/PRs to `master`.
- Two pages: homepage (`src/index.html`) and about page (`src/about/index.html`).
- The homepage grid layout uses CSS `round(up, sqrt(...))` for dynamic column calculation — requires a modern browser.
