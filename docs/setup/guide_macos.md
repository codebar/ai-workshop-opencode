# Setup — macOS

> Tested on macOS 13+ with both Apple Silicon and Intel.

## 1. Prerequisites

- **Terminal:** the built-in Terminal works, but a modern emulator (WezTerm, Alacritty, Ghostty, or Kitty) gives the best opencode TUI experience.
- **git:** `git --version` should print a version. Install via `xcode-select --install` if missing.
- **Node.js 20+** (only needed for the `npm` install path): `node --version`. Install via [nvm](https://github.com/nvm-sh/nvm) or `brew install node`.

## 2. Install opencode

Pick one of the following. The universal installer is the safest if you do not already use Homebrew.

**Universal installer (recommended):**

```bash
curl -fsSL https://opencode.ai/install | bash
```

The script downloads a native binary and adds it to your `PATH` via `.zshrc` / `.bashrc`. Restart your shell after installation.

**Homebrew:**

```bash
brew install anomalyco/tap/opencode
```

**npm:**

```bash
npm install -g opencode-ai
```

## 3. Verify

```bash
opencode --version
```

You should see a version string. If `command not found`, restart your terminal so the updated `PATH` takes effect.

## 4. First run

```bash
opencode
```

The TUI opens. Connect a provider — for the workshop we will use opencode zen so everyone has access to free models:

1. Type `/connect` and pick **opencode zen**.
2. Follow the browser auth flow it opens.
3. Type `/models` (or press `f2`) and pick a free model — `big-pickle` is a good starting default.
4. Send a test prompt: `summarize the contents of this directory`.

If everything responds, you are ready for the session.

## 5. Next steps

- Skim the keybindings in [`commands.md`](commands.md).
- Compare models in [`models.md`](models.md).
- Open the deck: [`../slides/opencode_session_one.md`](../slides/opencode_session_one.md).
