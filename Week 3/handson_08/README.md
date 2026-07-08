# Hands-On 8 — Vue.js: Composition API, Vue Router & Pinia

**Level:** Advanced
**Stack:** Vue 3 + Vite + Vue Router 4 + Pinia

## What this covers
- Single-file components (`<template>` / `<script setup>` / `<style scoped>`)
- `ref()` / `computed()` reactivity, `defineProps` / `defineEmits`, `v-for`, `v-model`
- **Vue Router**: named routes, `<RouterLink>` / `<RouterView>`, `useRoute()`, `useRouter()`, and a `router.beforeEach` navigation guard that logs every navigation
- **Pinia**: a Composition-API "setup store" (`enrollment.js`) with reactive state, a `computed` getter (`totalCredits`), actions (`enroll`, `unenroll`), an advanced async action (`fetchAndEnroll`), and `$reset()`
- `storeToRefs()` used in `ProfileView.vue` to destructure store state without losing reactivity

## Project structure
```
handson_08/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.js          # registers Pinia + Router, global error handler
    ├── App.vue
    ├── style.css
    ├── router/index.js
    ├── stores/enrollment.js
    ├── components/
    │   ├── Header.vue
    │   └── CourseCard.vue
    └── views/
        ├── HomeView.vue
        ├── CoursesView.vue
        ├── CourseDetailView.vue
        └── ProfileView.vue
```

## How to run
```bash
npm install
npm run dev
```
Visit `http://localhost:5173`.

## Try it
- Search on `/courses` filters live via a `computed` property.
- Clicking a course card title routes to `/courses/:id` (`useRoute` reads the param).
- Clicking **Enroll** (from either the list or the detail page) calls the Pinia store action and — on the detail page — redirects to `/profile` via `useRouter().push(...)`.
- Open Vue DevTools → **Pinia** tab to watch `enrolledCourses` and `totalCredits` update live.
- Check the console for `Navigating to: <path>` logs from the router guard.
