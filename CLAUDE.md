# CLAUDE.md

## Project overview

This repository contains a single-page Bootstrap 5 marketing/demo application. The page is currently static HTML rather than a Drupal theme or a package-managed application.

## Repository structure

- `sample.html` - Main landing page and all page styling.
- `README.md` - Repository note indicating that the file is read-only.
- `.claude/mcp.json` - GitHub and Playwright MCP server configuration.

The old `sample` text file was replaced by `sample.html`.

## Running locally

There is no `package.json`, build step, or test runner. Serve the repository over HTTP so browser behavior and external assets work correctly:

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Open:

```text
http://127.0.0.1:8000/sample.html
```

Stop the server with `Ctrl+C`.

## Browser validation

The repository configures Playwright MCP in `.claude/mcp.json`:

- GitHub MCP: `https://api.githubcopilot.com/mcp`
- Playwright MCP: `npx @playwright/mcp@latest`

When validating UI changes, check at least:

- Desktop rendering around 1440px wide.
- Mobile rendering around 375px wide.
- Mobile navigation toggle and anchor links.
- Image loading and browser console errors.
- Contact form behavior.
- Horizontal overflow and basic accessibility-tree output.

Generated Playwright logs and screenshots should remain local and should not be committed unless explicitly requested.

## Page content

`sample.html` includes:

- Responsive Bootstrap navigation.
- Hero section with primary calls to action.
- Features section.
- Product/value proposition section.
- Starter, Growth, and Scale pricing cards.
- Testimonials section.
- Contact/demo form.
- Footer links.

Bootstrap 5.3.3, Bootstrap Icons 1.11.3, Inter font files, and Unsplash images are loaded from external CDNs/URLs.

## Current known issues

- The contact form has no backend endpoint or submit handler. It currently submits as a default `GET` request to the same page.
- Contact fields do not have `name` attributes and are not marked `required`.
- The mobile navigation button should have an accessible label and explicit `aria-controls`.
- `/favicon.ico` is not present, which produces a browser 404 when served locally.
- External CDN/image dependencies should be reviewed before production deployment.
- Sample statistics, testimonials, and security claims should be replaced with verified product data.

## Change guidelines

- Keep the page accessible and responsive.
- Preserve existing Bootstrap conventions and in-page anchor IDs.
- Prefer semantic HTML, explicit form metadata, and visible success/error states.
- Avoid committing generated browser artifacts such as `.playwright-mcp/`, `landing-desktop.png`, or `landing-mobile.png`.
- After UI changes, serve the page locally and validate it with Playwright MCP at desktop and mobile sizes.
