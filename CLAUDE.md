# CLAUDE.md

## Project overview

This repository is a static Bootstrap 5 marketing landing page demo. The app is intentionally front-end only: it is served as plain HTML and CSS, without a framework, package manager, or build pipeline.

## Repository structure

- `sample.html` — complete landing page, CSS, and Bootstrap configuration
- `README.md` — project summary and local run instructions
- `.claude/mcp.json` — MCP configuration for GitHub and browser automation tools

## Local development

Serve the site over HTTP so the browser can load external assets correctly:

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8000/sample.html
```

To stop the server, press `Ctrl+C` in the terminal.

## Page features

`sample.html` includes:

- Responsive Bootstrap navigation
- Hero section with CTAs and stat cards
- Features grid
- Product/value proposition section
- Pricing cards for Starter, Growth, and Scale
- Testimonials section
- Contact/demo form
- Footer links

The page pulls Bootstrap 5.3.3, Bootstrap Icons, Inter fonts, and Unsplash images from public CDNs.

## Validation checklist

After making UI changes, validate at least the following with a browser or Playwright MCP:

- Desktop rendering around 1440px
- Mobile rendering around 375px
- Mobile navigation toggling and anchor-link behavior
- Image loading and browser console errors
- Contact form behavior and expected feedback
- Horizontal overflow and accessibility basics

Do not commit generated browser artifacts such as screenshots or Playwright output unless explicitly requested.

## Known issues and guardrails

- The contact form currently has no backend endpoint or submit handling.
- Form fields should include `name` values and `required` attributes where appropriate.
- The mobile navigation button should include an accessible label and `aria-controls`.
- A favicon is not provided, which can trigger a 404 when served locally.
- External CDN and image dependencies should be reviewed before production deployment.
- Product claims, statistics, and testimonials should be replaced with verified business data before going live.

## Change guidance

- Keep the page accessible, responsive, and semantic.
- Preserve existing Bootstrap conventions and in-page anchor IDs.
- Prefer explicit form metadata and visible success/error states.
- Avoid introducing build tooling unless the project requirements change.
- Keep changes scoped to the static page unless additional product functionality is required.
