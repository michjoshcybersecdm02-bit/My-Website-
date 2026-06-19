# AI SEC COMMUNITY

A premium, production-grade community website for **AI SEC COMMUNITY** — the global network for AI Security and AI for Security professionals.

## About

AI SEC COMMUNITY brings together researchers, cybersecurity professionals, developers, students, and AI enthusiasts shaping the future of secure AI systems. The platform features a full marketing site with 12 homepage sections, 9 additional pages, and a rich interactive design.

## Tech Stack

- **Framework**: TanStack Start (React 19, file-based routing)
- **Styling**: Tailwind CSS v4
- **Animations**: Framer Motion
- **Language**: TypeScript
- **Deployment**: Netlify

## Design Features

- Dark theme with purple/violet brand palette
- Glassmorphism card components
- Interactive particle network background (canvas-based)
- Animated statistics counters (scroll-triggered)
- Gradient text and glow effects
- Smooth scroll reveal animations with Framer Motion
- Fully responsive (mobile-first)
- Space Grotesk headings + Inter body typography (Google Fonts)

## Pages

| Route | Description |
|-------|-------------|
| `/` | Homepage with 12 sections (Hero, Stats, Focus Areas, Events, Speakers, Resources, Benefits, Blog, Partners, FAQ, CTA, Footer) |
| `/about` | Mission, Vision, Values, Leadership Team, Roadmap |
| `/events` | Event listing with type filtering and registration |
| `/speakers` | Speaker directory + Call for Speakers form | Call for panel speaker 
| `/resources` | Searchable resource hub with categories |
| `/community` | Membership benefits and community programs |
| `/blog` | Article listing with category filters |
| `/join` | Membership tiers + registration form with social login |
| `/contact` | Contact form with multiple inquiry types |
| `/privacy` | Privacy Policy |
| `/terms` | Terms of Service |

## Running Locally

```bash
npm install
npm run dev
```

The development server runs on `http://localhost:3000`.

For Netlify feature emulation (forms, functions, etc.):

```bash
netlify dev --port 8889
```

## Brand Colors

| Variable | Value |
|----------|-------|
| Primary | `#6D28D9` |
| Secondary | `#8B5CF6` |
| Accent | `#C4B5FD` |
| Background | `#0A0A0F` |
