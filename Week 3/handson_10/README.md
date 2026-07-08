# Hands-On 10 — API Integration & Advanced State Management

**Level:** Advanced
**Stack:** React + Redux Toolkit (implementation), with Angular/NgRx and Vue/Pinia concepts documented for comparison

## What this covers
- **Task 1 — Centralised API layer**: a single configured Axios instance (`api/apiClient.js`) with request/response interceptors (auth header injection, response unwrapping, standardised errors) and a domain module (`api/courseApi.js`) exposing `getAllCourses()`, `getCourseById()`, `enrollStudent()`
- **Task 2 — Redux Toolkit async thunks**: `store/coursesSlice.js` uses `createAsyncThunk` + `extraReducers` to manage `pending`/`fulfilled`/`rejected` states automatically; `components/CoursesPage.jsx` consumes it purely through selectors
- **Task 3 — NgRx concept & Pinia advanced patterns**: documented in `ngrx-concept.md` (Actions → Effects → Reducers → Selectors data flow, with full code samples), and implemented for Vue in `handson_08/src/stores/enrollment.js` (`fetchAndEnroll`, `$reset`, `storeToRefs`)
- **Global error handling** across all three frameworks: `components/ErrorBoundary.jsx` (React), `GlobalErrorHandler` (Angular, in `ngrx-concept.md`), and `app.config.errorHandler` (Vue, in `handson_08/src/main.js`)
- A full framework state-management comparison table (bottom of `ngrx-concept.md`)

## Files
| File | Purpose |
|---|---|
| `api/apiClient.js` | Centralised Axios instance, interceptors |
| `api/courseApi.js` | Course-specific API functions built on `apiClient` |
| `store/coursesSlice.js` | Redux Toolkit slice with `createAsyncThunk` and selectors |
| `store/store.js` | Redux store configuration |
| `components/CoursesPage.jsx` | Component consuming the thunk + selectors only |
| `components/ErrorBoundary.jsx` | React global error boundary with fallback UI |
| `ngrx-concept.md` | NgRx architecture + code samples, plus the 3-framework comparison table |
| `package.json` | Extra dependencies (`axios`, `@reduxjs/toolkit`, `react-redux`) needed on top of Hands-On 6 |

## How to run
This hands-on is designed as an *add-on* to the Hands-On 6 React project (which already has Vite, React Router, and Redux Toolkit set up):

1. Copy the `api/`, `store/`, and `components/` folders from this exercise into `handson_06/src/`.
2. Merge `store/coursesSlice.js` into the existing `store/store.js` reducer map alongside `enrollmentReducer`.
3. Wrap `<App />` in `<ErrorBoundary>` inside `main.jsx`.
4. `npm install axios` (Redux Toolkit and react-redux are already installed from Hands-On 6).
5. `npm run dev`.

## Try it
- The course grid loads through the full stack: component → thunk → `courseApi` → `apiClient` (interceptors log every request) → Redux state → selector → UI.
- Temporarily point `apiClient`'s `baseURL` at an invalid host to see the `rejected` thunk action fire and the standardised error message render.
- Read `ngrx-concept.md` for the Angular/NgRx equivalent architecture and the side-by-side comparison of React+Redux, Angular+NgRx, and Vue+Pinia.
