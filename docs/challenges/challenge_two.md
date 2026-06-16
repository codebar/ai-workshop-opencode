# Challenge 2 — Space Invaders: an arcade in an afternoon

**Level:** intermediate
**Estimated time:** 40–60 min
**Objective:** build a classic arcade game like *Space Invaders* from scratch, practice the iteration cycle, and learn to use `SPEC.md`, sub-agents, and the `frontend-design` skill to level up visually.

## Context

You're going to recreate the typical 80s arcade: a ship at the bottom of the screen, waves of aliens descending from above, bullets going up, and score. Only HTML, CSS, and a `<canvas>` with vanilla JavaScript. The goal is not just that it "works," but that it feels good to play: rhythm, impact effects, and increasing difficulty.

The challenge covers:

- Architecture of a game loop with `requestAnimationFrame`.
- Rendering on `<canvas>` (no external sprites, only shapes).
- Simple collision detection (AABB).
- Game states (intro → playing → game over).
- Iteration guided by feedback (game-feel, not just logic).

## Setup

```bash
mkdir invaders
cd invaders
opencode
```

Recommended for this challenge: a medium to high reasoning model (for example **Mimo 2.5 Pro** via OpenCode Zen, or **GPT-5.5 medium** if you have ChatGPT Plus connected). Smaller models tend to struggle with collision logic.

## Prompt

Copy and paste this prompt into OpenCode. It's designed to start in **Plan mode** first, validate the design, and then switch to Build:

````text
Build an arcade game on a single web page inspired by Space Invaders.

Required stack:
- HTML, CSS, and vanilla JavaScript
- Render on a single <canvas>
- No external dependencies, no image sprites (shapes drawn by code)
- Three files maximum: index.html, styles.css, game.js

Mechanics:
- Player ship at the bottom, moves with LEFT and RIGHT arrow keys
- Shooting with SPACEBAR (limited firing rate: max one bullet every 220 ms)
- Initial grid of 5 rows x 8 columns of aliens at the top
- Aliens move as a block left/right and drop one row when touching edge
- Every so often a random alien shoots downward (adjustable firing rate)
- AABB collision detection between bullets and aliens, and between enemy bullets and ship
- Each destroyed alien scores points based on its row (higher up = more points)
- 3 lives. Lose a life on impact, with brief invulnerability (~1 s)
- When all aliens are eliminated, a new wave begins that's faster

Game states:
- INTRO: screen with title "INVADERS", high score display, and "Press SPACE to start"
- PLAYING: HUD with score, lives, and current wave in the upper corner
- GAME OVER: screen with "GAME OVER", final score, and "Press SPACE to retry"
- High score persists in localStorage

Game feel (important):
- Small screen shake when destroying an alien
- Brief white flash on ship impact
- Simple particles (4-8 pixels) when destroying aliens
- Sounds generated with WebAudio (no files): pew on shooting, hit on impact, explosion on death
- Difficulty curve: each wave speeds up movement by 10%

Visual design:
- Retro CRT aesthetic, but with soft and modern colors
- Almost black background (#0E1116), ship in sage (#84B59F), aliens in eucalyptus (#69A297), and slate (#50808E)
- Monospaced typography (system-ui mono)
- No gradients; sharp pixel-perfect edges
- Canvas 800x600 logical, scaled responsively while maintaining aspect ratio

Deliverables:
1. index.html, styles.css, game.js
2. SPEC.md with the final specification (mechanics, states, game feel, acceptance criteria)
3. AGENTS.md with project rules (vanilla, no dependencies, single canvas, no external sprites)

First, give me a plan in five steps without touching any files.
When you say "go", we move to Build.
````

## Suggested steps during the exercise

1. **Plan:** read the plan the agent proposes, adjust if you want (for example, "I don't care about screen shake in the first version, prioritize collisions").
2. **Build:** respond `go` and let it execute. Meanwhile, in another tab, open the file explorer to watch how it creates `game.js`.
3. **Start the game:**
   ```text
   !npx serve .
   ```
4. **Iterate with short prompts.** Queue up several without waiting between them:
   - "The firing rate feels slow, lower it to 180 ms."
   - "When the player holds spacebar, it should fire continuously respecting the firing rate."
   - "Add a power-up that appears at random and grants double cannon for 6 seconds."
   - "Improve the retro look using the frontend-design skill."
5. **Use sub-agents for review.** In a single prompt:
   ```text
   In parallel:
   @reviewer review game.js and tell me the logic bugs you see
   @general evaluate game loop performance on mobile
   When both finish, consolidate an improvement plan.
   ```
6. **Commit:**
   ```text
   !git init && git add . && git commit -m "feat: invaders mvp"
   ```

## Acceptance criteria

- [ ] The game starts, is playable with keyboard, and ends when you lose 3 lives.
- [ ] Score and high score appear on screen and persist when reloading.
- [ ] Collisions work in both directions (bullet→alien and bullet→ship).
- [ ] Difficulty increases when changing waves.
- [ ] No external sprites: everything is drawn with code.
- [ ] The project includes `SPEC.md` and `AGENTS.md`.

## Extensions (if you have time left)

- Add a boss alien that appears every N waves, with multiple lives and different movement pattern.
- Gamepad support: read the Gamepad API and map d-pad + A button.
- Create a simple *replay* that records player inputs and allows playback.
- Convert the HUD into a reusable component and document the design in `DESIGN.md`.