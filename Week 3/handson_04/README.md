# Hands-On 4 — Async JavaScript, Fetch API & API Integration

**Level:** Intermediate
**Stack:** HTML5, CSS3, vanilla JS (ES6 modules) + Axios (CDN)
**API used:** [JSONPlaceholder](https://jsonplaceholder.typicode.com) — `/users`, `/posts`

## What this covers
- Promise chaining with `.then()` vs `async/await` + `try/catch`
- Simulated network delay + loading state (`fetchAllCourses`)
- `Promise.all()` for concurrent requests
- A reusable `apiFetch()` helper that checks `response.ok` and throws descriptive errors
- Loading spinner text, friendly error UI, and a **Retry** button
- Axios: auto JSON parsing, automatic error throwing on non-2xx, `params`, and a request interceptor

## Files
| File | Purpose |
|---|---|
| `index.html` | Page with Courses and Notifications sections, Axios CDN script, error/retry UI |
| `data.js` | Local fallback course data used to simulate a delayed API |
| `app.js` | All async logic — Promises, Fetch, error handling, Axios |
| `styles.css` | Styling for cards, status text, and error box |

## How to run
Serve locally (module imports need a server, not `file://`):
```bash
npx serve .
```
Then open the printed URL. Requires an internet connection since it calls the live JSONPlaceholder API.

## Try it
- Watch the console for the Task 1 Promise/async-await/`Promise.all` logs.
- The Courses section shows "Loading courses..." for ~1 second (simulated delay) before rendering.
- The Notifications section fetches real posts from JSONPlaceholder.
- To see the error state: uncomment the line at the bottom of `app.js` that calls `loadNotifications` with a bad URL, or edit `API_BASE` temporarily — the error box and **Retry** button will appear.

## fetch vs axios (summary)
1. Axios auto-parses JSON; fetch needs an explicit `.json()` call.
2. Axios rejects automatically on non-2xx responses; fetch only rejects on network failure.
3. Axios has built-in interceptors and a `timeout` option; fetch needs `AbortController` for timeouts.
