# CSS Specificity Calculator

A minimal, polished web app that calculates CSS selector specificity.  
Type one or more selectors (comma-separated) and the app gives a live breakdown of specificity as `(a,b,c,d)` along with a visual bar and tokenized parts.

- Dark gradient UI with high contrast
- Live calculation and token highlighting
- Copy results, clear input, and example presets

## Files

```
index.html   - Main single-page UI
style.css    - Styles (dark gradient, responsive)
script.js    - Specificity calculation & UI logic
README.md    - This file
```

## Features

- Parses complex selectors including:
  - IDs (`#id`)
  - Classes (`.class`)
  - Attribute selectors (`[attr="value"]`)
  - Pseudo-classes (`:hover`, `:nth-child(2)`)
  - Pseudo-elements (`::after`, `::first-letter`)
  - Combinators (descendant, `>`, `+`, `~`)
- Supports multiple selectors separated by commas (ignores commas inside parentheses)
- Visual bar to compare weights and tokenized badge list for quick inspection
- Copy result to clipboard

## Usage

Open `index.html` in your browser:

- Double-click `index.html` in the project folder
- Or start a local HTTP server for best results (recommended):

```bash
# Python 3 (works from project folder)
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

Type a selector in the textarea (supports multiple lines or comma-separated selectors). Results update live.

## Development

Install Git (if not already) and initialize the project:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
```

Create a GitHub repo and push (replace URL):

```bash
git remote add origin https://github.com/YOUR_USERNAME/css-specificity-calculator.git
git push -u origin main
```

Or use GitHub CLI:

```bash
gh auth login
gh repo create css-specificity-calculator --public --source=. --remote=origin --push
```

## Tests & Notes

- The calculator is intentionally conservative and uses regex-driven parsing (not a full CSS parser). It handles most real-world selectors you'll input.
- Inline styles (`style="..."`) are not present in selector strings; the app reports `(1,0,0,0)` only if you manually increment inline count (not necessary for typical usage).

## Contributing

PRs and issues welcome. If you add features, please:
- Keep UI minimal and accessible
- Add tests for selector edge-cases

## License

MIT © ngassanov07