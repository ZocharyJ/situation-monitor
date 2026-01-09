# Situation Monitor

A browser-only global situation dashboard (static HTML/CSS/JS) intended to run locally during development and deploy cleanly to GitHub Pages.

## Credits

This project is based on the original work by **Reggie (hipcityreg)**:

- Upstream/original: https://github.com/hipcityreg/situation-monitor
- This fork: https://github.com/ZocharyJ/situation-monitor

## What’s different from the original fork baseline

This repo has been heavily modified from the original fork starting point. Key changes include:

- **Static, browser-only architecture**: Runs as a plain static site (no backend required).
- **Modular ES modules**: Code organized under `js/` modules rather than a single script blob.
- **Persistent settings**: User settings and custom stream sources are stored via `localStorage`.
- **Configurable panels**: Panels can be toggled, reordered, and persisted.
- **Live stream handling upgrades**:
  - Supports multiple stream types (direct YouTube video IDs, channel-live embeds, and “attempt embed” for `/live` pages).
  - Defaults are geared toward more stable **channel-based live embeds**.
- **Tooltip system fix**: Tooltips moved away from CSS-only pseudo-elements (which were getting clipped) to a JS-driven body-level tooltip approach.
- **UI/UX refinements**: Wider settings modal sections, better hover behavior, and additional small layout tweaks.
- **Repository hygiene for GitHub Pages**:
  - Dev-only artifacts like `node_modules/` are ignored.
  - Optional test files can be removed.
  - Archived/unused code moved under `archive/`.

## Development

- Install deps (optional; only needed for local serving):
  - `npm install`
- Run locally:
  - `npm start`
  - Serves on `http://localhost:5173`

## GitHub Pages deployment

Because this is a static site, GitHub Pages can serve it directly:

- Ensure the repo contains only the deployable assets you want (typically `index.html`, `styles.css`, and `js/`).
- In GitHub: **Settings → Pages → Build and deployment** → select your branch/folder.

## Notes on embeds

Some embeds (especially YouTube `/live` landing pages) may fail due to YouTube’s embed restrictions or browser privacy features (Firefox Enhanced Tracking Protection can also impact playback).
