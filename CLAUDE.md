# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

A collection of browser-based games and interactive web apps. Each project is a **single self-contained HTML file** with embedded CSS and JS — no build tools, no frameworks, no dependencies.

## Running a File

Open any `.html` file directly in a browser. There is no build step, no server required.

```
# Open in default browser (Windows)
cmd.exe /c start "" "C:\AI_Projects\<file>.html"
```

## Project Structure

```
AI_Projects/
├── tetris.html              # Rainbow Tetris (canvas-based, rAF game loop)
└── Claude_Code_Test/
    └── tictactoe.html       # Tic Tac Toe (DOM-based, event-driven)
```

## Architecture Conventions

**Every game follows the same pattern:**
1. **HTML** — minimal semantic structure (canvas or a small set of divs)
2. **CSS** — dark background (`#111` or `#1a1a2e`), monospace or system font, flexbox centering
3. **JS** — all logic in one `<script>` tag, no modules, no external libraries

**Canvas games** (`tetris.html`):
- `requestAnimationFrame` loop with delta-time gravity
- 2D array as game board (0 = empty, 1–N = color index)
- Separate draw functions for board, active piece, ghost, and preview canvas

**DOM games** (`tictactoe.html`):
- State stored in plain JS variables/arrays
- Single event listener on a container (event delegation)
- UI updated by direct DOM manipulation

## Git & GitHub Workflow

All changes must be committed and pushed to `origin/master` on GitHub (`Goro-Goro-no-Mi/AI-Projects`).

```bash
git add <file>
git commit -m "concise description of what changed and why"
git push
```

Commit messages should be specific to what changed — not generic ("update tetris.html").
