# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the Apps

No build step required. Open either file directly in a browser:

```
# Windows
start calculator.html
start demand-planning.html

# Or simply double-click the file in Explorer
```

## Repository Structure

Two standalone, zero-dependency HTML applications (HTML + CSS + vanilla JS in a single file each):

- **`calculator.html`** — Standard calculator. State lives in four module-level variables: `current`, `previous`, `op`, `shouldResetScreen`. Keyboard events are bound via a single `keydown` listener on `document`.
- **`demand-planning.html`** — "DemandIQ" demand planning dashboard. Depends on Chart.js loaded from CDN (`cdn.jsdelivr.net`). UI is tab-based (Dashboard / Products / Forecast / Inventory / Orders); tab switching is handled by toggling `.active` on `.section` elements. CSS design tokens are defined as custom properties on `:root` (`--bg`, `--surface`, `--surface2`, `--border`, `--accent`, `--accent2`, `--success`, `--warning`, `--danger`, `--text`, `--muted`).

## Architecture Notes

- All logic, styles, and markup are co-located in each HTML file — there is no separate JS or CSS file.
- Both apps are entirely client-side; there is no server, no API, and no persistent storage.
- `demand-planning.html` requires an internet connection to load Chart.js from the CDN.
