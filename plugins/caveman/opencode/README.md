# Caveman — OpenCode Plugin

Ultra-compressed communication mode for [OpenCode](https://opencode.ai). Cuts ~75% of output tokens while keeping full technical accuracy.

## Install

**1. Copy the plugin to your global OpenCode plugins directory:**

```bash
mkdir -p ~/.config/opencode/plugins
cp caveman.js ~/.config/opencode/plugins/caveman.js
```

**2. Copy the command file to enable `/caveman` slash command support:**

```bash
mkdir -p ~/.config/opencode/commands
cp commands/caveman.md ~/.config/opencode/commands/caveman.md
```

**3. Restart OpenCode.**

No changes to `opencode.json` required — files in `~/.config/opencode/plugins/` are loaded automatically.

## Usage

| Trigger | Effect |
|---------|--------|
| `/caveman` | Enable caveman mode (full intensity) |
| `/caveman lite` | Enable lite intensity |
| `/caveman full` | Enable full intensity (default) |
| `/caveman ultra` | Enable ultra intensity |
| `caveman mode` | Enable via natural language |
| `talk like caveman` | Enable via natural language |
| `less tokens` | Enable via natural language |
| `stop caveman` | Disable caveman mode |
| `normal mode` | Disable caveman mode |

## Intensity Levels

| Level | Description |
|-------|-------------|
| **lite** | No filler or hedging. Keep articles and full sentences. Professional but tight. |
| **full** | Drop articles, fragments OK, short synonyms. Classic caveman. |
| **ultra** | Maximum compression. Abbreviate (DB/auth/config/req/res/fn/impl), arrows for causality (X → Y). |

## Notes

- Plugin only fires on TUI input (`tui.prompt.append`). Web and IDE interfaces not supported.
- Caveman mode persists until you say "stop caveman" or "normal mode", or the session ends.
- Code blocks, git commits, and PR descriptions are always written normally.
- Security warnings and irreversible action confirmations revert to normal prose automatically.
