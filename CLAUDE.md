# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML dashboard for The Loccisano Agency's GOAL Platform account review. Single-page report deployed on Vercel as a static site.

## Architecture

- **Single HTML file** (`index.html`): Self-contained report with inline CSS and no JavaScript dependencies. All styles are in a `<style>` block; no external stylesheets or build step.
- **Deployment**: Vercel static hosting via GitHub integration. Push to `main` triggers deploy.
- **No build tools**: No npm, no bundler, no framework. Just open `index.html` in a browser to preview.

## Design System

Uses GOAL Platform brand colors defined as CSS custom properties in `:root`:
- `--goal-brand: #077BE5` (primary blue)
- `--goal-dark-blue: #00172D`
- `--goal-accent-1: #3AEECA` (teal/green accent)
- `--goal-accent-2: #97C2E8` (light blue)
- `--goal-accent-3: #9FDACD`
- Status colors: `--success-green`, `--warning-red`, `--warning-orange`

Layout uses CSS Grid and Flexbox throughout. Horizontal bar charts are pure CSS (no chart library).

## Key Sections

The report follows this structure: Header → Executive Summary → KPI Cards → Conversion Funnel → Lead Source Distribution → Search Volume by Hour → Day of Week → Lead Quality → Process Review (4 cards) → ROI Diagnostic → Recommendations (numbered 1-4) → Next Steps → Footer.

## Development

Open `index.html` directly in a browser. No server needed. For live reload during development, use any static file server (e.g., `npx serve .` or `python3 -m http.server`).
