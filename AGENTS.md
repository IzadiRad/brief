# AGENTS.md

## Cursor Cloud specific instructions

### Product overview
This repo is a single static page: `index.html`. It is the **CodiMan project brief intake form** — a Persian (RTL) 7-section questionnaire. On submit it validates required fields (brand, industry, budget), builds a text brief, and offers copy-to-clipboard, `.txt` download, and an "open Telegram" handoff. There is **no backend, database, build step, or package manager**.

### Running it
Serve the file with any static server from the repo root, e.g.:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080/index.html`. Use `localhost` (a secure context) rather than `file://` so the clipboard actions work.

### Lint / test / build
There is **no lint config, no test suite, and no build**. `index.html` is the deliverable artifact itself. Editing the HTML/JS and refreshing the browser is the full dev loop (no hot reload — do a manual refresh).

### Gotchas
- Tailwind and the Vazirmatn font load from CDNs (`cdn.tailwindcss.com`, `fonts.googleapis.com`). With outbound network blocked the page still works but renders unstyled / with fallback fonts.
- The "ارسال در تلگرام" (Telegram) button opens `https://t.me/AMIzadirad` in a new tab; this is an external handoff, not part of this repo.
