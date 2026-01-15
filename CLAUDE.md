# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site for Folsom Lake Accounting, a CPA business website. The site uses the Graysx theme (a fork of StartBootstrap Grayscale).

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

- **config.toml**: Site configuration including business info (address, phone, email), navigation menu, and theme settings
- **data/homepage.yml**: All homepage content (hero section, about text, service cards) - this is where most content edits happen
- **themes/graysx/**: The Graysx Hugo theme
  - `layouts/index.html`: Main homepage template
  - `layouts/partials/`: Header, footer, and head partials
- **static/assets/**: Images and static files

## Deployment

- CI runs on pull requests (`.github/workflows/ci.yml`) - builds with Hugo to verify no errors
- Pushes to `main` auto-deploy to GitHub Pages (`.github/workflows/publish.yml`)
- Hugo version: 0.104.1 (extended), managed locally via mise
