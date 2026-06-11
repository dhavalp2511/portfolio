# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A static portfolio website (single page) built with Astro 5 and Tailwind CSS v4 — no React or other UI framework runtime — deployed to GitHub Pages. Bun is the package manager. The design is an "engineering record / drafting sheet" aesthetic: paper/ink/vermilion palette, Fraunces + Archivo + IBM Plex Mono, sections numbered FIG. 01–06.

## Commands

```bash
bun install          # Install dependencies
bun run dev          # Dev server at localhost:4321
bun run build        # Production build to ./dist/
bun run preview      # Preview the production build
bun run type-check   # astro check (TypeScript validation)
bun run lint         # ESLint over .js/.jsx/.ts/.tsx/.astro
bun run deploy       # Manual deploy (build + gh-pages -d dist)
```

There are no tests. Before committing, run `bun run build` to catch type/import errors.

Deployment is normally automatic: `.github/workflows/deploy.yml` builds and publishes to GitHub Pages on every push to `main`.

## Architecture

This is a content-driven single-page site. The data flow is:

1. **Content lives in JSON** — `src/data/*.json` (`personal.json`, `about.json`, `projects.json`, `experience.json`, `education.json`). Text/content changes are made here, not in components.
2. **Section components render the JSON** — `src/components/sections/*.astro` each import their data file and render one page section (Intro, About, Projects, Experience, Education, Footer).
3. **`src/pages/index.astro`** (the only page) composes all sections inside `src/layouts/Layout.astro`, plus `Navigation.astro`.

### Interactivity model

Everything is `.astro` components (PascalCase names, despite what `.cursorrules` says). Interactivity is plain `<script>` tags: an IntersectionObserver in `Layout.astro` drives `.reveal` scroll animations, and `Navigation.astro` handles the mobile menu and scrolled-header state. All animations have `prefers-reduced-motion` fallbacks — keep that invariant when adding motion.

### GitHub Pages base path

`astro.config.mjs` sets `base: "/portfolio"`. All internal links and asset URLs must account for this prefix (use `import.meta.env.BASE_URL` or Astro's URL helpers) or they will 404 in production while working in dev.

## Conventions

- TypeScript strict mode (`astro/tsconfigs/strict`).
- Styling is Tailwind-first (v4, via the `@tailwindcss/vite` plugin — there is no `tailwind.config` file). Design tokens (colors `paper`/`ink`/`vermilion`/`ember`/`rule`, fonts `display`/`body`/`mono`) live in the `@theme` block of `src/styles/global.css`, alongside shared primitives (`.shell`, `.stamp`, `.mono-label`, `.fig-head`, `.reveal`). Component-scoped styles go in the `.astro` file's `<style>` block. Dark sections use the `.dark-zone` class, which flips the rule/muted/accent variables locally.
- Shared primitives in `global.css` are unlayered, so overriding them with a utility needs Tailwind v4's trailing important modifier (`py-1!`, not `!py-1`).
- Mobile-first responsive design using Tailwind prefixes (`sm:`, `md:`, `lg:`); touch targets ≥ 44px.
- Keep JSON data files flat and simple; key shapes are documented in `.cursorrules` (e.g. `Project` has `id`, `title`, `description`, `image`, `technologies`, `features`, optional `liveUrl`/`githubUrl`, `status`, `date`).
- Use semantic HTML and ARIA labels; lazy-load heavy components with `client:visible`.
