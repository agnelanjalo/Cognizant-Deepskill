# Hands-On 1 — HTML5 Semantic Structure & CSS3 Foundations

**Level:** Beginner
**Stack:** HTML5, CSS3 (no framework)

## What this covers
- Semantic HTML5 elements: `header`, `nav`, `main`, `section`, `article`, `footer`
- CSS reset with `box-sizing: border-box`
- Flexbox header layout (site name + nav, space-between)
- Basic typography, box model, hover states
- `.course-card` styling with border, border-radius, box-shadow

## Files
| File | Purpose |
|---|---|
| `index.html` | Page skeleton for the Student Portal home page |
| `styles.css` | CSS3 styling: reset, box model, header/nav, hero, course cards |

## How to run
Open `index.html` directly in any modern browser — no build step required.

## Validation
Run the page through the [W3C Validator](https://validator.w3.org/) — it should report **zero errors**.

## Notes
- `<main>` appears exactly once and wraps the primary page content.
- `<article>` is used for course cards since each is self-contained, reusable content — more semantically correct than a plain `<div>`.
