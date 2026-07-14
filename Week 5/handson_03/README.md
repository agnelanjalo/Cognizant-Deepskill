# Hands-On 3 — JavaScript ES6+ & DOM Manipulation

**Level:** Beginner
**Stack:** HTML5, CSS3, vanilla JavaScript (ES6 modules)

## What this covers
- `let` / `const`, destructuring, arrow functions, template literals
- `Array.map()`, `Array.filter()`, `Array.reduce()`
- ES6 `import` / `export` modules
- DOM selection (`querySelector`), element creation (`createElement`), `DocumentFragment`
- Event listeners: live search (`input`), sort (`click`), and **event delegation** for course cards

## Files
| File | Purpose |
|---|---|
| `index.html` | Course page shell with search box, sort button, and empty grid container |
| `data.js` | Exports the course data array (id, name, code, credits, grade) |
| `app.js` | All JS logic: data practice (Task 1), dynamic rendering (Task 2), events (Task 3) |
| `styles.css` | Styling for controls, grid, and card focus states |

## How to run
Because this uses ES6 modules (`<script type="module">`), open it via a local server rather than the `file://` protocol (module imports are blocked by CORS on `file://` in most browsers).

```bash
# from inside handson_03/
npx serve .
# or
python3 -m http.server 8000
```
Then visit `http://localhost:8000` (or whichever port your tool prints).

## Try it
- Type in the search box → cards filter instantly.
- Click **Sort by Credits** → cards reorder by credits, descending.
- Click (or Tab + Enter on) a card → its name and grade appear below the grid.
- Open the browser console to see the Task 1 `map`/`filter`/`reduce` output.
