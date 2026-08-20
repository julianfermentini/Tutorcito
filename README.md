<h1 align="center">📚 Tutorcito</h1>

<p align="center">
  <strong>Plataforma web donde estudiantes universitarios ofrecen y contratan clases particulares con otros estudiantes.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-15-000000?logo=nextdotjs&logoColor=white" alt="Next.js 15">
  <img src="https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black" alt="React 19">
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Supabase-Auth%20%2B%20Postgres-3ECF8E?logo=supabase&logoColor=white" alt="Supabase">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?logo=tailwindcss&logoColor=white" alt="Tailwind CSS">
</p>

<p align="center">
  🇦🇷 Español&nbsp;&nbsp;·&nbsp;&nbsp;<a href="README.en.md">🇺🇸 Read in English</a>
</p>

---

## Qué es

Tutorcito es un proyecto grupal de la carrera en la Universidad del Aconcagua: un sitio tipo
marketplace donde un estudiante universitario puede encontrar tutores (otros estudiantes) para
materias puntuales, ver su perfil, precios y comentarios, y contactarlos. Cada tutor tiene una
página propia con su presentación, las materias que domina, su tarifa y reseñas de otros
estudiantes.

Este repositorio es mi fork del repo del equipo ([`Tutorcito/Tutorcito`](https://github.com/Tutorcito/Tutorcito)),
donde trabajé en conjunto con el resto del grupo.

## Mi contribución

Trabajé principalmente sobre el frontend, con foco en autenticación y UI:

- **Navbar dinámico** según el estado de sesión (usuario logueado vs. anónimo) — [PR #19](https://github.com/Tutorcito/Tutorcito/pull/19)
- **Flujo del botón "Quiero ser tutor"**, que dispara el alta de un usuario como tutor — [PR #49](https://github.com/Tutorcito/Tutorcito/pull/49)
- Ajustes y fixes de UI en las tarjetas (cards) de tutores — [PR #52](https://github.com/Tutorcito/Tutorcito/pull/52)

## Stack

| Capa | Tecnología |
|---|---|
| **Framework** | Next.js 15 (App Router), React 19, TypeScript |
| **Estilos** | Tailwind CSS 4, componentes Radix UI |
| **Auth y datos** | Supabase (Auth con Google OAuth, `@supabase/ssr` para sesión en servidor) |
| **Lint** | ESLint 9 |

## Funcionalidades

- Login con email/contraseña o **Google OAuth**, sesión persistida vía Supabase SSR
- **Onboarding en varios pasos** para completar el perfil al registrarse (`app/auth/onboarding/step1..4`)
- Perfil público de cada tutor: presentación, materias, precios y comentarios de otros usuarios
- Carrusel de recursos de estudio (Anki, Excalidraw, GeoGebra, NotebookLM)
- Cards de tutores con navegación a su perfil individual

## Estructura

```
tutorcito/
├── app/
│   ├── auth/                 # login, callback OAuth, onboarding (4 pasos)
│   ├── tutors/[tutorId]/      # perfil público de un tutor
│   └── page.tsx               # home
├── components/
│   ├── profileCard/            # header, bio, precios, acciones del perfil
│   ├── tutor/                  # bio, comentarios, tarjeta de precio
│   ├── navBar.tsx, footer.tsx
│   └── ui/                     # botones, inputs, selects (Radix)
├── context/AuthContext.tsx     # estado de sesión global
└── lib/
    ├── supabase.ts             # cliente Supabase + tipos de perfil
    └── auth.ts                 # helpers de login/registro
```

## Correr en local

```bash
npm install
# crear .env.local con:
#   NEXT_PUBLIC_SUPABASE_URL=...
#   NEXT_PUBLIC_SUPABASE_ANON_KEY=...
npm run dev
```

---

<p align="center">
  <a href="README.en.md">🇺🇸 Read this README in English</a>
</p>
