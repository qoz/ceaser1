# Caesar Cipher Solver - AI Coding Guidelines

## Project Overview
This is a browser-based Caesar cipher puzzle game built as a single-page web app. All logic resides in `index.html` with embedded JavaScript. The app supports two modes: loading puzzles from `puzzles.json` or manual text entry.

## Architecture
- **Single-file app**: HTML structure, CSS styling, and JavaScript logic combined in `index.html`.
- **Data flow**: User selects puzzle → loads cipher text → builds letter mapping UI → applies substitutions → checks against solution.
- **State management**: Global variables like `cipherText`, `mapping` (object), `puzzles` array track app state.

## Key Files
- `index.html`: Main app with DOM manipulation, event handlers, and game logic.
- `puzzles.json`: JSON array of puzzle objects (see structure below).
- `style.css`: Dark theme styling with flexbox layouts for responsive UI.
- `README.md`: Deployment and usage instructions.

## Data Structures
Puzzle objects in `puzzles.json`:
```json
{
  "id": "p1",
  "title": "Hello World Demo",
  "cipher": "KHOOR ZRUOG",
  "solution": "HELLO WORLD",
  "hint": { "cipher": "K", "plain": "H" },
  "publishDate": "2025-01-01"
}
```
- Use `fetch("puzzles.json")` for auto-loading; fallback to manual file input.

## Coding Patterns
- **Letter handling**: Always convert to uppercase A-Z. Use `alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("")` for validation.
- **UI updates**: Call `renderMappings()` and `decodeText()` after state changes to refresh display.
- **Mapping logic**: Prevent duplicate substitutions with confirmation dialogs. Hints auto-resolve conflicts.
- **Frequency calculation**: Count occurrences in `cipherText`, sort descending for display.
- **Event handling**: Use `addEventListener` for buttons; prompt for user input on letter taps.
- **Error messaging**: Update `messageEl.textContent` and `className` ("ok", "err", or "") for feedback.

## Workflows
- **Local development**: Open `index.html` directly in browser or serve with `python -m http.server 8000`.
- **Adding puzzles**: Edit `puzzles.json` with new objects; include optional `hint` for single-letter mappings.
- **Testing**: Manually verify letter mappings, hint application, and solution checking in browser.
- **Deployment**: Push to GitHub repo root; enable Pages for hosting.

## Conventions
- No external dependencies; vanilla JS only.
- Responsive design with mobile-friendly touch targets.
- Dev mode reveals solutions for loaded puzzles only.
- Preserve whitespace in cipher/solution text using `pre-wrap`.</content>
<parameter name="filePath">c:\SHARE\PYTHON\ceaser1\.github\copilot-instructions.md