# Setup — Windows

> **WSL2 is strongly recommended.** opencode's TUI and tooling assume a Unix-like shell. The native Windows install works for most tasks, but a few features and many terminal emulators behave better inside WSL2 Ubuntu.

## 1. Prerequisites

- **Terminal:** [Windows Terminal](https://aka.ms/terminal) (built-in on Win11). Inside it, prefer a WSL Ubuntu profile.
- **WSL2 (recommended):** open PowerShell as admin and run `wsl --install`. Reboot, then launch Ubuntu and create a user.
- **git:** inside WSL run `sudo apt install git -y`; on native Windows install [Git for Windows](https://git-scm.com/download/win).
- **Node.js 20+** (only for the `npm` install path): inside WSL use [nvm](https://github.com/nvm-sh/nvm); on native Windows use [Volta](https://volta.sh/) or the [Node.js MSI](https://nodejs.org/).

## 2. Install opencode

### Inside WSL2 (recommended)

Open your Ubuntu shell and follow the Linux instructions — universal installer is easiest:

```bash
curl -fsSL https://opencode.ai/install | bash
```

Or:

```bash
npm install -g opencode-ai
```

### Native Windows (PowerShell)

**Scoop:**

```powershell
scoop install opencode
```

**Chocolatey:**

```powershell
choco install opencode
```

**npm:**

```powershell
npm install -g opencode-ai
```

## 3. Verify

```bash
opencode --version
```

If WSL says `command not found`, restart the shell so the updated `PATH` is picked up. On native Windows, open a new PowerShell window.

## 4. First run

```bash
opencode
```

In the TUI, connect to opencode zen to access free models:

1. Type `/connect` and pick **opencode zen**.
2. Complete the browser auth flow.
3. Press `f2` (or type `/models`) and select a free model — `big-pickle` is a good default.
4. Send a test prompt: `what files are in this folder?`.

## 5. Next steps

- Keybindings: [`commands.md`](commands.md)
- Model comparison: [`models.md`](models.md)
- Slides: [`../slides/opencode_session_one.md`](../slides/opencode_session_one.md)
