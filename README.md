# AI Workshop — opencode

A hands-on workshop introducing [opencode](https://opencode.ai/), the open-source agentic coding CLI, and its free model offerings via [opencode zen](https://opencode.ai/docs/zen/). Designed for developers who are comfortable with the terminal and git but new to agentic coding tools. By the end, you will have opencode installed, connected to a free model, and you will have completed three guided challenges.

## Prerequisites

- A terminal (a modern emulator such as WezTerm, Alacritty, Ghostty, or Kitty is recommended)
- `git`
- Node.js 20+ (only required if you install opencode via `npm`)
- An internet connection to download the installer and reach model providers

## Fork & clone this repo

You will commit your challenge work into your own fork — not this upstream repo.

1. Open [github.com/codebar/ai-workshop-opencode](https://github.com/codebar/ai-workshop-opencode) and click **Fork** (top right). Leave the defaults and confirm.
2. Copy the clone URL from your fork (green **Code** button), then clone it:
   ```bash
   git clone git@github.com:<your-username>/ai-workshop-opencode.git
   cd ai-workshop-opencode
   ```
   Prefer HTTPS? Use `https://github.com/<your-username>/ai-workshop-opencode.git` instead.
3. _(Optional)_ Add the upstream so you can pull future updates from codebar:
   ```bash
   git remote add upstream https://github.com/codebar/ai-workshop-opencode.git
   ```

GitHub's full fork docs: <https://docs.github.com/get-started/quickstart/fork-a-repo>.

## Quick start

1. **Fork and clone** this repo (see above).
2. Pick your OS in [`docs/setup/`](docs/setup/) and follow the install guide.
3. Skim [`docs/setup/commands.md`](docs/setup/commands.md) for the keybindings you will use during the session.
4. Open [`docs/slides/opencode_session_one.md`](docs/slides/opencode_session_one.md) and follow along with the workshop.

## Index

### Setup
- [macOS](docs/setup/guide_macos.md)
- [Windows](docs/setup/guide_windows.md)
- [Linux](docs/setup/guide_linux.md)
- [Commands reference](docs/setup/commands.md) — switch agents, switch models, manage sessions
- [Models](docs/setup/models.md) — free opencode zen models vs. GPT / Claude

### Slides
- [Session one](docs/slides/opencode_session_one.md) — intro to opencode (Marp deck)
- [How to preview slides](docs/slides/README.md)

### Challenges
- [Challenge one](docs/challenges/challenge_one.md)
- [Challenge two](docs/challenges/challenge_two.md)
- [Challenge three](docs/challenges/challenge_three.md)

## License

See [LICENSE](LICENSE).
