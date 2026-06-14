# opencode commands & keybindings

A quick reference for the keys you will use during the workshop. These are the **defaults** — every binding is rebindable in `opencode.json`.

> **Leader key:** the default leader is **`ctrl+x`**. When you see `<leader>l` below, that means: press `ctrl+x`, release, then press `l`.

## Switch between agents

| Action | Key |
| --- | --- |
| Cycle to the next agent | `tab` |
| Cycle to the previous agent | `shift+tab` |
| Open the agent picker | `<leader>a` (`ctrl+x` then `a`) |

An **agent** is a named persona with its own system prompt, tool set, and optional model override. Define them in your project's `AGENTS.md` (created with `/init`) or in `opencode.json`.

## Switch between models

| Action | Key / Command |
| --- | --- |
| Cycle to the next recent model | `f2` |
| Cycle to the previous recent model | `shift+f2` |
| Open the model picker | `<leader>m` (`ctrl+x` then `m`) or type `/models` |
| Set a default model in config | `"model": "provider/model_id"` in `opencode.json` |

Model IDs use the `provider_id/model_id` format, for example:

```json
{ "model": "opencode-zen/big-pickle" }
```

## Check & manage sessions

| Action | Key / Command |
| --- | --- |
| List sessions | `<leader>l` (`ctrl+x` then `l`) |
| Open the session timeline | `<leader>g` (`ctrl+x` then `g`) |
| Rename the current session | `ctrl+r` |
| Generate a shareable session link | `/share` |
| Undo the last change | `/undo` |
| Redo a reverted change | `/redo` |

## Useful slash commands

| Command | What it does |
| --- | --- |
| `/init` | Scan the project and create `AGENTS.md` with project context |
| `/connect` | Add or switch the API provider for the current session |
| `/models` | Open the model picker |
| `/share` | Create a shareable link to the current session |
| `/undo` · `/redo` | Step backward / forward through the session's changes |

> Always verify the exact bindings against the live docs before each workshop: <https://opencode.ai/docs/keybinds/>.
