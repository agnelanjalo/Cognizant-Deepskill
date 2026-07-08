# Hands-On 9 — Web Accessibility (a11y) & Cross-Browser Compatibility

**Level:** Advanced
**Stack:** HTML5, CSS3, vanilla JS (ES6 modules)
**Builds on:** Hands-On 1–3 (the plain HTML/CSS/JS Student Portal)

## What this covers
- Full accessibility audit log (recorded as an HTML comment at the top of `index.html`)
- Semantic fixes: correct heading hierarchy, `<label for>` on the search input, `aria-label` on `<nav>`
- ARIA: `role="list"` / `role="listitem"` on the course grid, `role="status"` + `aria-live="polite"` on the results count and selected-course announcement, `aria-current="page"` on the active nav link
- Full keyboard navigation: course cards are `tabindex="0"` and respond to **Enter** and **Space**, matching the WAI-ARIA button interaction pattern
- Documented colour-contrast audit (before/after table) in `styles.css`, fixing one WCAG AA failure
- Cross-browser / caniuse notes for CSS Grid `auto-fit`/`minmax()` and Flexbox `gap`, plus a feature-detection example (`CSS.supports`) instead of browser-sniffing
- Visible focus outlines on every interactive element (never `outline: none` without a replacement)

## Files
| File | Purpose |
|---|---|
| `index.html` | Accessible course page; audit log is documented in the top HTML comment |
| `data.js` | Course data (unchanged from Hands-On 3) |
| `app.js` | Rendering + keyboard event handling (`Enter`/`Space` on cards) + live-region updates |
| `styles.css` | Styling with the contrast audit table and cross-browser notes documented in comments |

## How to run
```bash
npx serve .
```
Then open the printed local URL.

## How to verify
1. Open Chrome DevTools → **Lighthouse** → Accessibility category → **Generate report**. Should score 100.
2. Install the **axe DevTools** extension and re-scan — zero violations expected.
3. Tab through the whole page with only the keyboard: every link, input, button, and course card should be reachable and show a visible focus ring, and pressing Enter/Space on a focused card should select it the same as a click.
4. Turn on a screen reader (VoiceOver / NVDA) and confirm the results count and selected-course text are announced automatically when they change.
