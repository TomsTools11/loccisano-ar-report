# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML reporting hub for The Loccisano Agency's GOAL Platform NJ Auto campaign. A landing page links to individual report pages. Deployed on Vercel as a static site.

## Architecture

- **Landing page** (`index.html`): Reporting hub built on the structured dashboard template (navy sidebar + main content). Contains one card per report linking into `reports/`.
- **Reports** (`reports/*.html`): Self-contained report pages with inline CSS (and inline base64 logo). No JavaScript dependencies, no build step.
- **Shared assets** (`assets/`): `goal-logo.png` used by the landing page sidebar.
- **Deployment**: Vercel static hosting via GitHub integration. Push to `main` triggers deploy.
- **No build tools**: No npm, no bundler, no framework. Just open `index.html` in a browser to preview.

## Design System

Structured dashboard template using Inter (Google Fonts) and GOAL Platform brand colors defined as CSS custom properties in `:root`:
- `--blue: #057BE5` (primary blue)
- `--navy: #00172D` (sidebar background)
- `--mint: #3BEECA` (teal/green accent)
- `--ink: #0F1B2D`, `--body: #2B3442`, `--muted: #6A7482` (text)
- Status colors: `--success: #2BBF7A`, `--warning: #F0A93B`

Layout uses CSS Grid and Flexbox throughout: a 288px sticky navy sidebar (logo, title, nav, footer) and a main column of numbered blocks. Charts in reports are pure CSS (no chart library).

## Key Pages

- `index.html` — landing page: sidebar → executive summary → report cards (one per report, linking into `reports/`).
- `reports/campaign-performance-june-2026.html` — week-over-week campaign performance (key metrics, lead volume by day, conversion funnel, daily detail).
- `reports/lead-volume-plan-june-2026.html` — optimization updates applied June 8–11, 2026 (updates at a glance, update detail, early read, unchanged settings, next steps).

When adding a new report: drop the self-contained HTML file in `reports/` and add a matching card + sidebar nav link on `index.html`.

## Development

Open `index.html` directly in a browser. No server needed. For live reload during development, use any static file server (e.g., `npx serve .` or `python3 -m http.server`).
