# Portfolio Project Selection & Display Plan

## Context

Leticia's portfolio is aimed at **job hunting** — potential employers who don't know Screenwise. The goal is to show two core skill sets: **operational & process design** and **data & tooling**. Currently 3 projects are shown; the display style is minimal (icon + description + tags). The plan is to select the right projects and improve how each one is presented to tell a story, not just list tools.

---

## Framework: How to Select Projects

For a job-hunting portfolio, each project should earn its spot by answering:
1. **What problem did it solve?** (Employers care about impact, not features)
2. **Does it show a skill they'd hire for?** (Ops design or data/tooling — per your focus)
3. **Is it polished enough to show?** (Broken or incomplete tools do more harm than good)
4. **Does it add something new?** (Avoid showing the same skill twice)

---

## Recommended Projects (4 total)

### Keep (already on portfolio)

| # | Project | Why Keep |
|---|---|---|
| 9 | **KPI Performance Calculator** | Best data/tooling example — complex logic, local storage, real operational use |
| 7 | **Onboarding Flow Mapper** | Strong ops/process example — visual mapping, gap analysis, cross-channel thinking |

### Add

| # | Project | Why Add | Condition |
|---|---|---|---|
| 11 | **Comms Mapping** | Strongest ops/systematization story — shows SOPs, repeatable processes, strategic thinking | Needs a web tool built first — currently only markdown docs exist |
| 13 | **Line Test Support** | Real operational impact — reduces PSE time, improves accuracy, everyday tool | In progress; add to portfolio once design + mobile view improvements are done |

### Remove or Deprioritize

| # | Project | Why |
|---|---|---|
| 8 | **Screenwise Email Library** | Comms design skill — not your stated focus. Kept as card 3 but de-emphasised |
| 2 | **Green Belt Project** | Not a single presentable tool — would need a different format (e.g. case study PDF). Skip for now unless you want to add a "Case Studies" section later |

---

## Display Recommendation: Screenshot + Problem/Solution Card

For job hunting, **screenshot + a two-part description** is the strongest format because:
- Employers skim — a screenshot gives instant context without clicking
- The description should frame *the problem* first, then *what you built* — this shows business thinking, not just technical skills

### Card structure (per project):

```
[Screenshot or visual preview]
[Icon]  Project Title
[Problem badge: e.g. "The challenge: tracking 50+ panel members manually"]
Short description: what you built and why it matters
[Tag chips: skills used]
[View Project →]
```

### Screenshots: How to get them
- Open each project in browser, take a full-page screenshot (browser DevTools → Capture full size, or use macOS Cmd+Shift+4)
- Crop to show the most visually interesting part (a filled-in tool, not an empty state)
- Resize to consistent dimensions: **800×500px** works well for cards
- Save as `preview-[project-name].jpg` in the portfolio folder

---

## Current Status (as of May 2026)

| Card | Status | Notes |
|---|---|---|
| KPI Performance Calculator | ✅ Live | Description updated to problem-first |
| Onboarding Flow Mapper | ✅ Live | Description updated; Process Design tag added |
| Compliance Email Library | ✅ Live | Description updated to problem-first |
| Line Test Support | 🔄 Coming Soon | Card added with badge; activate link when tool is ready |
| Comms Mapping | ⏳ Not yet | No web tool exists yet — build tool first |

---

## Next Steps

1. **Screenshots** — Take screenshots of the 3 live tools and swap the gradient header backgrounds for real previews
2. **Line Test Support** — Finish design + mobile improvements, then update the card link
3. **Comms Mapping** — Build a web tool, then add as a 5th card (or replace Email Library)
4. **Deploy** — Publish to Vercel once all cards are finalised
5. **Contact form** — Replace email link with a Tally embed (Mi's suggestion)

---

## Critical Files

- `index.html` — all changes go here (single-file architecture)
- `../11- Comms Mapping/` — needs a web tool before portfolio integration
- `../13- Line Test Support/` — in progress; portfolio-ready once design + mobile are done
