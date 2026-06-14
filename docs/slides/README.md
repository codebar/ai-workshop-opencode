# Slides

Workshop slide decks authored in [Marp](https://marp.app/) — plain Markdown with YAML frontmatter, rendered to HTML/PDF/PPTX.

## Preview locally

Install the Marp CLI once:

```bash
npm install -g @marp-team/marp-cli
```

Start a live-reloading preview server **from this folder** so the local [`.marprc.yml`](./.marprc.yml) is picked up automatically:

```bash
cd docs/slides
marp -s .
```

Open the URL it prints (usually `http://localhost:8080`) and pick `opencode_session_one.md`.

> The `.marprc.yml` enables raw HTML (`markdown.html: true`) so the deck's `<div class="benchmark">`, `<div class="flow">`, and two-column layouts render instead of being escaped to text.

## Export

Run from inside this folder so `.marprc.yml` is auto-loaded:

```bash
cd docs/slides
marp --pdf --allow-local-files opencode_session_one.md
```

For PPTX or standalone HTML, swap `--pdf` for `--pptx` or `--html`. `--allow-local-files` is required because the deck embeds `./assets/tui.png`.

## Theme

The deck uses the custom `codebar` theme defined in [`themes/codebar.css`](themes/codebar.css), inspired by [codebar.io](https://codebar.io/). It is wired up automatically via the `themeSet` entry in `.marprc.yml`.

The VS Code Marp extension picks it up once you add this to your workspace settings:

```json
"markdown.marp.themes": ["./docs/slides/themes/codebar.css"]
```

## Diagrams

Diagrams in this deck are built with plain HTML + CSS (see `.flow` and `.benchmark` rules in [`themes/codebar.css`](themes/codebar.css)) for pixel-precise sizing and consistent rendering across browsers and PDF export. No external diagram libraries are loaded.
