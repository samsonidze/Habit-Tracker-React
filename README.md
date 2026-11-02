# Habit Tracker

A weekly habit tracker: add habits, tick them off day by day, see your current streak, and page back and forth through weeks. Everything is persisted in the browser, so there's no account and no backend.

**Live demo:** https://habit-tracker-react-steel.vercel.app

## Features
- **Weekly grid** – Monday-to-Sunday columns built with `date-fns`; previous/next buttons move the window a week at a time
- **One-tap completion** – toggle a habit for any past or current day; future days are disabled
- **Streak counter** – consecutive-day streak computed from the completion history
- **Persistence** – habits are saved to `localStorage` through a typed `useLocalStorage` hook that revives ISO date strings back into `Date` objects on load
- **Typed state** – a `HabitContext` + `useHabits()` hook expose `addHabit`, `toggleHabit` and `deleteHabit` with full TypeScript types
- Dark UI with Tailwind CSS, `tailwind-merge` for composable button variants

## Tech
React 19 (with the React Compiler) · TypeScript 6 · Vite · Tailwind CSS 4 · date-fns · ESLint (typescript-eslint, react-hooks)

## Structure
```
src/
├── context/
│   ├── HabitProvider.tsx   # State + actions, backed by useLocalStorage
│   └── useHabits.ts        # Context, Habit type and consumer hook
├── hooks/useLocalStorage.ts
└── components/             # Header (week nav), HabitForm, HabitList, Button
```

## Run locally
```bash
npm install
npm run dev
```

## Acknowledgements
Based on Web Dev Simplified's habit-tracker exercise (MIT, see `LICENSE`).
