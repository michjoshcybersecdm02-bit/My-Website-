# AGENTS.md — AI SEC COMMUNITY

Reference guide for AI agents working in this codebase.

## Architecture

This is a **TanStack Start** application (React 19, SSR-capable) deployed on Netlify.

### Key Directories

```
src/
├── components/         # Shared UI components
│   ├── Navbar.tsx      # Sticky nav with mobile drawer, scroll detection
│   ├── Footer.tsx      # Full footer with newsletter signup
│   └── ParticleBackground.tsx  # Canvas-based animated particle network
├── data/
│   └── siteData.ts     # All placeholder data (stats, events, speakers, etc.)
├── routes/             # File-based pages (TanStack Router)
│   ├── __root.tsx      # Root shell: head tags, nav, footer, particle bg
│   ├── index.tsx       # Homepage (12 sections)
│   ├── about.tsx
│   ├── events.tsx
│   ├── speakers.tsx
│   ├── resources.tsx
│   ├── community.tsx
│   ├── blog.tsx
│   ├── join.tsx
│   ├── contact.tsx
│   ├── privacy.tsx
│   └── terms.tsx
└── styles.css          # Global styles, CSS variables, utility classes
```

## Coding Conventions

- **File-based routing**: every new page goes in `src/routes/` using `createFileRoute`
- **Animations**: use Framer Motion `motion.*` with `whileInView` + `viewport={{ once: true }}` for scroll reveals
- **Glassmorphism**: apply `.glass` or `.glass-dark` CSS classes for card backgrounds
- **Gradient text**: use `.gradient-text` class for purple gradient text
- **Section pattern**: `<section className="section-padding relative">` with `<div className="max-w-7xl mx-auto">` inner container
- **Data**: all mock data lives in `src/data/siteData.ts`
- **No comments on obvious code** — self-documenting names preferred

## Design System

| Token | Value |
|-------|-------|
| Primary | `#6D28D9` (purple) |
| Secondary | `#8B5CF6` (violet) |
| Accent | `#C4B5FD` (light purple) |
| Background | `#0A0A0F` (near black) |
| Font headings | Space Grotesk (Google Fonts) |
| Font body | Inter (Google Fonts) |

CSS utilities in `src/styles.css`:
- `.glass` — glassmorphism panel
- `.gradient-text` — purple gradient text  
- `.glow-text` — text-shadow glow
- `.card-hover` — lift + shadow on hover
- `.section-padding` — responsive vertical padding
- `.grid-bg` — subtle dot-grid background
- `.radial-glow` — radial purple glow overlay

## Non-Obvious Decisions

- `ParticleBackground` renders as `position: fixed` canvas (z-index 0); all page content is in a `relative z-10` wrapper in `__root.tsx`
- The particle canvas has `pointer-events: none` so it doesn't block user interaction
- Google Fonts loaded via CSS `@import` in `styles.css` (not `<link>` tags) to avoid SSR hydration issues
- `'use client'` directive on components that use browser APIs (canvas, window)
- `Counter` uses `useInView` from framer-motion to trigger count-up animation on scroll

## Adding a New Page

1. Create `src/routes/<name>.tsx`
2. Export `export const Route = createFileRoute('/<name>')({ ... })`
3. Add nav link in `src/components/Navbar.tsx` if needed
4. Add data to `src/data/siteData.ts` if needed

## Database

No database currently wired. For persistence (registrations, newsletters), use `@netlify/database` with Drizzle ORM. Define schemas in `db/schema.ts`.
