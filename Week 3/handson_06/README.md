# Hands-On 6 — React Routing & State Management

**Level:** Intermediate
**Stack:** React 18 + Vite + React Router v6 + Redux Toolkit
**Builds on:** Hands-On 5

## What this covers
- **React Router v6**: `<BrowserRouter>`, `<Routes>`/`<Route>`, `<Link>`, `useParams()`, `useNavigate()`
- **Context API** (`src/context/EnrollmentContext.jsx`): a working Context-based enrollment store (Task 2), kept in the project as a reference implementation
- **Redux Toolkit** (`src/store/`): `configureStore`, `createSlice`, `useSelector`/`useDispatch` — the final enrollment state management used by the running app (Task 3, which explicitly replaces the Context version)

## Project structure
```
handson_06/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.jsx          # wraps App in BrowserRouter + Redux Provider
    ├── App.jsx            # route definitions
    ├── index.css
    ├── data/courses.js
    ├── components/
    │   ├── Header.jsx     # nav links + live enrolled count (useSelector)
    │   └── Footer.jsx
    ├── context/
    │   └── EnrollmentContext.jsx   # Task 2 reference implementation
    ├── store/
    │   ├── store.js
    │   └── enrollmentSlice.js      # Task 3 — enroll/unenroll reducers + selectors
    └── pages/
        ├── HomePage.jsx
        ├── CoursesPage.jsx        # search, enroll, useNavigate to /profile
        ├── CourseDetailPage.jsx   # useParams for :courseId
        └── ProfilePage.jsx        # useSelector/useDispatch, unenroll
```

## How to run
```bash
npm install
npm run dev
```
Visit `http://localhost:5173`.

## Try it
- Navigate via the header links — no full page reloads (client-side routing).
- Click a course title on `/courses` → `/courses/:id` shows that course's detail.
- Click **Enroll** on a course card → dispatches the Redux `enroll` action and auto-navigates to `/profile`.
- On `/profile`, click **Remove** → dispatches `unenroll`.
- Install the [Redux DevTools extension](https://github.com/reduxjs/redux-devtools) to watch the `enroll`/`unenroll` actions and state diffs live.

## Why Redux replaced Context here
Context works fine for this small example, but re-renders every consumer on any state change and doesn't scale well for frequently-updated state. Redux Toolkit's `createSlice` + Immer gives the same "no prop drilling" benefit with less boilerplate, plus time-travel debugging via Redux DevTools — which is why Task 3 supersedes the Task 2 Context version in the running app.
