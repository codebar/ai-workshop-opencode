# Challenge 1 — The Impossible Invitation to Refuse

**Level:** beginner
**Estimated time:** 20–30 min
**Objective:** practice your first prompt in OpenCode, see the Plan → Build cycle, and learn to iterate with short feedback.

## Context

We're going to build a single-page mini web app: a fun invitation to hang out with a friend. The page has two buttons, **Yes** and **No**. The **No** button flees from the cursor so no one can click it. The **Yes** button leads to a second screen with a calendar of the current month where the invitee chooses a day and time.

The challenge covers:

- Project generation from scratch (HTML + CSS + JS, no dependencies).
- JavaScript interaction logic (button movement, view navigation).
- Rendering a dynamic calendar based on system date.
- Light persistence of final choice in `localStorage`.

## Setup

```bash
mkdir invitation
cd invitation
opencode
```

Connect your favorite model (`/connect` and `/models`). For this challenge, a free model like **MiniMax M** or **Big Pickle** is more than enough.

## Prompt

Copy and paste this prompt into OpenCode. It's designed to start in **Build mode**, but you can start in **Plan** if you want to see the proposal first:

````text
Create a single-page mini web application titled "Want to hang out one day?".

Required stack:
- HTML, CSS, and vanilla JavaScript
- No external dependencies, no build step, no frameworks
- Three files maximum: index.html, styles.css, app.js
- Compatible with current Chrome, Safari, and Firefox

Views:

VIEW 1 — Invitation
- Centered title: "Do you want to hang out one day?"
- Optional subtitle with a friendly and fun touch
- Two buttons below the title: "Yes" and "No"
- "Yes" button: main style (accent color, smooth hover, accessible visible focus)
- "No" button: secondary style, but with special behavior:
  - When the user's cursor gets close to the "No" button within ~80px, the button
    must jump to a random position within the visible viewport
  - Must never be clickable
  - On touch devices, as soon as the user touches the screen near the
    button, the button moves to another corner (no overflow or broken scroll)
- Clicking "Yes" navigates to VIEW 2 with a smooth transition (fade or slide)

VIEW 2 — Calendar and time
- Calendar of the CURRENT MONTH from the system, generated dynamically in JavaScript
- Header with the month name and year
- 7x6 grid with days, marking "today" with a different style
- Days before today appear disabled (no click)
- When selecting a day, a time selector appears below in 30-minute intervals
  between 09:00 and 22:00
- "Confirm" button that saves the choice to localStorage and displays a
  final message: "Great! See you on {day} at {time}."

Visual design:
- Soft palette: cream background (#F5F1E8), sage accents (#84B59F), and slate (#50808E)
- Sans-serif system typography (system-ui)
- Centered, responsive layout, mobile-first
- Smooth animations (transition: 200ms ease)
- Visible focus state for keyboard accessibility

Deliverables:
1. The three project files
2. A SPEC.md with the final specification (objective, stack, views, acceptance criteria)
3. A one-page README.md with how to start the project (npx serve .)

When you finish, do NOT install anything extra. Only run `npx serve .` and tell me what URL I can open it at.
````

## Suggested steps during the exercise

1. **Plan first (optional):** press `Tab` to enter Plan mode and paste the previous prompt with "Don't modify anything yet, give me the plan." Review the plan proposed by the agent.
2. **Build:** go back to Build (`Tab`) and let it execute.
3. **Start:**
   ```text
   !npx serve .
   ```
4. **Iterate with short feedback.** Examples you can paste one after another while the agent keeps working (task queue):
   - "The No button goes off viewport, keep it always 16px within the borders."
   - "When the No button exit animation finishes, add a short confetti if the user clicks Yes."
   - "In view 2, disable weekends."
   - "Change the palette to something darker and more elegant while keeping sage as accent."
5. **Save tokens:** if you want to check a specific file, use `@app.js` in the input.
6. **Close the loop:** create an `AGENTS.md` with `/init` and commit with `/supercommit` (if you have it) or:
   ```text
   !git init && git add . && git commit -m "feat: invitation challenge"
   ```

## Acceptance criteria

- [ ] The page looks correct on mobile and desktop.
- [ ] The "No" button can never be clicked.
- [ ] The calendar reflects the actual current month and year.
- [ ] The choice is saved in `localStorage` and appears again when reloading.
- [ ] There are no errors in the console.
- [ ] The project includes `SPEC.md` and `README.md`.

## Extensions (if you have time left)

- Add a `mailto:` endpoint that opens the email client with the proposed date/time already filled in.
- Internationalize the calendar (es / en) by detecting browser language.
- Replace local persistence with a `share link` that encodes the choice in the query string.