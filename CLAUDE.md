# CLAUDE.md — Web Portfolio

## Project Overview
Personal portfolio for **Leticia Cezar** — Operations & Process Improvement, building internal tools (often with AI) that cut admin and make work easier for teams. London, UK.
Single-page site aimed at **hiring managers** (recruiters skim too). Primary goal: **get them to email Leticia.**

## Direction & Tone
- **Designed and bold** — confident colour, strong hierarchy, one dominant moment per screen. Deliberately NOT a safe, low-contrast template.
- **Warm + capable + approachable** — bold visuals balanced by a real photo and human, plain-spoken copy.
- **Personality thread:** self-taught, loves to learn, driven to help employees *and* the company thrive. AI/tooling is framed as a means to a human end.
- **Adjectives to convey:** knowledgeable, competent, resourceful — each project should *demonstrate* one, not just claim it.
- **No invented metrics.** Use honest qualitative outcomes (e.g. "replaced a manual spreadsheet process"). Never fabricate stats.

## Architecture
- **One file:** `index.html` — all HTML, CSS, and JavaScript embedded.
- **No build tools, no framework, no package.json.**
- **CDN-only dependencies.** Opens directly in a browser.
- Set-and-forget, but kept easy to edit (clear tokens + repeatable case-study pattern).

## CDN Dependencies
| Library | Version | Purpose |
|---|---|---|
| Google Fonts — Space Grotesk | 400–700 | Display / headings |
| Google Fonts — Inter | 400–700 | Body text |
| Font Awesome | 6.5.0 | Icons |

(Scroll animations use a native `IntersectionObserver` — no animation library/CDN.)

## Design System

### Colours (CSS custom properties in `:root`)
| Variable | Value | Use |
|---|---|---|
| `--ink` | `#34281f` | Warm soft-brown — headings & text (not pure black) |
| `--ink-soft` | `#5a4d42` | Body text |
| `--ink-mute` | `#837467` | Secondary text |
| `--cream` | `#ffffff` | Clean white page canvas |
| `--cream-deep` | `#ffe9d4` | Peachy tinted panels (About, footer) |
| `--paper` | `#ffffff` | Cards |
| `--coral` | `#ff6a45` | Primary bold accent — bright & happy |
| `--coral-deep` | `#ed4d28` | Hover / pressed |
| `--teal` / `--teal-deep` | `#14b8a6` / `#0e9787` | Mint-teal pop — Contact gradient, "Open the tool" buttons, live dot |
| `--sun` / `--sun-deep` | `#ffc24a` / `#f5a623` | Sunny yellow — KPI banner gradient, Contact `.mark` |
| `--border` / `--border-soft` | rgba ink | Borders |

**Palette mood:** bright and happy, no large dark surfaces. Coral leads; teal and sun are supporting pops (used where the design previously went ink-black: the KPI featured banner now coral→sun, Contact now teal, footer now peach). Keep it to these three accents — don't add more hues without asking.

### Typography
- **Display/headings:** Space Grotesk (700) — gives the bold, designed character.
- **Body:** Inter. Base 1rem, line-height 1.6.
- **Hero H1:** `clamp(2.6rem, 5.4vw, 4.2rem)`. One word/phrase highlighted with `.mark` (coral + underline swash).

### Responsive Breakpoints
- `≤ 900px` — hero & about stack; case study body goes single-column.
- `≤ 680px` — hamburger nav, single column, compact case summaries.
- `≤ 420px` — small-phone spacing.

## Page Sections (top → bottom)
1. **Nav** — sticky glass blur; links + dark "Get in touch" CTA; hamburger on mobile.
2. **Hero** — availability pill, bold headline with coral `.mark`, positioning line, Email/See-work CTAs, location + language meta, photo with coral offset block + "Self-taught" float badge.
3. **About** — `cream-deep` panel; lead line + bio + chips on the left, three trait cards (Knowledgeable / Competent / Resourceful) on the right.
4. **Work** — expandable case studies (`<details>`). **KPI Calculator is `.featured`** (ink banner, larger) and sits first. Each opens to Problem → Built → Changed + screenshot + "Open the tool" link.
5. **Contact** — full ink section; coral `.mark` headline; email-copy button (primary) + LinkedIn; social row.
6. **Footer** — ink, available status + version.
7. **Back-to-top** — coral rounded button, appears after 320px scroll.

## Project Links (relative `href`s)
| Case | Path |
|---|---|
| 01 KPI Performance Calculator (featured) | `../9- KPI Performance/index.html` |
| 02 Line Test Checklist | `../13- Line Test Support/index.html` |
| 03 Onboarding Process Map | `../7-onboarding-mapping/screenwise-onboarding-side-by-side.html` |
| 04 Infographics | `#` (no live tool yet) |

## Assets (in `assets/`)
`profile.jpeg`, `performance-calc-allocations.png`, `line-test-checklist.png`, `onboarding-map.png`, `screenwise-points-guide.png`.

## Live Links
- **Email:** leticiafcezar@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/leticiafcezar/

## How to Extend

### Add a case study
Copy a non-featured `<details class="case reveal">` block in `#work`. Update: `.case-num`, `<h3>`, summary `<p>`, the `.case-tag`s, the three `.story-block`s (The friction / What I built / What changed), the `.case-shot` image, and the `.case-actions` link `href`. Keep collapsed by default (only the featured KPI case has `open`).

### Make a case the featured one
Add `featured` to its class and a `<span class="featured-flag">…</span>` inside `.case-head`. Only one featured case at a time.

### Add a profile photo
Already wired: `.hero-photo-frame img` uses `assets/profile.jpeg`. Swap the file or the `src`.

## Conventions
- **Keep everything in `index.html`** — don't split CSS/JS unless asked.
- **No new CDNs** without asking first.
- **Mobile-first** — test every layout change at 375px and 1280px; nothing may overflow.
- **No inline-style overrides** that fight the CSS (this was the old file's main bug). Style via classes/tokens.
- **Reveal animation** — add class `reveal` to new blocks; the IntersectionObserver fades them in.
- **Always read `index.html` before editing** — it is the single source of truth.

## Do Not Change Without Asking
- The single-file architecture (`index.html` only).
- CDN versions.
- The single-accent (coral) discipline — no extra accent colours.
- Relative `href`s to the live tools.
- The "no invented metrics" rule for project copy.
