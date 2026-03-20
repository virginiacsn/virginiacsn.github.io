# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev          # Start dev server at localhost:4321
npm run build        # Type-check (astro check) + build to ./dist/
npm run preview      # Preview production build locally
npm run lint         # Run ESLint
npm run lint:fix     # Auto-fix ESLint issues
```

No test suite is configured.

## Architecture

This is an **Astro** static site (portfolio + blog) deployed to GitHub Pages at `https://virginiacsn.github.io`. It uses **Tailwind CSS** for styling with the Typography plugin for prose content, and **TypeScript** in strict mode.

### Content Collections

All dynamic content lives in `src/content/` and is managed via Astro Content Collections with Zod schemas defined in `src/content/config.ts`. The three collections are:

- `blog/` — Blog posts (Markdown/MDX), rendered at `/blog/[slug]`
- `projects/` — Project entries, rendered at `/projects/[slug]`
- `work/` — Work experience entries, rendered at `/work/`

### Routing

File-based routing in `src/pages/`. Dynamic collection pages use `[...slug].astro` pattern and call `getCollection()` + `getStaticPaths()` to generate static routes at build time.

### Key Files

- `src/consts.ts` — Site-wide configuration (title, description, social links, etc.)
- `src/lib/utils.ts` — Shared utilities: `cn()` (clsx + tailwind-merge), `formatDate()`, `readingTime()`, `dateRange()`
- `src/layouts/PageLayout.astro` — Main layout wrapper used by all pages
- `src/styles/global.css` — Global Tailwind directives and custom CSS; dark mode via `class` strategy

### Path Aliases

`@/*` resolves to `src/*` (configured in `tsconfig.json`).

### Deployment

Push to `main` triggers the GitHub Actions workflow (`.github/workflows/deploy.yml`), which runs `npm run build` and deploys `./dist/` to GitHub Pages.
