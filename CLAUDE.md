# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Appraiseye company marketing website (appraiseye.io). AI vision systems for surgical OR efficiency and Cell & Gene Therapy (CGT) manufacturing automation.

## Architecture

Pure static HTML site — no build tools, no package manager, no frameworks.

- **index.html** — Main landing page (~1400 lines). Contains all CSS (inline `<style>` block), vanilla JS, and HTML in a single file.
- **careers.html** — Careers/jobs page (~1500 lines). Same self-contained pattern.
- **Assets/** — Images (PNG + JPG): product shots, team photos, logos, news images.
- **CNAME** — GitHub Pages custom domain config (`appraiseye.io`).

All styling uses CSS custom variables defined at the top of each HTML file. Design system: dark theme with purple/cyan accents, Google Fonts (Inter, Space Grotesk).

JS features are vanilla: Intersection Observer for scroll animations, dynamic nav background, mobile menu toggle. No external libraries.

## Deployment

GitHub Pages from the `main` branch. Push to `main` = deploy to appraiseye.io. No CI/CD pipeline or build step.

## Development

No build, lint, or test commands. Edit HTML files directly. To preview locally, open the HTML file in a browser or use any static file server (e.g., `python3 -m http.server`).

## Key Conventions

- CSS and JS are embedded inline within each HTML file, not in separate files.
- Google Analytics is integrated (GA4: G-KD9GL2SSX4).
- Images go in `Assets/` directory.
- Responsive design uses media queries within the inline `<style>` block.

## Coding Guidelines

### Think Before Coding
- State assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them — don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.

### Simplicity First
- Minimum code that solves the problem. Nothing speculative.
- No features, abstractions, or "flexibility" beyond what was asked.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

### Surgical Changes
- Touch only what you must. Don't "improve" adjacent code, comments, or formatting.
- Match existing style, even if you'd do it differently.
- Remove imports/variables/functions that YOUR changes made unused. Don't remove pre-existing dead code unless asked.
- Every changed line should trace directly to the user's request.

### Goal-Driven Execution
- Transform tasks into verifiable goals with success criteria.
- For multi-step tasks, state a brief plan with verification checks.
- Loop until verified — don't stop at "it should work."
