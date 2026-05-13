# Bedrock-Addon-Studio
Alpha Version For Bedrock Addon Studio
---

# Bedrock Addon Studio

**Bedrock Addon Studio** is a comprehensive, all-in-one web-based IDE for creating, managing, and exporting Minecraft: Bedrock Edition addons. It provides a visual, code-first environment that bridges the gap between complex JSON structures and intuitive design, enabling creators to build behavior packs, resource packs, and scripts without leaving the browser.

![Version](https://img.shields.io/badge/version-2.0-green) ![Bedrock](https://img.shields.io/badge/Bedrock-1.21-blue) ![Script API](https://img.shields.io/badge/Script%20API-1.13-gold)

---

## 🚀 Key Features

- **📁 Full Addon Structure** – Visual editor for all core components: `manifest.json`, entities, items, blocks, recipes, loot tables, spawn rules, and more.
- **🎨 Resource Pack Tools** – Texture registration, sound definitions, particle effects, animations, and language file generation.
- **🧠 Script API Integration** – Ready-to-use TypeScript/JavaScript templates for `@minecraft/server`, UI forms, GameTest, HTTP requests, dynamic properties, and scoreboards.
- **⚡ Smart Code Generation** – One-click generation of valid JSON based on user inputs. No manual syntax errors.
- **🔍 Built-in Validator** – JSON syntax checker with common Bedrock-specific warnings (identifiers, `format_version`, experimental flags).
- **📚 Comprehensive References** – Molang expression library, event browser, schema viewer, version history, and best-practice checklists.
- **📦 Export Ready** – Direct guidance for packaging `.mcaddon` and `.mcpack` files.

---

## 🧩 Core Modules

### Behavior Pack Development
| Module | Description |
|--------|-------------|
| **Entities** | Configure health, speed, AI goals, combat components, loot tables, and spawn conditions. |
| **Items** | Define stack size, durability, cooldowns, food/weapon/armor behaviors, and texture mapping. |
| **Blocks** | Set hardness, blast resistance, light emission, states, and permutations. |
| **Recipes** | Build shaped, shapeless, furnace, smoker, and campfire recipes with a visual grid editor. |
| **Loot Tables** | Create drop pools with weighted entries and count ranges. |
| **Spawn Rules** | Control biome, height, light level, and group size for custom mob spawning. |

### Resource Pack Features
| Module | Description |
|--------|-------------|
| **Textures** | Generate `item_texture.json` and `terrain_texture.json` with texture size guidelines. |
| **Sounds** | Edit `sound_definitions.json` with category and pitch randomization support. |
| **Animations** | Define bone keyframes and Molang-driven rotations for entity animations. |
| **Languages** | Manage `.lang` localization strings for multiple locales. |
| **Particles** | Custom particle emitter configuration (rate, lifetime, speed, appearance). |

### Scripting & Tooling
- **Code Generator** – Nine TypeScript templates: event listeners, chat commands, tick loops, UI forms, GameTest suites, HTTP client, dynamic properties, scoreboard API, and schedulers.
- **Event Browser** – Searchable list of `world.afterEvents`, `beforeEvents`, and `system` events. One-click copy for subscription.
- **Molang Reference** – Query functions, math utilities, and variable scope explanations.
- **JSON Validator** – Syntax parsing + validation rules specific to Bedrock addons.
- **Schema Viewer** – Quick lookup of required fields for entities, items, blocks, recipes, manifests, and animations.

---

## 🛠️ How It Works

1. **Select a panel** from the sidebar (Manifest, Entities, Items, etc.).
2. **Fill in the intuitive form fields** – each input is mapped directly to the corresponding JSON property.
3. **Click “Generate” or watch live updates** – the output JSON panel updates in real-time.
4. **Copy the generated JSON** or use the built-in validator to check for errors.
5. **Use the script templates** to quickly implement advanced gameplay logic using `@minecraft/server`.
6. **Export your addon** – package the Behavior Pack and Resource Pack together as an `.mcaddon`.


---

## 🧪 Supported API Versions

| Module | Version | Status |
|--------|---------|--------|
| `@minecraft/server` | 1.13.0 | Stable |
| `@minecraft/server-ui` | 1.3.0 | Stable |
| `@minecraft/server-net` | 1.0.0-beta | Beta |
| `@minecraft/server-admin` | 1.0.0-beta | Beta |
| GameTest Framework | 1.0.0-beta | Beta |

**Experimental Features** – Holiday Creator Features, Custom Biomes, Upcoming Creator Features, Beta APIs.

---

## 📖 Documentation & Resources

The tool includes direct links to:
- [Microsoft Creator Documentation](https://learn.microsoft.com/en-us/minecraft/creator/)
- [bedrock.dev](https://bedrock.dev) – API Reference
- [wiki.bedrock.dev](https://wiki.bedrock.dev) – Community Wiki
- [Mojang Bedrock Samples](https://github.com/Mojang/bedrock-samples)
- Vanilla Behavior / Resource Pack downloads

---

## ✅ Development Checklist

1. Create `manifest.json` (both packs) with unique UUIDs and `min_engine_version`.
2. Set up folder structure (BP/ and RP/).
3. Define content JSON (entities, items, blocks) with proper `format_version`.
4. Register textures and geometries in `item_texture.json` and `terrain_texture.json`.
5. Add language strings to `RP/texts/en_US.lang` and list locales in `languages.json`.
6. Write scripts in `BP/scripts/` (TypeScript → JavaScript).
7. Package as `.mcaddon` (zip both packs → rename).

---

## ⚠️ Common Pitfalls (Validator Checks)

- Missing `format_version` at root.
- Identifier lacks `namespace:` prefix.
- Trailing commas before closing braces/brackets.
- Wrong `min_engine_version` for the feature used.
- Component paths missing `minecraft:` prefix.
- Missing `description.identifier` inside the root key.

---

## 🧑‍💻 Target Audience

- **Bedrock Addon Developers** – from beginners to advanced creators.
- **Map Makers** – needing custom items, blocks, or entities.
- **Server Owners** – adding GameTest frameworks or script-based mechanics.
- **Educators** – teaching Minecraft modding with visual tooling.

---

## 📦 Export Format

| Extension | Contents |
|-----------|----------|
| `.mcpack` | Single pack (BP or RP only) |
| `.mcaddon` | BP + RP combined in one zip |
| `.mcworld` | World with embedded packs |
| `.mctemplate` | World template for Marketplace |

---

## 🔧 Technical Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6)
- **UI**: Custom design system with dark theme, CSS Grid, Flexbox
- **Fonts**: Outfit (sans-serif) + JetBrains Mono (code)
- **Icons**: Font Awesome 6.5.0
- **JSON Processing**: Native `JSON.stringify` / `JSON.parse` with custom syntax highlighting
- **No Build Step** – Single HTML file, runs entirely in the browser.

---

## 💡 Usage Tips

- Use the **live manifest generator** to toggle script modules and capabilities – dependencies auto-update.
- The **entity builder** includes a tab for AI goals (melee attack, ranged attack, random walk) with priority settings.
- **Recipe grid** supports dynamic shaping – any character in the 3×3 grid becomes a key.
- **Script templates** are ready to paste into `BP/scripts/main.ts` – they include imports and type hints.
- **Event browser** lets you copy exact event names for subscription.
- **Quick templates** in the Code Generator cover advanced structures like features, biomes, and render controllers.

---

## 🧪 Validation & Best Practices

The built-in JSON validator checks for:
- Valid JSON syntax (no stray commas, quotes balanced).
- Presence of `format_version`.
- Recognized root wrapper (`minecraft:entity`, `minecraft:item`, etc.).
- Identifier format (must contain a colon).

It also highlights common mistakes with descriptive warnings, making it a useful learning tool for new addon creators.

---

## 🐞 Report a Bug

Found an issue or have a suggestion? Your feedback helps improve Bedrock Addon Studio!

### How to Report

| Method | Link / Instructions |
|--------|---------------------|
| **Discord Server** | [Join our Discord](https://discord.com/invite/m2UdYmjyXE) – Report bugs in `#report` |
| **GitHub Issues** | *(Coming soon)* |
| **Direct Message** | Contact the developer via Discord DM |

### What to Include in Your Bug Report

To help us fix issues quickly, please include:

📋 Bug Description:
(What happened? What did you expect to happen?)

🔄 Steps to Reproduce:

Go to...

Click on...

See error...

📸 Screenshots/Recording:
(If applicable)

🖥️ Environment:

Browser: (Chrome/Firefox/Safari/Edge)

Device: (PC/Mac/Mobile)

OS: (Windows/MacOS/iOS/Android)

📦 Affected Panel:
(Manifest / Entities / Items / Blocks / Scripts / etc.)

🔧 Generated JSON (if relevant):
(Paste the output that caused the issue)
### Known Issues & Roadmap

| Issue | Status |
|-------|--------|
| None currently reported | ✅ Active monitoring |

**Feature requests are also welcome!** Suggest new panels, templates, or tools you'd like to see.


---

## 🙏 Contributing

Contributions are welcome! If you'd like to help improve Bedrock Addon Studio:

1. **Report bugs** via Discord (link above)
2. **Suggest features** in the `#suggestions` channel
3. **Share templates** – useful JSON snippets or script patterns
4. **Spread the word** – tell other addon creators about the tool

---

## 📄 License

This tool is provided as an open-source reference implementation for Bedrock addon development.  
All generated JSON output follows Mojang's specification for Minecraft: Bedrock Edition.

---

**Start building your next Bedrock addon today – no installation, no setup, just your browser and creativity.**

**🐞 Found a bug?** [Report it on Discord](https://discord.com/invite/m2UdYmjyXE)
