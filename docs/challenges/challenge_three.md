# Challenge 3 — Todo List Pro with backend and SQLite

**Level:** advanced
**Estimated time:** 60–90 min
**Objective:** build a real fullstack web application with SQLite persistence, practice the complete OpenSpec workflow (SPEC.md → AGENTS.md → sub-agents), and learn to work with multiple layers at once (frontend, API, database).

## Context

The classic Todo List, but built the way a professional team would: REST API backend, SQLite database, decoupled frontend, and a minimum of care for security and tests. It's the perfect challenge to show how OpenCode shines in multi-layer projects.

The challenge covers:

- Client-server architecture in a simple monorepo.
- REST endpoints with input validation.
- Persistence in SQLite (a single `data.db` file).
- Live AGENTS.md: rules that the agent respects between iterations.
- Division of work into sub-agents (explore, security, reviewer).
- Basic automated tests.

## Setup

```bash
mkdir todolist-pro
cd todolist-pro
opencode
```

Recommended: **Mimo 2.5 Pro** or **Qwen 3.6** for execution via OpenCode Zen, planning with **GPT-5.5 high** if you have ChatGPT Plus connected. The challenge benefits greatly from a good planner.

## Prompt

Copy and paste this prompt into OpenCode, ideally starting in **Plan mode**:

````text
Build a fullstack Todo List application with SQLite persistence.

Folder structure:
- /server      → Node.js backend + SQLite (no Express if possible, use native http or minimal dependency like Hono)
- /web         → vanilla frontend (HTML + CSS + JS, no frameworks)
- /db          → data.db file and SQL migrations
- AGENTS.md    → project rules
- SPEC.md      → live specification
- README.md    → how to start and test

Backend:
- Runtime: Node.js 24 or Bun (agent chooses and documents in AGENTS.md)
- REST API at /api with the following endpoints:
  - GET    /api/notes              → paginated list (?page=1&limit=20)
  - POST   /api/notes              → creates a note
  - GET    /api/notes/:id          → detail
  - PATCH  /api/notes/:id          → updates title, content, or status (done)
  - DELETE /api/notes/:id          → logical delete (soft delete, deleted_at column)
- Input validation: required title 1-120 chars; optional content max 5000 chars
- Consistent JSON responses: { ok: true, data } or { ok: false, error: { code, message } }
- Error handling with correct status codes (400, 404, 409, 500)
- CORS open to localhost in development

Database:
- SQLite (better-sqlite3 or bun:sqlite driver)
- File at /db/data.db
- Initial migration at /db/migrations/001_init.sql with the notes table:
  id INTEGER PRIMARY KEY AUTOINCREMENT
  title TEXT NOT NULL
  content TEXT
  done INTEGER NOT NULL DEFAULT 0
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP
  updated_at DATETIME DEFAULT CURRENT_TIMESTAMP
  deleted_at DATETIME
- Migrations apply automatically when starting the server

Frontend:
- index.html with:
  - List of notes, filterable by status (all / pending / completed)
  - Inline form to create new note (title + content)
  - Inline editing when clicking title or content
  - Button to mark as done (accessible checkbox)
  - Delete button with discreet confirmation
  - Friendly empty state when there are no notes
- styles.css with the soft sage palette from the workshop:
  cream background #F5F1E8, sage accents #84B59F, slate #50808E, text #2E3A42
- app.js with fetch to /api, error handling, and visual feedback
- No frameworks or libraries; one template helper allowed (template literals)

Tests (minimal):
- API tests with node:test or bun:test
- Coverage: create, list paginated, update, delete, error validations
- Single command: `bun test` or `npm test`

Quality:
- Consistent code style (Prettier defaults)
- README with: requirements, start (single command), endpoints, curl examples
- AGENTS.md with all decisions (runtime, SQLite driver, no framework, no frontend framework)
- SPEC.md with objectives, entities, endpoints, and acceptance criteria

Steps before starting to program:
1. Give me a numbered plan of 7 to 10 steps without touching files.
2. List the decisions I need to confirm (runtime, driver, single startup command).
3. Wait for me to say "go" before starting to write code.
````

## Suggested steps during the exercise

1. **Plan and decisions.** Review the plan and confirm key decisions (runtime, driver). This avoids rewrites.
2. **Build with sub-agents.** When implementation starts, divide the work:
   ```text
   In parallel:
   @explore map what files you'll create and in what order
   @general assess API security risks (SQL injection, CORS, validation)
   ```
3. **Build by layers.** Explicitly suggest to the agent to go layer by layer:
   - Migration and data access module.
   - Endpoints one by one with their tests.
   - Minimal frontend connected to backend.
   - Visual polish and empty states.
4. **Iterate with curl examples.** When the backend is ready, test in Shell Mode:
   ```text
   !curl -s http://localhost:3000/api/notes | jq
   !curl -s -X POST http://localhost:3000/api/notes -H 'Content-Type: application/json' -d '{"title":"First note","content":"hello"}'
   ```
5. **Save tokens.** For spot fixes, use `@server/routes/notes.js` or other specific files in the input.
6. **Close with a clean commit:**
   ```text
   /supercommit feat: todo list MVP fullstack
   ```
   Or manually:
   ```text
   !git init && git add . && git commit -m "feat: todo list MVP fullstack"
   ```

## Acceptance criteria

- [ ] `bun dev` (or `npm run dev`) starts backend and frontend with a single command.
- [ ] All 5 REST endpoints work with consistent JSON responses.
- [ ] Database persists after restarting the server.
- [ ] Delete is logical (note isn't lost from database).
- [ ] Frontend shows empty states and errors in a friendly way.
- [ ] Tests pass (`bun test` or `npm test`).
- [ ] Repository includes `SPEC.md`, `AGENTS.md`, and `README.md`.
- [ ] No obvious vulnerabilities (SQL injection, XSS when rendering content).

## Extensions (if you have time left)

- **Tags:** add a tag system per note and a tag filter in the frontend.
- **Search:** `GET /api/notes?q=text` endpoint with full-text search using SQLite's FTS5 extension.
- **Basic auth:** middleware with Bearer token and single user configurable by `.env`.
- **Export / Import:** endpoints to download and upload JSON backups.
- **PWA:** convert the frontend into an installable PWA with manifest and offline-first service worker.
- **DESIGN.md:** document the design system used and ask the AI to respect those tokens in future iterations.