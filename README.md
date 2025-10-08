# Pulse·10 — Daily Longevity Habits

Pulse·10 is a mobile-first health and fitness experience that helps you stack 10-minute longevity rituals. It blends habit tracking, immersive session flows, gamified momentum, and AI-guided personalization into a single progressive web app.

## Highlights

- **Mobile-first experience** designed for thumb-friendly interactions, with fluid motion and vivid feedback.
- **10-minute longevity stacks** combining mobility, breathwork, strength, and recovery phases you can launch instantly.
- **Habit tracking + streaks** with XP, levels, and badges that reward consistent execution.
- **AI-powered insights** that synthesize your last seven days of activity into actionable nudges.
- **Seasonal missions** and micro-challenges to keep behavior change fresh and compounding.
- **Local-first data** stored in `localStorage` via Zustand persistence, so your progress sticks between visits.

## Tech Stack

- [Vite](https://vitejs.dev/) + React 18 + TypeScript for a fast, modern SPA foundation
- [Tailwind CSS](https://tailwindcss.com/) for utility-first styling tuned to mobile performance
- [Zustand](https://github.com/pmndrs/zustand) with persistence for lightweight state management
- [Framer Motion](https://www.framer.com/motion/) for interaction polish and animated transitions
- [date-fns](https://date-fns.org/) for ergonomic time utilities

## Getting Started

> Requires Node.js 18+ and npm.

```bash
# Install dependencies
npm install

# Start the dev server
npm run dev

# Build for production
npm run build

# Preview the production build locally
npm run preview

# Run linting
npm run lint
```

Open http://localhost:5173 to explore the app. On first launch you will walk through onboarding to personalize your daily stacks.

## Project Structure

```
src/
├─ components/       // Reusable UI building blocks (habits, session, insights, etc.)
├─ data/             // Seed habits and session template definitions
├─ layouts/          // Cross-page shells and navigation
├─ pages/            // Route-level views (dashboard, session, insights, profile, onboarding)
├─ store/            // Zustand store with persistence, gamification, AI logic
├─ hooks/            // Custom hooks like the session timer
├─ constants/        // Missions, badges, and other static metadata
├─ types/            // Shared TypeScript contracts
└─ utils/            // (Reserved) shared helpers
```

## Key Flows

- **Onboarding** collects wake/wind-down windows, focus areas, and environment access to tailor recommendations.
- **Dashboard** surfaces today’s habit stack, streak progress, gamification engine, and seasonal missions.
- **Session** delivers guided 10-minute stacks with live timers, phase progress, and quick completion logging.
- **Insights** hosts the AI coach feed with actionable nudges and an execution log.
- **Profile** lets you retune preferences, review aggregate stats, and manage daily logs.

## Data & Personalization

All habit completions feed the `pulse-10-store` persistence key. The store handles:

- XP + level progression, streak maintenance, and badge unlocks
- Auto-logging of session phases to daily entries
- AI insight generation that reacts to the past 7 days of data

The AI insights are deterministic client-side heuristics so the experience works offline.

## Extending Pulse·10

- Connect to a backend or wearables by replacing the persistence layer in `usePulseStore`.
- Add push notifications (web or native) by wiring into the preferred habit slots saved during onboarding.
- Expand AI logic in `generateAIInsights` with additional heuristics or external inference APIs.
- Integrate charts by attaching a data viz library and feeding it the `history` slice from the store.

## Accessibility & Performance

- Motion and gradients are balanced with a dark, high-contrast palette for readability.
- Components keep DOM depth shallow and reuse Tailwind utilities for a small CSS payload.
- Session timer effects are throttled at 1Hz and cleanup automatically for low battery cost.

---

Have fun building daily longevity momentum ✨
