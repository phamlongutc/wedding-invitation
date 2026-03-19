# Copilot instructions — Thiệp cưới (Thiep-cuoi-deploy)

**Overview**
- **Project type**: Static single-page wedding-invitation site with an optional Node static server.
- **Entry points**: See [index.html](index.html) (UI and inline styles) and [server.js](server.js) (local dev server).

**How To Run (developer)**
- **Install + run**: `npm install` then `npm start` (reads [package.json](package.json) -> `node server.js`).
- **Quick local check**: open [index.html](index.html) directly in a browser for static-preview.

**Where to change content**
- **Visual/content changes**: edit [index.html](index.html). Most page layout is inline-generated HTML/CSS blocks.
- **Styles**: additional styles live under assets/css/ (e.g., [assets/css/style.css](assets/css/style.css)).
- **Images & media**: assets/images/ and assets/audio/.
- **Client JS**: main bundle is [assets/js/app.js](assets/js/app.js) — it's bundled/minified. Prefer changing HTML or smaller JS modules where available instead of editing the bundle directly.

**Conventions & important patterns**
- **Static-first**: The site is authored as a static export (heavy inline CSS in `index.html`) — small edits to HTML/CSS are the safest approach.
- **Single bundled JS**: `assets/js/app.js` is a packed bundle (fingerprinting, analytics and feature code). Treat it as generated; avoid large rewrites here unless you regenerate the bundle.
- **Personalization via query string**: The invitation supports `?name=GuestName` (see README.md). Preserve URL-based personalization when changing navigation or canonical links.
- **Relative asset paths**: All assets are referenced relative to the repository root (keep paths like `assets/...`).

**Integration & deployment**
- **Netlify**: Project includes [netlify.toml](netlify.toml) with a single-page redirect rule; deploy by connecting repo to Netlify or using drag-and-drop per README.
- **Node server**: [server.js](server.js) uses `express.static(__dirname)` and falls back to `index.html` for SPA routing.

**When an AI agent should modify which files**
- **Small text or layout changes**: modify [index.html](index.html) or files in assets/css/.
- **Add/remove images**: add under assets/images/ and update references in [index.html](index.html).
- **Instrumentation/analytics**: locate analytics calls inside [assets/js/app.js](assets/js/app.js) (minified); prefer adding a small separate script tag in [index.html](index.html) for new instrumentation.

**Examples**
- Update invitation title: edit the `<title>` tag in [index.html](index.html).
- Add a new static image: place file in assets/images/ and add the corresponding `<img src="assets/images/<name>">` in [index.html](index.html).
- Run locally: in terminal
```bash
npm install
npm start
# then open http://localhost:3000
```

**Do not assume**
- There is no source map or unbundled JS source in repo — editing `assets/js/app.js` is fragile.
- There are no automated tests or CI workflows in this repo.

If any section is unclear or you'd like me to include more examples (e.g., exact HTML snippets to change), tell me which area to expand.
