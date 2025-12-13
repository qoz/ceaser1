# Caesar Cipher Solver (Web App)

A small browser-based Caesar cipher / substitution puzzle game.

## Features

- Works in any modern browser (desktop or mobile).
- Two play modes:
  - **Puzzle list mode**: choose from predefined puzzles stored in `puzzles.json`.
     On page load, the app tries to fetch("puzzles.json"); if present and valid, it populates the dropdown. You can also load puzzles via the file input in the UI.
  - **Manual mode**: paste or type an encrypted message yourself.
- Letter substitution UI:
  - Shows only letters that actually appear in the cipher.
  - Each letter button displays a **count** (frequency in the message).
  - Tap a letter to assign a substitution; input is sanitized to a single A–Z letter.
  - Duplicate substitutions are detected; you get a confirmation if you reuse a letter.
- Frequency view:
  - Shows letters sorted by descending frequency.
- Hint support:
  - Each puzzle can provide a `hint` mapping (cipher → plain).
  - "Apply Hint" button fills in that mapping.
- Dev mode:
  - Checkbox to reveal the full solution text (for loaded puzzles only).
- Font / readability controls:
  - "Text display options" dropdown.
  - Fonts apply to:
    - Encrypted message
    - Decryption
    - Letter replacement UI
    - Frequency view
  - "Large Print" makes main text larger (1.6em) and UI moderately larger (1.2em).
  - "Extra Letter Spacing" adds spacing around all relevant text.

## Files

- `index.html` — main HTML + JavaScript game logic.
- `style.css` — styling for layout, buttons, and text.
- `puzzles.json` — optional JSON file containing puzzles.
- `README.md` — this documentation.

## Running Locally

Option 1 (simplest):

1. Put all files in one folder.
2. Open `index.html` in your browser (double-click or drag into the browser).

Option 2 (local web server, recommended):

```bash
cd caesar-solver
python -m http.server 8000
```

Then visit: http://localhost:8000/

Deploying (e.g. GitHub Pages)

Create a GitHub repo with these files in the root.

Enable GitHub Pages for the repo.

Visit the GitHub Pages URL (e.g. https://username.github.io/caesar-solver/).

The app will auto-load puzzles.json from the same directory if present.