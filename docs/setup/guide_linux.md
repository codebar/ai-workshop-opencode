# Setup — Linux

> Tested on Ubuntu 22.04+, Fedora 39+, and Arch.

## 1. Prerequisites

- **Terminal:** any modern emulator works (GNOME Terminal, Konsole, WezTerm, Alacritty, Ghostty, Kitty).
- **git:** `git --version`. Install via your package manager (`sudo apt install git`, `sudo dnf install git`, `sudo pacman -S git`).
- **Node.js 20+** (only needed for the `npm` install path): `node --version`. Install via [nvm](https://github.com/nvm-sh/nvm) for the smoothest experience across distros.

## 2. Install opencode

Pick one of the following.

**Universal installer (recommended):**

```bash
curl -fsSL https://opencode.ai/install | bash
```

The script downloads a native binary, places it in `~/.local/bin` (or similar), and patches your shell config. Restart your shell or `source ~/.bashrc` / `~/.zshrc` after installation.

**Arch (AUR):**

```bash
paru -S opencode-bin       # or yay -S opencode-bin
```

**Homebrew on Linux:**

```bash
brew install anomalyco/tap/opencode
```

**npm (any distro):**

```bash
npm install -g opencode-ai
```

## 3. Verify

```bash
opencode --version
```

If you see `command not found`, make sure `~/.local/bin` is on your `PATH` (the installer adds this for most shells — restart the terminal).

## 4. First run

```bash
opencode
```

In the TUI, connect to opencode zen so you can use the free model tier:

1. Type `/connect` and select **opencode zen**.
2. Complete the browser auth flow.
3. Press `f2` (or type `/models`) and pick a free model — `big-pickle` is a solid default.
4. Send a test prompt: `list the largest files in this folder`.

## 5. Next steps

- Keybindings: [`commands.md`](commands.md)
- Model comparison: [`models.md`](models.md)
- Slides: [`../slides/opencode_session_one.md`](../slides/opencode_session_one.md)
