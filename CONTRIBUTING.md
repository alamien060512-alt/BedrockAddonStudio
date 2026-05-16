# Contributing to Minecraft Addon Builder

Thanks for your interest in contributing! This tool is a single-file HTML app for generating Minecraft Bedrock Edition `.mcaddon` packages. Contributions of all kinds are welcome.

---

## Getting Started

No build system, no dependencies, no `npm install`. Just open `index.html` in a browser and you're running the app.

To contribute:

1. Fork the repository
2. Make your changes directly in `index.html`
3. Test in Chrome or Firefox (Chrome recommended — closest to Minecraft's WebView)
4. Open a pull request with a clear description of what you changed and why

---

## Project Structure

Everything lives in `index.html`. The major sections inside the file are marked with block comments:

- **Styles** — CSS variables, layout, cards, toggles, syntax highlighting
- **HTML panels** — Manifest, Entities, Items, Blocks, Recipes, Loot Tables, Spawn Rules, Scripts, Textures, Sounds, Animations, Particles
- **`hl(json)`** — JSON syntax highlighter (token-by-token, single-pass)
- **`genManifest()`** — Builds the BP manifest object and stores it in `_lastManifestObj`
- **`exportAddon()`** — Reads the Include in Export checkboxes, assembles JSZip, triggers download

---

## What to Work On

### Bug fixes
- If a generated JSON file is malformed or fails to import into Minecraft, please open an issue with the exact steps to reproduce and the pack type used.

### New panel sections
If you're adding a new BP or RP section (e.g. feature rules, render controllers):
1. Add the panel HTML alongside the existing panels
2. Add a generator function following the `gen*()` naming pattern
3. Add an `inc-*` checkbox to the **Include in Export** card in the Manifest panel
4. Gate the export in `exportAddon()` behind the new checkbox — follow the pattern of existing sections

### Manifest accuracy
The `genManifest()` function targets `@minecraft/server 1.13.0` and engine version `1.21.0`. If these become outdated, update the defaults in `genManifest()` and the dropdown options in the Manifest panel HTML.

---

## Code Style

- **No frameworks, no bundler.** Vanilla JS only.
- Use `const` and `let`, never `var`.
- Helper: `$('element-id')` is shorthand for `document.getElementById`.
- JSON is always serialized with `JSON.stringify(obj, null, 2)` — never built by hand as a string.
- The manifest object must always go through `_lastManifestObj` so the exporter gets clean JSON, not innerHTML.
- The `hl()` highlighter must stay single-pass — do not add sequential `.replace()` chains that operate on already-tagged output.

---

## Testing Checklist

Before opening a PR, verify:

- [ ] The manifest preview shows valid JSON with no `key>` artifacts
- [ ] Only checked sections appear in the exported `.mcaddon` zip
- [ ] The BP folder is absent when no BP sections are checked
- [ ] The RP folder is absent when no RP sections are checked
- [ ] The exported pack imports without errors in Minecraft Bedrock (test with a fresh world)
- [ ] The file works when opened directly from disk (no local server needed)

---

## Reporting Issues

Open an issue and include:

- What you selected / toggled in the UI
- The contents of the downloaded zip (folder names and file names are enough)
- Minecraft Bedrock version if the pack fails to import
- A screenshot if the preview panel looks wrong

---

## License

By contributing, you agree your changes will be released under the same license as the project.
