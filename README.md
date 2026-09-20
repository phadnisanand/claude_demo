# BootstrapLab demo

This repository contains a single-page Bootstrap 5 marketing landing page built as a static HTML demo. It is intentionally simple and does not require a build tool or package install.

## Files

- `sample.html` — the complete landing page markup and inline styling
- `CLAUDE.md` — project notes and local development guidance
- `.claude/mcp.json` — local MCP server configuration for GitHub and Playwright

## Run locally

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8000/sample.html
```

## Notes

- No Node.js or package workflow is required.
- The page relies on Bootstrap and external image/font CDNs in the browser.
- For accessibility and UX validation, test both desktop and mobile layouts in a browser.
