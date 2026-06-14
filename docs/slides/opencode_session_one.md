---
marp: true
theme: codebar
paginate: true
title: opencode — Session One
description: Intro to opencode and free models via opencode zen
author: codebar
header: 'AI Workshop · opencode'
footer: 'codebar · AI Workshop'
html: true
---

<!-- _class: lead -->

<div class="tagline">codebar · AI Workshop · Session 01</div>

# opencode
## Agentic coding with open-source models

<div class="meta">

**Presenter:** _Karel M._ - [_@oricha_](https://github.com/oricha)
**Co-host:** _Andy D._ [_@mkdir-andy_](https://github.com/mkdir-andy)

**Sponsor:** [_Factoria F5_](https://factoriaf5.org/)

</div>

---

<!-- _class: agenda -->

## Agenda

1. opencode introduction
2. Local setup & tool tour
3. Live demo
4. Hands-on with coaches
5. Share & discuss

---

## How we code is changing

Five years ago, our job was to **type code**.
Today, increasingly, it is to **steer it**.

- Editors → autocomplete → chat → **agents that act**.
- The bottleneck moves from _writing_ to _reviewing_ and _deciding_.
- The gate used to be the **subscription**. Today there are **free, open-source paths in**.

> Today is about picking one up and trying it.

---

## What is a code agent?

An **agent** is an LLM in a loop with tools.

- It **reads** your files, **runs** commands, **writes** code, **observes** results, **decides** what to do next.
- The LLM inside is the **model** — Claude, GPT, Big Pickle, DeepSeek…
- Each model has its own **strengths, cost, and access requirements**.

> The next choice is which model — and therefore which **provider** — does the work.

---

## Free vs paid — closer than you'd think

Share of real GitHub issues each model resolves on **SWE-bench Verified** — free models are within striking distance.

<div class="benchmark">
  <div class="bench-name">Claude Opus 4.5 <span class="tag paid">paid</span></div>
  <div class="bench-track"><div class="bench-fill paid" style="width: 82%"></div></div>
  <div class="bench-val">82%</div>

  <div class="bench-name">Claude Sonnet 4.5 <span class="tag paid">paid</span></div>
  <div class="bench-track"><div class="bench-fill paid" style="width: 77%"></div></div>
  <div class="bench-val">77%</div>

  <div class="bench-name">GPT-5 <span class="tag paid">paid</span></div>
  <div class="bench-track"><div class="bench-fill paid" style="width: 74%"></div></div>
  <div class="bench-val">74%</div>

  <div class="bench-name">DeepSeek V4 Flash <span class="tag free">free</span></div>
  <div class="bench-track"><div class="bench-fill free" style="width: 65%"></div></div>
  <div class="bench-val">65%</div>

  <div class="bench-name">Nemotron 3 Ultra <span class="tag free">free</span></div>
  <div class="bench-track"><div class="bench-fill free" style="width: 62%"></div></div>
  <div class="bench-val">62%</div>

  <div class="bench-name">Big Pickle <span class="tag free">free</span></div>
  <div class="bench-track"><div class="bench-fill free" style="width: 58%"></div></div>
  <div class="bench-val">58%</div>

  <div class="bench-name">MiMo V2.5 <span class="tag free">free</span></div>
  <div class="bench-track"><div class="bench-fill free" style="width: 52%"></div></div>
  <div class="bench-val">52%</div>

  <div class="bench-name">North Mini Code <span class="tag free">free</span></div>
  <div class="bench-track"><div class="bench-fill free" style="width: 48%"></div></div>
  <div class="bench-val">48%</div>
</div>

<div class="bench-caption">Illustrative — check the live leaderboard at <a href="https://www.swebench.com/">swebench.com</a>.</div>

---

## Why opencode

- **Open source** — community-driven, self-hostable, no vendor lock-in.
- **75+ providers** — Anthropic, OpenAI, Google, local models, opencode zen.
- **Free tier via opencode zen** — try real agentic coding without a credit card.
- **TUI-first** — built for the terminal; pairs well with WezTerm, Alacritty, Ghostty, Kitty.
- **Composable** — define custom agents and project rules in `AGENTS.md`.

---

<!-- _class: two-col -->

## TUI tour

<div class="columns">

<div>

Three regions to know:

- **Input area** (bottom) — your prompts and slash commands.
- **Transcript** (centre) — the agent's actions, file diffs, tool output.
- **Status bar** (top/bottom) — current agent · current model · session name.

Slash commands you will use first: `/init`, `/connect`, `/models`, `/share`.

</div>

<div>

![opencode TUI](./assets/tui.png)

</div>

</div>

---

## Interacting — agents, models, sessions

| What | Key | What it does |
| --- | --- | --- |
| **Agents** | `tab` / `shift+tab` · `ctrl+x a` | Switch the persona driving the session |
| **Models** | `f2` / `shift+f2` · `ctrl+x m` | Change which model is doing the work |
| **Sessions** | `ctrl+x l` · `ctrl+x g` · `ctrl+r` | List, open timeline, rename |

Full reference: [`setup/commands.md`](../setup/commands.md).

---

## Live demo

Build a small project, live, using opencode + a free zen model.

While you watch, pay attention to:

- **Prompt style** — intent-first, not step-by-step.
- **When to switch agents** — research vs. implement vs. review.
- **Undo / redo** — `/undo` and `/redo` are your safety net.

---

## Hands-on with coaches

Each student is paired **1:1 with a coach** — together you pick one challenge and work through it as a team.

1. [Challenge one](../challenges/challenge_one.md) — _context: TBD_
2. [Challenge two](../challenges/challenge_two.md) — _context: TBD_
3. [Challenge three](../challenges/challenge_three.md) — _context: TBD_

**Before you start:** fork [github.com/codebar/ai-workshop-opencode](https://github.com/codebar/ai-workshop-opencode) and clone your fork locally — that gives you a sandbox to commit your work into.

---

## Share & discuss

Last 15 minutes — open mic.

- Show one thing the agent did **well**.
- Show one thing it got **wrong** and how you steered it.
- Ask the room: prompts, models, workflows, surprises.

---

<!-- _class: lead -->

<div class="tagline">Thank you</div>

# Keep going

<div class="meta">

**Workshop repo:** https://github.com/codebar/ai-workshop-opencode
**opencode docs:** https://opencode.ai/docs/
**codebar:** https://codebar.io/

</div>
