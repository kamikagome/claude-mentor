# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single-page personal marketing site for 1:1 private Claude AI classes aimed at complete beginners. The production page is `index.html` — it is the live, self-contained site shipped to [claudewithkamil.online](https://claudewithkamil.online/).

Files:
- `index.html` — the production page; all styles live in an inline `<style>` block at the top
- `Learn Claude AI.html` — the original hi-fi prototype used as the design reference
- `avatar.png` — instructor headshot used in the About section

There is no build step, no framework, no npm. Open `index.html` directly in a browser to develop.

## Architecture

Everything is in one file: `index.html`. Structure inside:

1. `<head>` — Google Fonts (Fraunces + Inter), Umami analytics, Schema.org JSON-LD, Open Graph tags
2. `<style>` block — all CSS, organized by component; CSS custom properties define all design tokens
3. `<body>` — sections in order: nav → hero → `#how` → `#about` → two-column → pull-quote → testimonials → `#book` → footer

No JavaScript. Booking uses `mailto:usmanov.kamil.pt@gmail.com`. Anchor links use `scroll-behavior: smooth` set on `html`.

## Design tokens (CSS custom properties)

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#f6f2ec` | Page background (warm cream) |
| `--paper` | `#fffdf8` | Cards (pull-quote, CTA card, testimonials) |
| `--ink` | `#1c1917` | Body text, primary button bg |
| `--dim` | `#6b6560` | Secondary text, nav links |
| `--rule` | `#e3dbcd` | Light 1px section dividers |
| `--rule-strong` | `#d8d0c4` | Dotted borders, card borders |
| `--accent` | `oklch(0.62 0.13 32)` | Coral — italic emphasis, dots, eyebrow marks (original to this site, not Anthropic brand) |

Two typefaces: **Fraunces** (variable serif, headings/italic accents, opsz axis) and **Inter** (body/nav/buttons).

## Responsive breakpoints

- `max-width: 860px` — about grid, two-column, three-up, CTA all collapse to single column
- `max-width: 720px` — `.wrap` horizontal padding drops to 24px
- `max-width: 560px` — nav hides all non-CTA links

## Open TODOs

1. **Booking flow**: CTA button uses `mailto:`. Optionally wire to a form, Calendly, or Cal.com embed.
2. **Testimonials**: only one student quote exists — add more as they come in using the `.testimonial-card` pattern.
