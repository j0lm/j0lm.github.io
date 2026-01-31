# j0lm.github.io

Personal site. Single-file, no build step. Everything lives in `index.html`.

## Aesthetic

Minimal terminal vibe. The page content is rendered inside a `<pre>` tag styled to look like a JSON file. Keep everything lowkey — no flashy UI, no unnecessary chrome. When adding interactive elements, make them subtle and unobtrusive.

## Structure

- `index.html` — the entire site. Styles, markup, and JS all inline.
- `CHANGELOG.md` — tracks changes. Uses Keep a Changelog format. Update the `[Unreleased]` section when adding or changing features.

## Theming

Colors are driven by two CSS custom properties on `:root`:

- `--text-color` (default `#cdbe78`) — used by body, links, the color toggle icon, and the color picker menu.
- `--bg-color` (default `#202020`) — used by body and the color picker menu background.

All color references in the CSS use these variables. Link hover uses `filter: brightness(1.15)` instead of a hardcoded color so it adapts automatically.

## Color Picker

A subtle 10px circle icon is fixed to the top-right corner (`#color-toggle`). Clicking it opens a small menu (`#color-menu`) with two native `<input type="color">` pickers for text and background. The menu border and input borders use `color-mix()` to stay faded. Clicking outside closes the menu.

## Adding a Project

Projects are listed inside the `<pre>` JSON block as objects in the `"projects"` array. Each project has:

- `name` — the project name, wrapped in an `<a>` tag linking to it
- `description` — what the project does
- `status` — e.g. `maintained`, `unmaintained`
- `notes` — (optional) any open issues or observations
