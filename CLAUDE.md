# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Astro static site for Folsom Lake Accounting, a CPA business website. Styled with Tailwind CSS, using Inter (body) and Source Serif 4 (headings) fonts.

## Commands

**Local development:**

```bash
mise run dev
```

**Production build:**

```bash
mise run build
```

## Architecture

- **src/data/siteData.ts**: All site content and configuration (business info, hero text, services, nav links)
- **src/layouts/BaseLayout.astro**: HTML shell with meta tags, fonts, GA4, Calendly widget, Navbar, Footer
- **src/components/**: Astro components (Navbar, Hero, Services, ServiceCard, Reviews, Contact, AboutHero, Footer, CalendlyWidget)
- **src/pages/**: Route pages (index.astro, about.astro)
- **src/styles/global.css**: Tailwind directives and base styles
- **public/assets/**: Images and static files
- **tailwind.config.mjs**: Tailwind theme with brand color palette and font families

## Tool Management

All tools (Node, npm, etc.) are managed by [mise](https://mise.jdx.dev/). Always use `mise run` to build, test, and run dev commands — never call `npm` directly. This ensures the correct tool versions are used.

## Deployment

- CI runs on pull requests (`.github/workflows/ci.yml`) — `npm ci && npm run build`
- Pushes to `main` auto-deploy to Vercel (output dir: `dist/`)
- Node 22, managed locally via mise
