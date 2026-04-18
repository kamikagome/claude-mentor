# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A design handoff for a single-page personal marketing site: 1:1 private Claude AI classes for complete beginners. The repository contains two files:

- `Learn Claude AI.html` — the hi-fi prototype. Open in a browser to verify colors, hover states, and responsive behavior. All styles live in an inline `<style>` block at the top.
- `README.md` — the full implementation spec: sections, design tokens, interactions, responsive breakpoints, and developer TODOs.

## Implementation goal

Recreate the design in whatever target framework exists (React/Next.js, Astro, Eleventy, or plain HTML/CSS). If no codebase exists yet, static HTML/CSS or Astro is preferred for a one-pager; Next.js if more pages are planned. The HTML file is a reference, not code to ship directly.

## Fidelity expectation

**High-fidelity.** Colors, typography, spacing, hover states, and responsive breakpoints are all final. Match the spec in README.md exactly.

## Key design decisions

- **No JavaScript or client-side state** — the page is fully static. Booking uses a mailto link.
- **Two typefaces**: Fraunces (serif, variable, opsz axis) for headings/italic accents; Inter for body/nav/buttons. Load from Google Fonts or self-host via the framework's font loader.
- **Three responsive breakpoints**: 860px (grid collapse), 720px (wrap padding drops to 24px), 560px (nav hides non-CTA links).
- The coral `--accent` color (`oklch(0.62 0.13 32)`) is original to this site — not an Anthropic brand color.

## Open TODOs (from README)

1. **About photo**: replace the CSS placeholder gradient with a real `<img>` at 4:5 aspect-ratio, 4px radius.
2. **Email address**: `hello@learnclaude.example` appears in the footer and the CTA button `mailto:` — replace with the real address.
3. **Booking flow**: CTA button currently uses `mailto:`. Optionally wire to a form, Calendly, or Cal.com embed using the target codebase's form solution.
