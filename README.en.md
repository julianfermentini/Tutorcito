<h1 align="center">📚 Tutorcito</h1>

<p align="center">
  <strong>A marketplace where university students offer and book tutoring sessions with other students.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-15-000000?logo=nextdotjs&logoColor=white" alt="Next.js 15">
  <img src="https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black" alt="React 19">
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Supabase-Auth%20%2B%20Postgres-3ECF8E?logo=supabase&logoColor=white" alt="Supabase">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?logo=tailwindcss&logoColor=white" alt="Tailwind CSS">
</p>

<p align="center">
  <a href="README.md">🇦🇷 Leer en Español</a>&nbsp;&nbsp;·&nbsp;&nbsp;🇺🇸 English
</p>

---

## What it is

Tutorcito is a group project from my degree at Universidad del Aconcagua: a marketplace-style site
where a university student can find tutors (other students) for specific subjects, view their
profile, pricing, and reviews, and reach out to them. Each tutor gets their own page with a bio,
the subjects they teach, their rate, and reviews from other students.

This repository is my fork of the team's repo ([`Tutorcito/Tutorcito`](https://github.com/Tutorcito/Tutorcito)),
where I worked alongside the rest of the group.

## My contribution

I mostly worked on the frontend, focused on authentication and UI:

- **Dynamic navbar** that reflects session state (logged-in vs. anonymous user) — [PR #19](https://github.com/Tutorcito/Tutorcito/pull/19)
- **"I want to be a tutor" button flow**, which kicks off onboarding a user as a tutor — [PR #49](https://github.com/Tutorcito/Tutorcito/pull/49)
- UI adjustments and fixes on the tutor cards — [PR #52](https://github.com/Tutorcito/Tutorcito/pull/52)

## Stack

| Layer | Technology |
|---|---|
| **Framework** | Next.js 15 (App Router), React 19, TypeScript |
| **Styling** | Tailwind CSS 4, Radix UI components |
| **Auth & data** | Supabase (Auth with Google OAuth, `@supabase/ssr` for server-side sessions) |
| **Lint** | ESLint 9 |

## Features

- Email/password login or **Google OAuth**, session persisted via Supabase SSR
- **Multi-step onboarding** to complete a profile on signup (`app/auth/onboarding/step1..4`)
- Public tutor profile page: bio, subjects, pricing, and reviews from other users
- Study-resource carousel (Anki, Excalidraw, GeoGebra, NotebookLM)
- Tutor cards linking into each individual profile

## Structure

```
tutorcito/
├── app/
│   ├── auth/                 # login, OAuth callback, onboarding (4 steps)
│   ├── tutors/[tutorId]/      # public tutor profile
│   └── page.tsx               # home
├── components/
│   ├── profileCard/            # profile header, bio, pricing, actions
│   ├── tutor/                  # bio, comments, price card
│   ├── navBar.tsx, footer.tsx
│   └── ui/                     # buttons, inputs, selects (Radix)
├── context/AuthContext.tsx     # global session state
└── lib/
    ├── supabase.ts             # Supabase client + profile types
    └── auth.ts                 # login/signup helpers
```

## Running locally

```bash
npm install
# create .env.local with:
#   NEXT_PUBLIC_SUPABASE_URL=...
#   NEXT_PUBLIC_SUPABASE_ANON_KEY=...
npm run dev
```

---

<p align="center">
  <a href="README.md">🇦🇷 Leer este README en Español</a>
</p>
