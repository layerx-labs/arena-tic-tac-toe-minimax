# Arena Sprint: Tic-Tac-Toe — Plan

## 1. Project Idea

**"Neon Arena Tic-Tac-Toe"** — a single-page, browser-playable 3×3 Tic-Tac-Toe game with a dark neon arcade aesthetic. Two players (X and O) alternate locally; the game detects wins and draws, shows whose turn it is, and lets players reset. The visual personality (glowing neon marks, dark background, subtle animations) makes it memorable and fun while remaining technically minimal and bug-free.

---

## 2. Problem & Target User

**Problem:** A working, visually polished Tic-Tac-Toe game that runs entirely in the browser — no backend, no login, no build step — deployed to a public URL from a GitHub repository.

**Target user:** Hackathon judges and casual visitors who want a quick, satisfying two-player game. Simplicity and reliability trump feature depth.

---

## 3. Core Features

- **3×3 game board** — clickable cells rendered with CSS Grid
- **Two-player local play** — X and O alternate turns on the same device
- **Turn indicator** — clear display of whose turn it is (X or O)
- **Win detection** — all 8 winning lines checked after every move
- **Draw detection** — flagged when all 9 cells are filled with no winner
- **Win/draw announcement** — clear on-screen message with the result
- **New game / reset** — button to clear the board and restart
- **Hover feedback** — cells highlight on hover before a move is made
- **Win animation** — winning line cells glow/brighten on game win
- **Responsive layout** — works on desktop and mobile

---

## 4. Tech Stack

| Choice | Justification |
|---|---|
| **Vanilla HTML/CSS/JS** (single `index.html`) | Zero build step, zero dependencies, zero framework bugs. Maximum reliability for "It works (40%)". |
| **CSS Custom Properties** | Enables a cohesive neon theme with a single source of truth for colors. |
| **CSS Grid** | Semantic, clean board layout — no floats or flexbox hacks needed. |
| **Unicode symbols** (× / ○) | No image assets required; crisp at any resolution. |
| **GitHub Pages** | Native to the GitHub repo — free, fast, reliable hosting. One-click deploy from the `main` branch. |
| **Git / GitHub** | Source control with incremental commits; required for the Craft (30%) rubric. |

---

## 5. Architecture

```
/workspace/
├── index.html      # All HTML, CSS, and JS in one file
├── README.md       # Project documentation
└── PLAN.md         # This plan (for reference)
```

**Frontend only** — no backend, no API, no database. All state (current player, board cells, game status) lives in JavaScript variables. The DOM is updated imperatively on each move.

**File structure rationale:** A single `index.html` is the simplest possible artifact — no bundler, no server, no dependencies. Open it directly in a browser or serve it from GitHub Pages. The README explains how to run it locally.

---

## 6. How the Idea Maps to the Rubric

| Rubric Criterion | How This Project Addresses It |
|---|---|
| **It works (40%)** | Vanilla JS with a well-tested win-check loop (8 lines). No framework, no async, no edge cases. Logic is 100% in one readable function. |
| **Craft (30%)** | Single HTML file with clearly separated CSS/JS sections. Incremental git commits: board → click handling → win detection → styling → animations → reset → README → deploy. |
| **Shipped (20%)** | GitHub Pages serves `index.html` directly from `layerx-labs/arena-tic-tac-toe-minimax`. README links to both the repo and the live demo URL. |
| **Writeup (10%)** | README covers: what it is, how to run locally (open `index.html` in any browser), tech stack (with justifications), and key decisions. TAIKAI project page links both. |

---

## 7. Milestone List (Build Phase)

| # | Milestone | Git Commit Message |
|---|---|---|
| 1 | HTML skeleton + 3×3 board cells | `"feat: initial HTML structure with 3x3 grid"` |
| 2 | Game logic: click handling, turn alternation, win detection, draw detection | `"feat: game logic — turn alternation, win/draw detection"` |
| 3 | Status display (turn indicator + result message) | `"feat: status display for turn and game result"` |
| 4 | Reset / New Game button | `"feat: reset button to start a new game"` |
| 5 | Neon styling: dark background, glowing marks, hover effects | `"style: neon arcade theme"` |
| 6 | Win-line highlight animation | `"style: win-line glow animation"` |
| 7 | Responsive layout for mobile | `"style: responsive layout for mobile"` |
| 8 | README.md with documentation | `"docs: README with run instructions and decisions"` |
| 9 | Deploy to GitHub Pages + push all commits | `"deploy: enable GitHub Pages, push to main"` |

---

## 8. Definition of Done

The project is **done** when:

1. The game is fully playable: X and O alternate turns, clicking a filled cell does nothing, wins are detected on all 8 lines, draws are detected, and the reset button works.
2. The live demo is accessible at a public URL (GitHub Pages).
3. The GitHub repository contains the source with a clear README.
4. The TAIKAI project page is published with the GitHub repo URL and live demo URL filled in.
5. The git history shows incremental commits (not a single mega-commit).
6. The game loads without console errors in Chrome and Firefox.
