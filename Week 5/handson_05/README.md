# Hands-On 5 — React Fundamentals: Components, Props, State & Hooks

**Level:** Intermediate
**Stack:** React 18 + Vite

## What this covers
- JSX, functional components, Fragments
- Props (`Header`, `Footer`, `CourseCard`) and prop spreading
- `useState` for search, enrollment, and a local `StudentProfile` form
- Lifting state up: `enrolledCourses` lives in `App.jsx`, passed down via `onEnroll`
- `useEffect` for data fetching on mount, loading/error state, and a dependency-array demo

## Project structure
```
handson_05/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.jsx
    ├── App.jsx
    ├── index.css
    ├── data/
    │   └── courses.js
    └── components/
        ├── Header.jsx
        ├── Footer.jsx
        ├── CourseCard.jsx
        └── StudentProfile.jsx
```
> `node_modules/` is intentionally excluded — install dependencies fresh with the commands below.

## How to run
```bash
npm install
npm run dev
```
Visit the printed local URL (typically `http://localhost:5173`).

## Try it
- Type in the search box → the course grid filters live.
- Click **Enroll** on a card → the "Enrolled" count in the header updates (state lifted from `CourseCard` → `App`).
- Fill out the profile form → the preview line updates as you type (local component state).
- Open the console → "Courses updated" logs every time the `courses` array changes, demonstrating the `useEffect` dependency array.
