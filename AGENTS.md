# Agent Instructions

## Project Overview

- This is a single-page React 19 portfolio built with TypeScript and Vite.
- Application composition lives in [src/App.tsx](src/App.tsx); the entry point is [src/main.tsx](src/main.tsx).
- Each major portfolio section is an independently owned component in [src/components](src/components): hero, about, projects, skills, experience, and contact.
- Shared scroll behavior is implemented by [src/components/ScrollStack.tsx](src/components/ScrollStack.tsx) and [src/components/ScrollStack.css](src/components/ScrollStack.css).
- Static media belongs in [public](public), including the existing video assets in [public/videos](public/videos).

## Commands

- Install dependencies with `npm install`.
- Start local development with `npm run dev`.
- Run the production typecheck and build with `npm run build`.
- Run lint with `npm run lint`.
- Preview the built output with `npm run preview`.
- There is currently no test script or test framework; use the build and lint commands plus focused browser checks for UI changes.

## Conventions

- Keep section-specific markup, content, and interaction logic in its owning component. Change [src/App.tsx](src/App.tsx) only for page composition or shared layout concerns.
- Use Tailwind utilities for component styling. Keep global resets, font imports, and document-level behavior in [src/index.css](src/index.css).
- Preserve the established visual language: cinematic black backgrounds, warm gold/brown accents, responsive layouts, Framer Motion animation, and Lenis-based scrolling.
- Reuse the existing React, Framer Motion, Lenis, and Tailwind dependencies before introducing new packages or abstractions.
- Keep public asset paths rooted at `/`; verify that referenced files exist under [public](public).
- Preserve the existing TypeScript style and avoid unrelated formatting or refactors.

## Validation and Pitfalls

- After edits, run `npm run lint` and `npm run build`.
- For visual changes, also inspect the page at desktop and mobile widths; check animation, video loading, keyboard focus, and reduced-motion behavior where relevant.
- Portfolio content is currently hardcoded in section components, so update the nearest owning component rather than creating a data layer for a one-off change.
- The contact form currently provides local UI feedback only; do not imply that it sends email or reaches a backend unless an integration is added.
- The resume link in [src/components/HeroSection.tsx](src/components/HeroSection.tsx) requires `public/resume.pdf`, which is not currently present.
- The existing README is the default Vite template; do not treat it as authoritative project documentation until it is updated.
