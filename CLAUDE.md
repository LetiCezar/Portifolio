# CLAUDE.md — Web Portfolio

## Project Overview
Personal portfolio for **Leticia Cezar** — Panel Service Executive, Screenwise, London UK.
Single-page site showcasing her internal tools and operational projects.

## Architecture
- **One file:** `index.html` — all HTML, CSS, and JavaScript are embedded here
- **No build tools, no framework, no package.json**
- **CDN-only dependencies** (no local node_modules or vendor folders)
- Opens directly in a browser; no local server needed

## CDN Dependencies
| Library | Version | Purpose |
|---|---|---|
| Google Fonts — Inter | 400–800 | Primary typeface |
| Font Awesome | 6.5.0 | Icons throughout |
| AOS (Animate on Scroll) | 2.3.4 | Scroll-triggered entrance animations |

## Design System

### Colors (CSS custom properties in `:root`)
| Variable | Value | Use |
|---|---|---|
| `--accent` | `#75975e` | Sage green accent — buttons, links, highlights |
| `--accent-dark` | `#4b6043` | Hover state / darker green |
| `--accent-muted` | `rgba(117, 151, 94, 0.08)` | Subtle tinted backgrounds |
| `--text-heading` | `#111827` | Section titles, card headings |
| `--text-body` | `#4B5563` | Body copy |
| `--text-light` | `#9CA3AF` | Secondary/muted text |
| `--bg-page` | `#F9FAFB` | Page background (off-white) |
| `--bg-card` | `#FFFFFF` | Card surfaces |
| `--border` | `#E5E7EB` | Card/section borders |

### Typography
- **Font:** Inter (system fallbacks: Helvetica Neue → Arial → sans-serif)
- **Base size:** 1rem, line-height 1.7
- **Hero title:** `clamp(2.8rem, 6vw, 4rem)` — scales with viewport
- **Section titles:** 2rem, weight 700

### Responsive Breakpoints
- `≤ 1024px` — tablet (grid collapses)
- `≤ 768px` — mobile (hamburger nav, single column)
- `≤ 480px` — small phones (tighter spacing)

## Page Sections (top → bottom)
1. **Nav** — sticky, glassmorphic blur, active link underline, hamburger on mobile
2. **Hero** — "Available for collaboration" badge, name/title/subtitle, two CTAs
3. **About** — "LC" monogram avatar + 4 chip tags + 2-paragraph bio
4. **Skills** — 4-column card grid: Data & Analysis · Web & Code · Operations · Soft Skills
5. **Projects** — 3-column card grid with links to real tools (see below)
6. **Contact** — centered card with email CTA, LinkedIn, GitHub
7. **Footer** — dark background, copyright
8. **Back-to-top** — fixed circular button (appears after 300px scroll)

## Project Cards & Paths
| Card | Relative path |
|---|---|
| KPI Performance Calculator | `../9- KPI Performance/index.html` |
| Screenwise Email Library | `../8- GSW Flow/V2/` |
| Onboarding Flow Mapper | `../7- Onboarding Mapping/screenwise-onboarding-side-by-side.html` |

## Live Links
- **Email:** leticiafcezar@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/leticiafcezar/
- **GitHub:** https://github.com/LetiCezar

## How to Extend

### Add a project card
Copy an existing `.project-card` block in the `#projects` section. Update: icon class, title, description, tag chips, and the `href` on the link button. Use a relative path (`../folder/file.html`) for local tools.

### Add a profile photo
Inside `.about-avatar`, replace the `<span>LC</span>` with:
```html
<img src="photo.jpg" alt="Leticia Cezar" style="width:100%;height:100%;object-fit:cover;border-radius:50%;">
```
Then remove the avatar's background-color and the `font-size`/`font-weight` rules from `.about-avatar`.

### Add a new section
1. Add a `<section id="new-section" class="section">` block in the HTML
2. Add a nav link `<a href="#new-section">Label</a>` in the `<nav>`
3. Follow the existing section pattern: `.container > .section-header > h2 + p`, then content

## Conventions
- **Keep everything in `index.html`** — do not split into separate CSS/JS files unless explicitly asked
- **No new CDNs** without asking first
- **Mobile-first** — test all layout changes at 375px and 1280px
- **AOS attributes** — add `data-aos="fade-up"` and `data-aos-delay="N"` to new cards for consistent entrance animation
- **Always read `index.html` before editing** — the file is the single source of truth

## Do Not Change Without Asking

- CDN versions (pinned in the table above)
- CSS custom property names in `:root`
- Relative paths in project card `href` attributes
- The single-file architecture (`index.html` only)
