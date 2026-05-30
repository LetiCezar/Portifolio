# Portfolio Sprint Plan — 2 Weekends to Public

**Owner:** Leticia Cezar
**Start:** Weekend of 30–31 May 2026 (adjust if needed)
**Goal:** Public portfolio live on GitHub Pages, positioned for Ops Analyst + Lean Six Sigma / Process Improvement roles.
**Time budget:** ~8 hours per weekend = 16 hours total.
**Source of audit:** `AUDIT-2026-05.md`

---

## Philosophy

Two weekends, two themes:

- **Weekend 1 — Substance.** Add the evidence layer (metrics, LSS framing, case studies). This is the work that actually changes recruiter response rate.
- **Weekend 2 — Ship.** Polish, accessibility, hosting. The week between is for letting the writing breathe and editing it with fresh eyes.

If anything slips, sacrifice polish — never sacrifice the substance work in Weekend 1.

---

## Pre-flight (≤ 30 mins, do before Weekend 1)

A short setup pass so the weekends are uninterrupted creative time.

- [ ] **Decide one sentence: "I'm looking for a role in ___ at ___-stage companies in London."** Write it on a sticky note. Every word on the site should serve this.
- [ ] **Pull metrics for each project.** Even rough ones. Open the KPI Calculator, Email Library, Onboarding Mapper and write down: time saved, errors reduced, frequency of use, people impacted. If you don't know, estimate a range ("~20–30 mins/week").
- [ ] **Take 3 screenshots.** Full-page screenshots of each live tool at desktop width (1280px). Save as `assets/preview-kpi.png`, `assets/preview-email.png`, `assets/preview-onboarding.png`. Create the `assets/` folder if it doesn't exist (it doesn't — see audit issue #1).
- [ ] **Find your `profile.jpeg`** and put it in the new `assets/` folder. The site references it but the folder doesn't exist yet.
- [ ] **Create a 1-page CV PDF** (or use an existing one). Save as `assets/Leticia-Cezar-CV.pdf`.

---

## Weekend 1 — Substance (Saturday + Sunday, ~8h)

### Block A — Saturday morning (2h): Hero + positioning

**Outcome:** The first 5 seconds tell a recruiter exactly who you are and what you're looking for.

- [ ] Rewrite hero copy to add **one credential line** under the role line. Example:
  *"Panel Service Executive · Screenwise · London"*
  *"Lean Six Sigma Green Belt (in progress) · BA Hons HR & Psychology"*
- [ ] Add an **"Available for" line** under the badge:
  *"Open to Operations Analyst / Process Improvement roles · London / hybrid"*
- [ ] Remove inline styles from the hero (`style="margin: 0px 110px"` etc.) — they break on tablets. Let the existing `.container` do the work.
- [ ] Add a **stats strip** below the hero CTAs:
  *3 internal tools shipped · ~X hours/month saved · 4 cross-functional projects led*
  Use approximate numbers. They tell the eye "this person measures."

### Block B — Saturday afternoon (3h): Case studies

**Outcome:** Each project has a 150-word writeup that frames problem → approach → result.

For each of the 3 projects, write:

```
PROBLEM (1–2 sentences)
What was broken or slow? Who felt it? How often?

APPROACH (2–3 sentences)
What did you do? What method or framework? (Mention DMAIC, process mapping,
root cause, etc. where it applies.)

RESULT (1–2 sentences, with numbers)
What changed? Quantify if possible — even approximate is fine.

WHAT I LEARNED (1 sentence — optional but powerful)
```

- [ ] **KPI Calculator** — frame as "Measure" / data tooling story.
- [ ] **Email Library** — frame as "Improve / Control" story (standard work, reducing variation).
- [ ] **Onboarding Mapper** — frame as "Analyse" / process mapping story.

Add these as expandable sections inside each project card, OR as a separate `case-studies.html` page. **Recommended:** inline expandable — keeps the single-file architecture.

### Block C — Sunday morning (2h): Skills + About

**Outcome:** Skill cards use the methodology vocabulary recruiters search for. About section names what you want next.

- [ ] **Rewrite Operations skill card** to include: *DMAIC · Process mapping (SIPOC, swimlanes) · Root cause analysis · SOPs & control plans · RACI · Stakeholder management*
- [ ] **Rename "How I Work"** to **"Working approach"** and lead with: *Continuous improvement mindset · Data-driven decisions · Bilingual (EN/PT) · Cross-functional collaboration*
- [ ] **Add a line to About** stating what you're looking for: *"Currently exploring full-time roles in Operations and Process Improvement — ideally somewhere I can keep building tools while learning the discipline more formally."*
- [ ] Add a **"Currently learning"** chip row with: *Lean Six Sigma Green Belt · SQL · UX research methods*

### Block D — Sunday afternoon (1h): CV link + LSS surfacing

- [ ] Add **CV download button** in the Contact card next to Email / LinkedIn. Link to `assets/Leticia-Cezar-CV.pdf`.
- [ ] Add an **LSS badge** to the hero meta strip next to location/timezone. Use Font Awesome `fa-certificate` icon.
- [ ] Update `PORTFOLIO_PLAN.md` to mark which of its "Next Steps" are now done.

**End of Weekend 1 checkpoint:**
- Hero states what you want and what you have.
- Three projects each have a problem/approach/result writeup with at least one number.
- Skills use LSS vocabulary.
- CV is downloadable.

If you only have time for one weekend — *this is the one that matters.*

---

## Mid-week pause (10 mins/day Mon–Fri)

- [ ] Re-read each case study once. Cut filler. Tighten verbs.
- [ ] Show the site to one person you trust. Ask: *"What kind of role do you think I'm looking for?"* Their answer should match your one-sentence positioning.
- [ ] If they say "tech / web developer" — your tooling skills are overpowering your ops framing. Adjust.

---

## Weekend 2 — Ship (Saturday + Sunday, ~8h)

### Block E — Saturday morning (2h): Technical hygiene

**Outcome:** Site is robust, accessible, and presentable.

- [ ] **Fix the `assets/profile.jpeg` issue** (verify file is in place from pre-flight).
- [ ] **Remove all `style="..."` inline overrides.** Move what you need into the existing CSS. Lines 797, 798, 816, 818, 820, 824, 833, 845, 897, 976, 978, 980 are the worst offenders.
- [ ] **Fix `getElementById('year')` orphan** — either add `<span id="year"></span>` in the footer next to the copyright, or remove the JS.
- [ ] **Remove `white-space: nowrap`** on About + Contact subtitles (lines 820, 980). Forces horizontal scroll on mobile.
- [ ] **Update `CLAUDE.md`** colour table to match actual palette (teal, not sage). Current CLAUDE.md will confuse you in 6 months.
- [ ] **Add favicon.** Either a `LC` monogram SVG or a generated one. Save as `assets/favicon.svg`, reference in `<head>`.

### Block F — Saturday afternoon (2h): SEO + share previews

**Outcome:** When you share the URL on LinkedIn, Slack, or email, it looks intentional.

- [ ] Add `<meta name="description">` to `<head>`:
  *"Leticia Cezar — Operations & process improvement in London. Building internal tools at Screenwise. Lean Six Sigma Green Belt in progress."*
- [ ] Add Open Graph tags (`og:title`, `og:description`, `og:image`, `og:url`).
- [ ] Create a simple **OG share image** (1200×630px). Can be a screenshot of your hero, your name + role on a coloured card, or a Canva 5-min job. Save as `assets/og-image.png`.
- [ ] Add `<link rel="canonical">` pointing to your GitHub Pages URL.
- [ ] Test the share preview using the LinkedIn Post Inspector or Twitter Card Validator after publishing.

### Block G — Sunday morning (2h): Accessibility pass

**Outcome:** Site passes basic WCAG 2.1 AA expectations.

- [ ] Add **skip-link** at top of `<body>`: `<a class="skip-link" href="#main">Skip to content</a>` with CSS to show on focus.
- [ ] Add `aria-hidden="true"` to all decorative Font Awesome icons inside buttons/links.
- [ ] Add `aria-label` to icon-only buttons (back-to-top already has one — good).
- [ ] Wrap AOS animations in `@media (prefers-reduced-motion: reduce)` query that disables them.
- [ ] Run a Lighthouse audit in Chrome DevTools. Target: Accessibility ≥ 95.
- [ ] Verify keyboard nav: Tab through the page. Every link/button should be reachable and visibly focused.

### Block H — Sunday afternoon (2h): Publish

**Outcome:** Site is live, URL is shareable, version-controlled.

- [ ] Follow `PUBLISHING.md` (the GitHub Pages step-by-step). End with a live URL like `https://leticezar.github.io/portfolio/`.
- [ ] Add the URL to your LinkedIn (Featured section + Contact info field).
- [ ] Add the URL to the top of your CV.
- [ ] Share with 2–3 people (mentor, ex-colleague, friend in ops) and ask: *"If you saw this attached to a job application, what role would you assume I want?"* — the answer is your final sanity check.
- [ ] Create a `READ-ME-FIRST.md` for yourself with the URL, the GitHub repo, and 3 things you might change next.

---

## Stretch / out-of-scope (do later, not this sprint)

These are good ideas from the existing `PORTFOLIO_PLAN.md` — explicitly **not** in this sprint to protect the timeline:

- Comms Mapping web tool (needs a separate build sprint first).
- Line Test Support card (waiting on tool finish).
- Replacing email with a Tally form.
- Adding a blog or `/writing` section.
- Custom domain.
- Analytics (Plausible / Cloudflare) — only worth adding once you have steady traffic.

Park these. Ship first.

---

## Definition of done

- [ ] Site loads from a public `https://...` URL.
- [ ] All 3 project cards have a problem/approach/result writeup with at least one number each.
- [ ] LSS Green Belt is visible in the hero area.
- [ ] CV is downloadable from the Contact section.
- [ ] No broken images, no console errors, no horizontal scroll on mobile.
- [ ] Lighthouse: Performance ≥ 90, Accessibility ≥ 95, SEO ≥ 95.
- [ ] LinkedIn share preview shows your OG image, not a blank card.

When all eight tick, you ship — and you start applying.

---

*This plan is intentionally tight. Reality usually means one of two things: (a) Weekend 1 takes longer than expected, in which case do Weekend 2 the following weekend, or (b) you finish faster and use the spare time on stretch goals. Either is fine.*
