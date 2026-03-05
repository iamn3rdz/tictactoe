# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A single-page Tic Tac Toe game (`tictactoe.html`) — no build step, no dependencies, no package manager.

## Running

Open `tictactoe.html` directly in a browser:

```bash
start tictactoe.html   # Windows
```

## Git Workflow

After completing any meaningful unit of work, commit and push to GitHub:

```bash
git add <files>
git commit -m "short, clear description of what changed and why"
git push
```

Commit frequently — after each feature, fix, or logical change — so progress is never lost. Keep commit messages concise and specific (e.g. `"Add AI opponent with minimax"`, not `"update stuff"`).

## Architecture

Everything lives in one self-contained file (`tictactoe.html`):

- **HTML** — 3×3 grid of `.cell` divs, a status line, score counters, and a restart button
- **CSS** (inline `<style>`) — dark theme, grid layout, hover/win highlight states
- **JS** (inline `<script>`) — pure vanilla JS; no frameworks. State is held in three variables: `board` (9-element array), `current` (active player), `gameOver`. Win detection iterates `WINS` (8 hardcoded combos). Scores persist across restarts via the `scores` object.
