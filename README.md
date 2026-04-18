# Handoff: Learn Claude AI — 1:1 Classes Personal Site

## Overview
A single-page personal marketing site for a solo instructor offering 1:1 private Claude AI classes aimed at complete beginners. The site's job is to establish trust quickly, explain how a session works, introduce the teacher, and drive the visitor to a booking email. Tone is warm, literary, and quiet — intentionally the opposite of a typical SaaS landing page.

## About the Design Files
The file bundled here (`Learn Claude AI.html`) is a **design reference**, created in plain HTML/CSS as a fully-styled prototype. It is not production code to copy and ship directly.

Your task is to **recreate this design in the target codebase's existing environment** — React/Next.js, Astro, Eleventy, a static site generator, or whatever already exists for this project — using that codebase's established component patterns, styling solution (CSS modules, Tailwind, vanilla CSS, etc.), and conventions. If there is no codebase yet, choose the simplest appropriate framework (for a one-pager like this, static HTML/CSS or Astro/Eleventy is a reasonable default; Next.js is fine if more pages are planned).

The HTML file is self-contained and can be opened directly in a browser to reference pixel-level appearance, hover states, and responsive breakpoints.

## Fidelity
**High-fidelity (hifi).** Colors, typography, spacing, hover states, and responsive breakpoints are all final. Recreate pixel-perfectly using the codebase's existing libraries and patterns. Exact token values are listed in the Design Tokens section below.

## Sections (single page, in order)

### 1. Top nav
- **Purpose**: Identity + inline anchor nav + primary CTA
- **Layout**: Flex row, `justify-content: space-between`, vertical padding 28px, horizontal padding matches page wrap (56px desktop, 24px mobile)
- **Components**:
  - **Brand**: 18×18 coral circle + text "Learn Claude", weight 500, size 13px
  - **Links**: "How it works", "About", "Book a class →" — gap 28px, color `--dim`, hover → `--ink`
  - **Responsive**: below 560px, hide all non-CTA links

### 2. Hero
- **Purpose**: Position the service and drive the primary CTA
- **Layout**: Vertical stack inside page wrap; padding 56px top / 96px bottom
- **Components**:
  - **Eyebrow**: "1:1 private classes · for complete beginners", 13px, color `--accent`, preceded by a 28×1px accent-colored rule
  - **Headline** (`h1.hero-title`): Fraunces serif, weight 400, size `clamp(44px, 7vw, 84px)`, line-height 1.02, letter-spacing -0.035em. Two lines:
    - "Learn Claude AI," (ink)
    - "*one quiet hour at a time.*" (italic, accent)
  - **Lede**: Inter, 18px, line-height 1.55, color `--dim`, max-width 580px, margin-top 32px
  - **Actions row** (gap 12px, margin-top 36px):
    - Primary button: "Book your first class →" — ink bg, bg color text, padding 14px/22px, radius 999px
    - Ghost button: "See how a session works" — transparent bg, 1px `--rule-strong` border, same radius
    - Hover on primary → bg `#000`; hover on ghost → bg `#ede6d9`; arrow on primary nudges 3px right on hover (transition 160ms)
  - **Meta row**: three inline items with 6px accent-colored dots — "60-minute sessions", "Online, 1:1", "Work remotely with students anywhere"

### 3. How it works
- **Section header** (in `.wrap.section-pad`): eyebrow "— How it works" (Fraunces italic 14px accent), title "We learn by doing, not by watching slides." (Fraunces 400, `clamp(28px, 3.6vw, 40px)`), subtitle paragraph in `--dim`
- **Three-up grid**: `grid-template-columns: repeat(3, 1fr)` with 1px vertical dividers (color `--rule`). Each cell has padding 48px/40px.
  - Cell: italic numbered kicker ("— 01/02/03" accent Fraunces), Fraunces h3 (22px, line-height 1.2), supporting paragraph in `--dim` 14.5px
  - Content:
    1. "We start with your goals" — figure out what they actually want to do
    2. "You try it, live" — student drives from first class
    3. "You leave with something you can use today" — a practical takeaway per session
- **Responsive**: stack to single column below 860px; dividers become bottom borders

### 4. About
- **Layout**: `grid-template-columns: 1fr 1.1fr`, gap 56px, align-items start
- **Portrait**: `aspect-ratio: 4/5`, 4px radius, background placeholder using 135° repeating-linear-gradient of two warm tans (`#e4d9c2` and `#ece3cf` at 8px stripes) with a centered monospace label "your photo here" (12px, `#8b7f6a`, `--bg` chip)
  - **TODO for developer**: replace placeholder with real `<img>` once the instructor provides a headshot; keep 4:5 aspect-ratio and 4px radius
- **Bio column**:
  - Title (Fraunces, matches `.section-title`): "Someone who genuinely enjoys making this stuff click."
  - Paragraph 1: "I work remotely in the tech industry, where AI is part of my daily work. I've been teaching people one-on-one for more than five years — so I know how to explain things clearly, at your pace, without ever making you feel behind."
  - Paragraph 2 (color `--dim`): "My students are small business owners, writers, consultants, retirees, and curious beginners. What they have in common is that they wanted a real person to learn with — not another YouTube tutorial."
  - Certificates list (dotted 1px `--rule-strong` bottom borders, 14px padding):
    - "Claude AI — Certified" / "Anthropic"
    - "Gemini AI — Certified" / "Google · Coursera"
    - "5+ years of 1:1 mentoring" / "Independent"
- **Responsive**: single column below 860px; portrait max-width 420px and flips to 5:4 aspect-ratio

### 5. Two-column list section
- **Layout**: `grid-template-columns: 1fr 1fr`, gap 72px, single column below 860px
- **Left column**: eyebrow "— Each session includes", subhead "A class that actually fits." (Fraunces 26px), bulleted list:
  - A focused 1:1 lesson built entirely around your goals
  - Real, hands-on practice from the very first session
  - A judgment-free space to ask anything — no question is too basic
  - Practical takeaways you can use the same day
- **Right column**: eyebrow "— This is for you if", subhead "You've been curious, but unsure where to begin.", bulleted list:
  - You've heard about Claude AI but have no idea where to start
  - You've tried it, felt confused, and quietly gave up
  - You want to learn with a real person, not a video on 2× speed
  - You're worried AI is "too technical" for you — it isn't
- **List styling**: `ul.list` with a 14×1px accent-colored mark 28px from the left replacing the bullet; 1px `--rule` bottom border between items; no bottom border on the last item

### 6. Pull-quote
- **Purpose**: Reinforce the "1:1 works" value prop
- **Component**: `.pullquote` card, `--paper` bg, 1px `--rule` border, 4px radius, padding 40px/44px
  - Kicker: "A note to the beginner" (Inter 11px uppercase, letter-spacing 0.12em, `--dim`)
  - Body (Fraunces 22px, line-height 1.45): "It is proven that 1:1 learning is the most effective way to learn anything — because it provides personalized instruction, immediate feedback, and *consistent engagement.*" (last fragment italicized in `--accent`)
  - No signature

### 7. Booking CTA
- **Layout**: `grid-template-columns: 1.3fr 1fr`, gap 48px, align-items center (single column below 860px)
- **Left**: eyebrow "— Book your first class", large headline (Fraunces, `clamp(32px, 4.2vw, 48px)`, line-height 1.08):
  - "One hour."
  - "One-on-one."
  - "*Starts with your first question.*" (italic, accent)
  - Supporting paragraph below in `--dim`
- **Right (`.cta-card`)**: `--paper` bg, 1px `--rule-strong` border, padding 28px
  - Four rows separated by dotted `--rule-strong` borders:
    - Format · 1:1, online
    - Length · 60 minutes
    - Experience needed · None
    - First session · Intro rate
  - Full-width primary button "Request a time →" — `mailto:hello@learnclaude.example`
  - **TODO for developer**: swap mailto for real address, or wire to a form/Calendly/Cal.com embed

### 8. Footer
- **Layout**: Flex row, 1px `--rule` top border, padding 28px vertical
- **Left**: 12px accent dot + "Learn Claude"
- **Right**: "hello@learnclaude.example" (replace with real address)

## Interactions & Behavior

- **Buttons**: `transition: transform 120ms ease, background 120ms ease`. `:active` translateY(1px). Primary button hover → bg `#000`. Ghost hover → bg `#ede6d9`. Arrow glyph inside primary button translates 3px on hover (`transition: transform 160ms ease`).
- **Nav links**: color transition from `--dim` to `--ink` on hover.
- **Anchor scrolling**: nav links point to `#how`, `#about`, `#book`. Add `scroll-behavior: smooth` on `html` if the codebase doesn't already globally set it.
- **No client-side state or JS** in the current prototype — the whole page is static. Booking is handled by a mailto. If the target codebase wants a form, wire it through its existing form solution.

## State Management
None. This is a static marketing page. Any future contact form should use the codebase's existing form handling (server action, API route, third-party embed, etc.).

## Design Tokens

### Colors
| Token | Value | Usage |
|---|---|---|
| `--bg` | `#f6f2ec` | Page background (warm cream) |
| `--paper` | `#fffdf8` | Cards (pull-quote, CTA card) |
| `--ink` | `#1c1917` | Body text, primary button bg |
| `--dim` | `#6b6560` | Secondary text, nav links |
| `--rule` | `#e3dbcd` | Light 1px section dividers |
| `--rule-strong` | `#d8d0c4` | Stronger dotted borders, card borders |
| `--accent` | `oklch(0.62 0.13 32)` | Warm coral — italic emphasis, dots, eyebrow marks |
| `--accent-soft` | `oklch(0.62 0.13 32 / 0.10)` | (declared, currently unused — safe to drop) |

### Typography
- **Display**: `"Fraunces", "Tiempos Headline", "GT Super", Georgia, serif` — used for all headings and italic accents. Weights used: 400, 500. Optical size axis is present (Fraunces variable).
- **Sans**: `"Inter", "Söhne", system-ui, -apple-system, sans-serif` — body, nav, buttons, kickers.
- **Google Fonts import**: `Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,500;0,9..144,600;1,9..144,400;1,9..144,500` + `Inter:wght@400;500;600`.
- **Scale**:
  - Body: 16px / 1.5
  - Hero headline: `clamp(44px, 7vw, 84px)` / 1.02 / -0.035em
  - Section title: `clamp(28px, 3.6vw, 40px)` / 1.1 / -0.025em
  - Subhead (`h3.sub`): 26px / 1.15 / -0.02em
  - Three-up h3: 22px / 1.2 / -0.015em
  - Pull-quote body: 22px / 1.45 / -0.01em
  - Lede: 18px / 1.55
  - List items: 15.5px / 1.5
  - Section sub / bio: 16px / 1.6
  - Kicker: 11px uppercase, letter-spacing 0.12em
  - Meta / cert issuer: 13–14px

### Spacing
- Page wrap max-width: **1120px**, horizontal padding **56px** (desktop) / **24px** (≤720px)
- Section vertical padding: **72px** (`.section-pad`)
- Hero top/bottom: **56px / 96px**
- Grid gaps: **56px** (about), **72px** (two-column), **48px** (CTA)
- Button padding: **14px / 22px**, radius **999px**
- Card padding: **28px** (CTA card), **40px / 44px** (pull-quote)

### Borders & radii
- Card radius: **4px**
- Button radius: **999px** (pill)
- Dividers: 1px `--rule`; dotted rows: 1px dotted `--rule-strong`

### Responsive breakpoints
- `max-width: 860px` → about grid, two-column, three-up, CTA all collapse to single column
- `max-width: 720px` → `.wrap` horizontal padding drops to 24px
- `max-width: 560px` → nav hides non-CTA links

## Assets
- **Fonts**: Fraunces + Inter, loaded from Google Fonts via `<link>` in the current prototype. In a real codebase prefer self-hosting or the framework's font loader (e.g. `next/font`).
- **Imagery**: None shipped. The About section has a placeholder block that needs to be replaced with a real headshot. No icons, no illustrations — do not add any.
- **Email address**: `hello@learnclaude.example` is a placeholder throughout — swap for the real one.

## Notes on Brand Usage
This site is a teacher-facing personal site mentioning Claude by name, not an Anthropic property. Use only the product name in running copy; do not lift Anthropic wordmarks, logos, or trade dress. The coral accent in this design is an **original color choice for this site**, not an Anthropic brand color.

## Files
- `Learn Claude AI.html` — the full hi-fi prototype. Open in a browser to reference exact visuals, hover states, and responsive behavior. All styles are inline in a `<style>` block at the top of the file.
