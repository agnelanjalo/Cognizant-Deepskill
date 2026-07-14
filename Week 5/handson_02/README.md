# Hands-On 2 — CSS Flexbox, Grid & Responsive Design

**Level:** Beginner
**Stack:** HTML5, CSS3 (no framework)
**Builds on:** Hands-On 1

## What this covers
- Flexbox header/nav layout with a mobile hamburger placeholder
- Flexbox stats bar (Courses Enrolled / GPA / Semester)
- CSS Grid course card layout using `repeat(auto-fit, minmax(280px, 1fr))`
- Mobile-first responsive design with `min-width` media queries at `768px` and `1024px`
- Fluid typography with `clamp()` and viewport units (`40vh` hero)

## Files
| File | Purpose |
|---|---|
| `index.html` | Home page with hero, stats bar, and 5-card course grid |
| `styles.css` | Mobile-first Flexbox + Grid styles with responsive breakpoints |
| `nav.js` | Toggles the mobile hamburger nav and syncs `aria-expanded` |

## How to run
Open `index.html` directly in a browser. Use DevTools' device toolbar to test at:
- **375px** — single-column, hamburger nav
- **768px** — 2-column course grid, full nav visible
- **1280px** — 3-column course grid, expanded hero padding

## Design approach
Base styles target the smallest screen first; complexity is *added* via `min-width` media queries rather than removed via `max-width`, per mobile-first best practice.
