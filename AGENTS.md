# AGENTS.md

## Cursor Cloud specific instructions

### What this project is
- Single-file static web app: everything lives in `index.html` (HTML + inline CSS + inline vanilla JS). It is "CodiMan — بریف پروژه نرم‌افزاری", a bilingual (Persian/RTL default, English/LTR) software-project brief wizard that autosaves to `localStorage` and can export a PDF or share via a Telegram deep link.
- There is no backend, no database, no package manager, no build step, and no lockfiles. All third-party libs (jsPDF, Google Fonts) are loaded from CDNs at runtime.

### Running it (development)
- Serve the folder with any static server and open the page, e.g. `python3 -m http.server 8000` from the repo root, then open `http://localhost:8000/`. Opening `index.html` directly as a `file://` URL also works.
- There is nothing to install/build; edits to `index.html` are picked up on browser refresh.

### Lint / test / build
- No lint, test, or build tooling is configured in this repo. There are no automated tests. "Build" is a no-op — the deliverable is `index.html` itself.

### Gotchas
- Internet access is required for the two CDN dependencies. The core form works offline (fonts fall back to system fonts), but the "Download PDF" button depends on jsPDF loading from the CDN — if it fails to load, the app shows "PDF library unavailable" instead of downloading.
- The Telegram share button just opens `https://t.me/AMIzadirad` in a new tab; there is no API integration.
