## virginiacsn.github.io

Under construction...

My personal website — about, projects, and CV — built with Astro, Tailwind CSS, and TypeScript. Deployed to GitHub Pages at [virginiacsn.github.io](https://virginiacsn.github.io).

Based on the [astro-nano](https://github.com/markhorn-dev/astro-nano) template.

### Structure

```
src/
├── content/
│   ├── projects/    # Project entries, rendered at /projects/[slug]
│   └── work/        # Work experience entries, rendered at /work/ (CV)
├── layouts/
│   └── PageLayout.astro   # Main layout wrapper used by all pages
├── pages/           # File-based routing; dynamic pages use [...slug].astro
├── styles/
│   └── global.css   # Global Tailwind directives and custom CSS
├── lib/
│   └── utils.ts     # Shared utilities (cn, formatDate, readingTime, dateRange)
└── consts.ts        # Site-wide config (title, description, social links)
```

### Commands

| Command            | Action                                     |
| :----------------- | :----------------------------------------- |
| `npm install`      | Install dependencies                       |
| `npm run dev`      | Start local dev server at `localhost:4321` |
| `npm run build`    | Type-check + build to `./dist/`            |
| `npm run preview`  | Preview production build locally           |
| `npm run lint`     | Run ESLint                                 |
| `npm run lint:fix` | Auto-fix ESLint issues                     |
