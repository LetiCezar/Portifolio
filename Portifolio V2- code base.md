<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Leticia Cezar — Operations & Internal Tools</title>
<meta name="description" content="Leticia Cezar — operations and process improvement. I build internal tools, often with AI, that cut admin and make work easier for teams.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* ============================================================
   DESIGN TOKENS — edit colours & type here, they cascade everywhere
   ============================================================ */
:root {
  /* --- Palette: sunny cream canvas, bright coral accent, mint + sun pops --- */
  --ink:        #34281f;   /* warm soft-brown — headings & text (not pure black) */
  --ink-soft:   #5a4d42;   /* body text */
  --ink-mute:   #837467;   /* secondary text */
  --cream:      #ffffff;   /* clean white page canvas */
  --cream-deep: #ffe9d4;   /* peachy tinted panels */
  --paper:      #ffffff;   /* cards */

  --coral:      #ff6a45;   /* THE bold accent — bright & happy */
  --coral-deep: #ed4d28;   /* hover / pressed */
  --coral-tint: rgba(255, 106, 69, 0.12);
  --coral-line: rgba(255, 106, 69, 0.32);

  --teal:       #14b8a6;   /* fresh mint-teal — cheerful cool pop */
  --teal-deep:  #0e9787;   /* teal hover / gradients */
  --teal-tint:  rgba(20, 184, 166, 0.12);

  --sun:        #ffc24a;   /* sunny yellow — bright highlight */
  --sun-deep:   #f5a623;

  --border:     rgba(28, 23, 20, 0.12);
  --border-soft:rgba(28, 23, 20, 0.07);

  --shadow-sm:  0 1px 2px rgba(28, 23, 20, 0.05);
  --shadow-md:  0 14px 40px -12px rgba(28, 23, 20, 0.18);
  --shadow-lg:  0 40px 80px -24px rgba(28, 23, 20, 0.28);

  --display: 'Space Grotesk', 'Inter', system-ui, sans-serif;
  --sans:    'Inter', system-ui, 'Helvetica Neue', Arial, sans-serif;

  --maxw: 1140px;
}

* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; scroll-padding-top: 88px; }
body {
  font-family: var(--sans);
  font-size: 1rem;
  line-height: 1.6;
  color: var(--ink-soft);
  background: var(--cream);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
}
a { color: inherit; text-decoration: none; }
img { max-width: 100%; display: block; }
::selection { background: var(--coral); color: #fff; }

.wrap { width: 100%; max-width: var(--maxw); margin: 0 auto; padding: 0 1.5rem; }

/* ============================================================
   NAV
   ============================================================ */
.nav {
  position: sticky; top: 0; z-index: 50;
  background: rgba(247, 241, 232, 0.82);
  backdrop-filter: saturate(160%) blur(16px);
  -webkit-backdrop-filter: saturate(160%) blur(16px);
  border-bottom: 1px solid var(--border-soft);
}
.nav-in { display: flex; align-items: center; justify-content: space-between; height: 72px; }
.brand { display: flex; align-items: center; gap: 0.7rem; font-family: var(--display); font-weight: 700; color: var(--ink); letter-spacing: -0.02em; }
.brand-mark {
  width: 34px; height: 34px; border-radius: 10px;
  background: var(--ink); color: var(--coral);
  display: grid; place-items: center; font-size: 0.85rem; font-weight: 700;
}
.nav-links { display: flex; align-items: center; gap: 0.25rem; }
.nav-links a {
  font-size: 0.9rem; font-weight: 500; color: var(--ink-soft);
  padding: 0.5rem 0.85rem; border-radius: 8px; transition: color .15s, background .15s;
}
.nav-links a:hover, .nav-links a.active { color: var(--ink); background: var(--coral-tint); }
.nav-cta {
  font-family: var(--sans); font-weight: 600; font-size: 0.88rem;
  background: var(--ink); color: #fff !important; padding: 0.55rem 1.05rem !important;
  border-radius: 8px; transition: background .15s, transform .15s;
}
.nav-cta:hover { background: var(--coral); transform: translateY(-1px); }
.nav-toggle { display: none; background: transparent; border: 1px solid var(--border); width: 42px; height: 42px; border-radius: 10px; color: var(--ink); font-size: 1.05rem; cursor: pointer; }

/* ============================================================
   BUTTONS
   ============================================================ */
.btn {
  display: inline-flex; align-items: center; gap: 0.55rem;
  font-family: var(--sans); font-weight: 600; font-size: 0.95rem;
  padding: 0.95rem 1.6rem; border-radius: 11px; cursor: pointer;
  border: 1.5px solid transparent; transition: transform .16s, background .16s, color .16s, border-color .16s, box-shadow .16s;
}
.btn-primary { background: var(--coral); color: #fff; box-shadow: 0 10px 26px -10px var(--coral); }
.btn-primary:hover { background: var(--coral-deep); transform: translateY(-2px); }
.btn-dark { background: var(--teal); color: #fff; }
.btn-dark:hover { background: var(--teal-deep); transform: translateY(-2px); }
.btn-ghost { background: transparent; color: var(--ink); border-color: var(--border); }
.btn-ghost:hover { border-color: var(--ink); transform: translateY(-2px); }

/* ============================================================
   HERO — one dominant statement, one bold accent phrase
   ============================================================ */
.hero { padding: 5.5rem 0 5rem; position: relative; }
.hero-grid { display: grid; grid-template-columns: 1.45fr 1fr; gap: 3.5rem; align-items: center; }

.pill {
  display: inline-flex; align-items: center; gap: 0.55rem;
  padding: 0.42rem 0.9rem; border-radius: 999px;
  background: var(--paper); border: 1px solid var(--border);
  font-size: 0.8rem; font-weight: 600; color: var(--ink); margin-bottom: 1.6rem;
  box-shadow: var(--shadow-sm);
}
.pill .dot { width: 9px; height: 9px; border-radius: 50%; background: var(--teal); box-shadow: 0 0 0 0 rgba(15,110,99,.6); animation: pulse 2.2s infinite; }
@keyframes pulse { 0%{box-shadow:0 0 0 0 rgba(15,110,99,.5)} 70%{box-shadow:0 0 0 9px rgba(15,110,99,0)} 100%{box-shadow:0 0 0 0 rgba(15,110,99,0)} }

.hero h1 {
  font-family: var(--display); font-weight: 700;
  font-size: clamp(2.6rem, 5.4vw, 4.2rem); line-height: 1.02;
  letter-spacing: -0.035em; color: var(--ink); margin-bottom: 1.4rem; text-wrap: balance;
}
.hero h1 .mark { color: var(--coral); position: relative; white-space: nowrap; }
.hero h1 .mark::after {
  content: ""; position: absolute; left: -2px; right: -2px; bottom: 0.06em; height: 0.28em;
  background: var(--coral-tint); z-index: -1; border-radius: 3px;
}
.hero-sub { font-size: 1.18rem; color: var(--ink-soft); max-width: 540px; margin-bottom: 1.1rem; text-wrap: pretty; }
.hero-pos { font-size: 0.98rem; color: var(--ink-mute); max-width: 540px; margin-bottom: 2.2rem; }
.hero-pos b { color: var(--ink); font-weight: 600; }
.hero-ctas { display: flex; gap: 0.8rem; flex-wrap: wrap; margin-bottom: 2.4rem; }
.hero-meta { display: flex; gap: 1.4rem; flex-wrap: wrap; }
.hero-meta span { display: inline-flex; align-items: center; gap: 0.5rem; font-size: 0.86rem; color: var(--ink-mute); font-weight: 500; }
.hero-meta i { color: var(--coral); }

.hero-photo { position: relative; }
.hero-photo-frame {
  position: relative; border-radius: 24px; overflow: hidden;
  border: 1px solid var(--border); box-shadow: var(--shadow-lg);
  aspect-ratio: 4 / 5; background: var(--cream-deep);
}
.hero-photo-frame img { width: 100%; height: 100%; object-fit: cover; }
.hero-photo::before {
  content: ""; position: absolute; inset: auto -18px -18px auto; width: 62%; height: 62%;
  background: var(--coral); border-radius: 24px; z-index: -1;
}
.hero-badge-float {
  position: absolute; left: -16px; bottom: 24px; z-index: 2;
  background: var(--ink); color: #fff; border-radius: 14px; padding: 0.85rem 1.05rem;
  box-shadow: var(--shadow-md); max-width: 200px;
}
.hero-badge-float b { font-family: var(--display); display: block; font-size: 1.5rem; color: var(--coral); line-height: 1; }
.hero-badge-float span { font-size: 0.78rem; color: rgba(255,255,255,.75); }

/* ============================================================
   SECTION SHELL
   ============================================================ */
.section { padding: 5.5rem 0; }
.section-head { max-width: 680px; margin-bottom: 3rem; }
.eyebrow {
  display: inline-flex; align-items: center; gap: 0.5rem;
  font-family: var(--display); font-size: 0.8rem; font-weight: 600; letter-spacing: 0.06em;
  text-transform: uppercase; color: var(--coral); margin-bottom: 1rem;
}
.eyebrow::before { content: ""; width: 22px; height: 2px; background: var(--coral); display: inline-block; }
.section-head h2 {
  font-family: var(--display); font-weight: 700;
  font-size: clamp(2rem, 4vw, 2.9rem); line-height: 1.05; letter-spacing: -0.03em;
  color: var(--ink); margin-bottom: 1rem; text-wrap: balance;
}
.section-head p { font-size: 1.08rem; color: var(--ink-mute); text-wrap: pretty; }

/* ============================================================
   ABOUT
   ============================================================ */
.about { background: var(--cream-deep); }
.about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3.5rem; align-items: center; }
.about-bio p { font-size: 1.08rem; margin-bottom: 1.1rem; text-wrap: pretty; }
.about-bio p:last-of-type { margin-bottom: 0; }
.about-bio b { color: var(--ink); font-weight: 600; }
.about-lead { font-family: var(--display); font-size: clamp(1.4rem,2.4vw,1.8rem) !important; font-weight: 500; color: var(--ink) !important; line-height: 1.3; letter-spacing: -0.02em; }
.about-chips { display: flex; flex-wrap: wrap; gap: 0.55rem; margin-top: 1.8rem; }
.chip { display: inline-flex; align-items: center; gap: 0.5rem; padding: 0.45rem 0.95rem; border-radius: 999px; background: var(--paper); border: 1px solid var(--border); font-size: 0.84rem; font-weight: 500; color: var(--ink-soft); }
.chip i { color: var(--coral); }
.about-traits { display: grid; gap: 1rem; }
.trait { display: flex; gap: 1rem; padding: 1.3rem 1.4rem; background: var(--paper); border: 1px solid var(--border); border-radius: 16px; box-shadow: var(--shadow-sm); }
.trait-ic { flex: 0 0 auto; width: 44px; height: 44px; border-radius: 12px; background: var(--coral-tint); color: var(--coral-deep); display: grid; place-items: center; font-size: 1.1rem; }
.trait h4 { font-family: var(--display); font-size: 1.02rem; color: var(--ink); margin-bottom: 0.2rem; }
.trait p { font-size: 0.9rem; color: var(--ink-mute); }

/* ============================================================
   WORK — expandable case studies. KPI is the featured one.
   ============================================================ */
.cases { display: grid; gap: 1.5rem; }
.case {
  background: var(--paper); border: 1px solid var(--border); border-radius: 20px;
  overflow: hidden; transition: border-color .2s, box-shadow .2s, transform .2s;
}
.case[open], .case:hover { border-color: var(--coral-line); box-shadow: var(--shadow-md); }
.case > summary {
  list-style: none; cursor: pointer; display: grid; grid-template-columns: auto 1fr auto;
  gap: 1.4rem; align-items: center; padding: 1.6rem 1.8rem;
}
.case > summary::-webkit-details-marker { display: none; }
.case-num { font-family: var(--display); font-weight: 700; font-size: 1.05rem; color: var(--coral); width: 2.2rem; }
.case-head h3 { font-family: var(--display); font-size: 1.35rem; color: var(--ink); letter-spacing: -0.02em; margin-bottom: 0.25rem; }
.case-head p { font-size: 0.96rem; color: var(--ink-mute); }
.case-head .tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 0.7rem; }
.case-tag { font-size: 0.72rem; font-weight: 600; padding: 0.25rem 0.6rem; border-radius: 6px; background: var(--cream-deep); color: var(--ink-soft); }
.case-toggle {
  flex: 0 0 auto; display: inline-flex; align-items: center; gap: 0.5rem;
  font-weight: 600; font-size: 0.85rem; color: var(--ink);
  padding: 0.6rem 1rem; border: 1.5px solid var(--border); border-radius: 10px;
  white-space: nowrap; transition: background .15s, border-color .15s, color .15s;
}
.case:hover .case-toggle { border-color: var(--coral); color: var(--coral-deep); }
.case-toggle i { transition: transform .25s; }
.case[open] .case-toggle i { transform: rotate(180deg); }
.case[open] .case-toggle .lbl::after { content: " case study"; }
.case-toggle .lbl::after { content: " case study"; }

/* featured (KPI) — bigger, bright coral banner */
.case.featured { border-color: var(--coral-line); }
.case.featured > summary { background: linear-gradient(120deg, var(--coral) 0%, var(--sun-deep) 130%); grid-template-columns: auto 1fr auto; }
.case.featured .case-num { color: #fff; }
.case.featured .case-head h3 { color: #fff; font-size: 1.6rem; }
.case.featured .case-head p { color: rgba(255,255,255,.9); }
.case.featured .case-tag { background: rgba(255,255,255,.22); color: #fff; }
.case.featured .case-toggle { color: #fff; border-color: rgba(255,255,255,.55); }
.case.featured:hover .case-toggle { border-color: #fff; color: var(--coral-deep); background: #fff; }
.featured-flag { display: inline-flex; align-items: center; gap: 0.4rem; font-size: 0.72rem; font-weight: 700; letter-spacing: 0.05em; text-transform: uppercase; color: #fff; margin-bottom: 0.5rem; }

/* expanded body */
.case-body { padding: 0 1.8rem 1.9rem; border-top: 1px solid var(--border-soft); }
.case-body-in { display: grid; grid-template-columns: 1fr 1fr; gap: 2.2rem; padding-top: 1.7rem; align-items: start; }
.case-story { display: grid; gap: 1.3rem; }
.story-block h5 { font-family: var(--display); font-size: 0.82rem; letter-spacing: 0.05em; text-transform: uppercase; color: var(--coral-deep); margin-bottom: 0.4rem; }
.story-block p { font-size: 0.98rem; color: var(--ink-soft); }
.case-shot { border-radius: 14px; overflow: hidden; border: 1px solid var(--border); box-shadow: var(--shadow-sm); background: var(--cream-deep); }
.case-shot img { width: 100%; display: block; }
.case-actions { margin-top: 1.7rem; }
.case-actions .btn { font-size: 0.9rem; padding: 0.8rem 1.3rem; }

/* ============================================================
   CONTACT
   ============================================================ */
.contact { background: linear-gradient(135deg, var(--teal) 0%, var(--teal-deep) 100%); color: #fff; }
.contact .section-head { max-width: none; text-align: center; margin: 0 auto 2.5rem; }
.contact .eyebrow { color: #fff; justify-content: center; }
.contact .eyebrow::before { background: #fff; }
.contact .section-head h2 { color: #fff; }
.contact .section-head h2 .mark { color: var(--sun); }
.contact .section-head h2 .mark::after { background: rgba(255,255,255,.18); }
.contact .section-head p { color: rgba(255,255,255,.85); max-width: 560px; margin: 0 auto; }
.contact-actions { display: flex; gap: 0.9rem; justify-content: center; flex-wrap: wrap; margin-bottom: 2.2rem; }
.contact-socials { display: flex; gap: 0.7rem; justify-content: center; padding-top: 2rem; border-top: 1px solid rgba(255,255,255,.12); max-width: 560px; margin: 0 auto; }
.soc { width: 48px; height: 48px; border-radius: 12px; display: grid; place-items: center; border: 1px solid rgba(255,255,255,.18); color: rgba(255,255,255,.85); background: rgba(255,255,255,.04); transition: all .16s; }
.soc:hover { background: var(--coral); border-color: var(--coral); color: #fff; transform: translateY(-2px); }
.email-copy { position: relative; font-family: inherit; }
.email-copy .ic { transition: opacity .15s; }
.email-copy .ic--hover, .email-copy .ic--done { display: none; }
.email-copy:hover .ic--default { display: none; }
.email-copy:hover .ic--hover { display: inline-block; }
.email-copy.is-copied .ic--default, .email-copy.is-copied .ic--hover { display: none !important; }
.email-copy.is-copied .ic--done { display: inline-block; }

/* ============================================================
   FOOTER
   ============================================================ */
.footer { background: var(--cream-deep); color: var(--ink-mute); padding: 2rem 0; border-top: 1px solid var(--border-soft); font-size: 0.85rem; }
.footer-in { display: flex; justify-content: space-between; align-items: center; gap: 1rem; flex-wrap: wrap; }
.footer b { color: var(--ink); font-family: var(--display); }
.footer .live { color: var(--teal-deep); font-weight: 600; }

/* back to top */
.to-top { position: fixed; bottom: 1.6rem; right: 1.6rem; z-index: 60; width: 48px; height: 48px; border-radius: 14px; background: var(--coral); color: #fff; border: none; cursor: pointer; box-shadow: 0 12px 28px -8px var(--coral); display: grid; place-items: center; font-size: 0.95rem; opacity: 0; transform: translateY(10px); pointer-events: none; transition: opacity .2s, transform .2s; }
.to-top.show { opacity: 1; transform: translateY(0); pointer-events: auto; }
.to-top:hover { background: var(--coral-deep); }

/* reveal on scroll */
.reveal { opacity: 0; transform: translateY(22px); transition: opacity .6s ease, transform .6s ease; }
.reveal.in { opacity: 1; transform: none; }

/* ============================================================
   RESPONSIVE
   ============================================================ */
@media (max-width: 900px) {
  .hero-grid { grid-template-columns: 1fr; gap: 2.5rem; }
  .hero-photo { max-width: 360px; }
  .about-grid { grid-template-columns: 1fr; gap: 2.5rem; }
  .case-body-in { grid-template-columns: 1fr; gap: 1.5rem; }
  .case-shot { order: -1; }
}
@media (max-width: 680px) {
  .nav-links { position: absolute; top: 72px; left: 0; right: 0; flex-direction: column; align-items: stretch; gap: 0; background: var(--cream); border-bottom: 1px solid var(--border); padding: 0.5rem 1.5rem 1rem; transform: translateY(-10px); opacity: 0; pointer-events: none; transition: opacity .18s, transform .18s; }
  .nav-links.open { transform: none; opacity: 1; pointer-events: auto; }
  .nav-links a { padding: 0.9rem 0; border-bottom: 1px solid var(--border-soft); }
  .nav-links .nav-cta { margin-top: 0.6rem; text-align: center; }
  .nav-toggle { display: grid; place-items: center; }
  .hero { padding: 3.5rem 0; }
  .section { padding: 4rem 0; }
  .case > summary { grid-template-columns: auto 1fr; gap: 0.9rem 1rem; padding: 1.3rem 1.3rem; }
  .case-toggle { grid-column: 2; justify-self: start; }
  .case.featured .case-head h3 { font-size: 1.3rem; }
  .case-toggle .lbl::after, .case[open] .case-toggle .lbl::after { content: "" !important; }
  .case-body { padding: 0 1.3rem 1.5rem; }
}
@media (max-width: 420px) {
  .wrap { padding: 0 1.1rem; }
  .hero-meta { gap: 0.9rem; }
  .hero-badge-float { left: 8px; }
}
</style>
</head>
<body id="top">

<!-- ========== NAV ========== -->
<nav class="nav">
  <div class="wrap nav-in">
    <a href="#top" class="brand"><span class="brand-mark">LC</span> Leticia Cezar</a>
    <div class="nav-links" id="navLinks">
      <a href="#about">About</a>
      <a href="#work">Work</a>
      <a href="#contact" class="nav-cta">Get in touch</a>
    </div>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle menu"><i class="fa-solid fa-bars"></i></button>
  </div>
</nav>

<!-- ========== HERO ========== -->
<header class="hero">
  <div class="wrap hero-grid">
    <div class="hero-copy">
      <span class="pill"><span class="dot"></span> Available for full-time roles</span>
      <h1>I build internal tools that make work <span class="mark">easier</span>.</h1>
      <p class="hero-sub">Operations &amp; process improvement — I spot the friction, figure out what's missing, and build something that removes it.</p>
      <p class="hero-pos"><b>Operations + process improvement, often using AI to build internal tools</b> that cut admin and give teams clarity.</p>
      <div class="hero-ctas">
        <a href="#contact" class="btn btn-primary"><i class="fa-solid fa-envelope"></i> Email me</a>
        <a href="#work" class="btn btn-ghost">See the work <i class="fa-solid fa-arrow-down"></i></a>
      </div>
      <div class="hero-meta">
        <span><i class="fa-solid fa-location-dot"></i> London · Remote / Hybrid</span>
        <span><i class="fa-solid fa-language"></i> English · Portuguese</span>
      </div>
    </div>
    <div class="hero-photo">
      <div class="hero-photo-frame"><img src="assets/profile.jpeg" alt="Leticia Cezar"></div>
      <div class="hero-badge-float"><b>Self-taught</b><span>builder &amp; lifelong learner</span></div>
    </div>
  </div>
</header>

<main>

<!-- ========== ABOUT ========== -->
<section id="about" class="section about">
  <div class="wrap">
    <div class="about-grid">
      <div class="about-bio reveal">
        <span class="eyebrow">About</span>
        <p class="about-lead">I'm Leticia — I make work better for the people doing it, and for the company they do it for.</p>
        <p>My work sits in the operational layer that keeps research, support, and delivery connected. I'm <b>self-taught</b>, I love to learn, and I'm happiest when I've turned a messy manual process into something that just works.</p>
        <p>That looks like mapping how work actually happens, spotting the gaps, and building the tool that closes them — internal apps, process maps, infographics, and AI-powered workflows that fit the way a team really works.</p>
        <div class="about-chips">
          <span class="chip"><i class="fa-solid fa-chart-line"></i> Data &amp; Analysis</span>
          <span class="chip"><i class="fa-solid fa-screwdriver-wrench"></i> Internal Tools</span>
          <span class="chip"><i class="fa-solid fa-wand-magic-sparkles"></i> AI Workflows</span>
          <span class="chip"><i class="fa-solid fa-people-arrows"></i> Cross-team Ops</span>
        </div>
      </div>
      <div class="about-traits reveal">
        <div class="trait"><div class="trait-ic"><i class="fa-solid fa-lightbulb"></i></div><div><h4>Knowledgeable</h4><p>I design the metrics and the logic, not just the interface.</p></div></div>
        <div class="trait"><div class="trait-ic"><i class="fa-solid fa-circle-check"></i></div><div><h4>Competent</h4><p>I ship real, working tools that teams use day to day.</p></div></div>
        <div class="trait"><div class="trait-ic"><i class="fa-solid fa-compass"></i></div><div><h4>Resourceful</h4><p>I taught myself to build, so a missing tool is never a dead end.</p></div></div>
      </div>
    </div>
  </div>
</section>

<!-- ========== WORK ========== -->
<section id="work" class="section">
  <div class="wrap">
    <div class="section-head reveal">
      <span class="eyebrow">Selected work</span>
      <h2>Tools I've built &amp; shipped.</h2>
      <p>Internal products built to solve real, day-to-day operational problems. Open any one to see the thinking — the friction, what I built, and what changed.</p>
    </div>

    <div class="cases">

      <!-- FEATURED: KPI Calculator -->
      <details class="case featured reveal" open>
        <summary>
          <span class="case-num">01</span>
          <div class="case-head">
            <span class="featured-flag"><i class="fa-solid fa-star"></i> Featured</span>
            <h3>KPI Performance Calculator</h3>
            <p>End-to-end: I designed the metrics &amp; logic, then built the tool.</p>
            <div class="tags"><span class="case-tag">Metrics design</span><span class="case-tag">JavaScript</span><span class="case-tag">Internal tool</span></div>
          </div>
          <span class="case-toggle"><span class="lbl">Read</span> <i class="fa-solid fa-chevron-down"></i></span>
        </summary>
        <div class="case-body">
          <div class="case-body-in">
            <div class="case-story">
              <div class="story-block"><h5>The friction</h5><p>Team leaders were spending real time pulling weekly numbers by hand, and employees only heard how they were performing in occasional reviews — never day to day. Feedback was slow, manual, and easy to misread.</p></div>
              <div class="story-block"><h5>What I built</h5><p>I developed the performance metrics and the calculation logic from scratch, then built an HTML internal tool around them. It turns weekly panel metrics into a single, clear performance score against target — no spreadsheet wrangling.</p></div>
              <div class="story-block"><h5>What changed</h5><p>Leaders lost the manual admin, and employees got daily, easy-to-understand feedback they could act on themselves. The thinking and the build were both mine — the metric design is what makes the score actually mean something.</p></div>
              <div class="case-actions"><a class="btn btn-dark" href="../9- KPI Performance/index.html" target="_blank" rel="noopener">Open the tool <i class="fa-solid fa-arrow-up-right-from-square"></i></a></div>
            </div>
            <div class="case-shot"><img src="assets/performance-calc-allocations.png" alt="KPI Performance Calculator — allocation groups with metric targets"></div>
          </div>
        </div>
      </details>

      <!-- Line Test Checklist -->
      <details class="case reveal">
        <summary>
          <span class="case-num">02</span>
          <div class="case-head">
            <h3>Interactive Line Test Checklist</h3>
            <p>A guided, auto-saving form that makes every handover consistent.</p>
            <div class="tags"><span class="case-tag">Internal tool</span><span class="case-tag">UX</span><span class="case-tag">Ops</span></div>
          </div>
          <span class="case-toggle"><span class="lbl">Read</span> <i class="fa-solid fa-chevron-down"></i></span>
        </summary>
        <div class="case-body">
          <div class="case-body-in">
            <div class="case-story">
              <div class="story-block"><h5>The friction</h5><p>The 5-stage line test for PSE Support lived in people's heads and free-text notes, so handovers were inconsistent and steps got missed.</p></div>
              <div class="story-block"><h5>What I built</h5><p>A guided, auto-saving checklist that walks through each stage and turns the result into a clean, copy-ready note.</p></div>
              <div class="story-block"><h5>What changed</h5><p>Every handover now follows the same structure and produces the same shape of note — less missed, less re-explaining.</p></div>
              <div class="case-actions"><a class="btn btn-dark" href="../13- Line Test Support/index.html" target="_blank" rel="noopener">Open the tool <i class="fa-solid fa-arrow-up-right-from-square"></i></a></div>
            </div>
            <div class="case-shot"><img src="assets/line-test-checklist.png" alt="Line Test Checklist tool — Screenwise PSE Support"></div>
          </div>
        </div>
      </details>

      <!-- Onboarding Map -->
      <details class="case reveal">
        <summary>
          <span class="case-num">03</span>
          <div class="case-head">
            <h3>Onboarding Process Map</h3>
            <p>A side-by-side view of the participant journey, used to find drop-off.</p>
            <div class="tags"><span class="case-tag">Process mapping</span><span class="case-tag">Onboarding</span><span class="case-tag">Cross-functional</span></div>
          </div>
          <span class="case-toggle"><span class="lbl">Read</span> <i class="fa-solid fa-chevron-down"></i></span>
        </summary>
        <div class="case-body">
          <div class="case-body-in">
            <div class="case-story">
              <div class="story-block"><h5>The friction</h5><p>No one had a shared picture of the full participant onboarding journey, so it was hard to agree where people were dropping off.</p></div>
              <div class="story-block"><h5>What I built</h5><p>A side-by-side visual map of the journey from survey submission through compliance, laid out so each stage is comparable at a glance.</p></div>
              <div class="story-block"><h5>What changed</h5><p>Ops, Engineering, and Research could finally point at the same map — making drop-off points and ownership obvious.</p></div>
              <div class="case-actions"><a class="btn btn-dark" href="../7-onboarding-mapping/screenwise-onboarding-side-by-side.html" target="_blank" rel="noopener">Open the map <i class="fa-solid fa-arrow-up-right-from-square"></i></a></div>
            </div>
            <div class="case-shot"><img src="assets/onboarding-map.png" alt="Onboarding flow map — participant journey from survey submission through compliance"></div>
          </div>
        </div>
      </details>

      <!-- Infographics -->
      <details class="case reveal">
        <summary>
          <span class="case-num">04</span>
          <div class="case-head">
            <h3>Explainer Infographics</h3>
            <p>Turning rewards, processes &amp; policy into clear, shareable visuals.</p>
            <div class="tags"><span class="case-tag">Data viz</span><span class="case-tag">Comms</span><span class="case-tag">Design</span></div>
          </div>
          <span class="case-toggle"><span class="lbl">Read</span> <i class="fa-solid fa-chevron-down"></i></span>
        </summary>
        <div class="case-body">
          <div class="case-body-in">
            <div class="case-story">
              <div class="story-block"><h5>The friction</h5><p>Panel rewards and policies were written as dense text, so participants and stakeholders often misread how points and bonuses worked.</p></div>
              <div class="story-block"><h5>What I built</h5><p>Visual explainers — like the Screenwise Points Guide — that translate the rules into clear, shareable graphics.</p></div>
              <div class="story-block"><h5>What changed</h5><p>One image now does the job a paragraph couldn't, cutting the back-and-forth and making the rules easy to share.</p></div>
            </div>
            <div class="case-shot"><img src="assets/screenwise-points-guide.png" alt="Screenwise Points Guide infographic — monthly points and bonus rewards"></div>
          </div>
        </div>
      </details>

    </div>
  </div>
</section>

<!-- ========== CONTACT ========== -->
<section id="contact" class="section contact">
  <div class="wrap">
    <div class="section-head reveal">
      <span class="eyebrow">Contact</span>
      <h2>Let's make something work <span class="mark">better</span>.</h2>
      <p>Looking for a full-time role where operations, tooling, and delivery actually matter. The fastest way to reach me is email — I reply the same day.</p>
    </div>
    <div class="contact-actions reveal">
      <button type="button" class="btn btn-primary email-copy" id="emailCopy" data-email="leticiafcezar@gmail.com" aria-label="Copy email address">
        <i class="fa-solid fa-envelope ic ic--default"></i>
        <i class="fa-solid fa-copy ic ic--hover"></i>
        <i class="fa-solid fa-check ic ic--done"></i>
        <span class="email-copy-label">leticiafcezar@gmail.com</span>
      </button>
      <a href="https://www.linkedin.com/in/leticiafcezar/" class="btn btn-ghost" style="color:#fff;border-color:rgba(255,255,255,.28)" target="_blank" rel="noopener"><i class="fa-brands fa-linkedin-in"></i> LinkedIn</a>
    </div>
    <div class="contact-socials reveal">
      <a class="soc" href="mailto:leticiafcezar@gmail.com" aria-label="Email"><i class="fa-solid fa-envelope"></i></a>
      <a class="soc" href="https://www.linkedin.com/in/leticiafcezar/" target="_blank" rel="noopener" aria-label="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
    </div>
  </div>
</section>

</main>

<footer class="footer">
  <div class="wrap footer-in">
    <div><b>Leticia Cezar</b> — Operations &amp; Internal Tools</div>
    <div><span class="live">● available</span> &nbsp;·&nbsp; v2026.06</div>
  </div>
</footer>

<button class="to-top" id="toTop" aria-label="Back to top"><i class="fa-solid fa-arrow-up"></i></button>

<script>
  // Mobile nav
  const navToggle = document.getElementById('navToggle');
  const navLinks = document.getElementById('navLinks');
  navToggle.addEventListener('click', () => {
    const open = navLinks.classList.toggle('open');
    navToggle.innerHTML = open ? '<i class="fa-solid fa-xmark"></i>' : '<i class="fa-solid fa-bars"></i>';
  });
  navLinks.addEventListener('click', e => {
    if (e.target.tagName === 'A') { navLinks.classList.remove('open'); navToggle.innerHTML = '<i class="fa-solid fa-bars"></i>'; }
  });

  // Active nav link + back-to-top
  const ids = ['about','work','contact'];
  const links = Array.from(navLinks.querySelectorAll('a'));
  const secs = ids.map(i => document.getElementById(i)).filter(Boolean);
  const toTop = document.getElementById('toTop');
  const onScroll = () => {
    const y = window.scrollY + 130; let cur = '';
    secs.forEach(s => { if (s.offsetTop <= y) cur = s.id; });
    links.forEach(a => a.classList.toggle('active', a.getAttribute('href') === '#' + cur));
    toTop.classList.toggle('show', window.scrollY > 320);
  };
  window.addEventListener('scroll', onScroll, { passive: true });
  onScroll();
  toTop.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

  // Reveal on scroll
  const io = new IntersectionObserver(es => es.forEach(en => { if (en.isIntersecting) { en.target.classList.add('in'); io.unobserve(en.target); } }), { threshold: 0.12 });
  document.querySelectorAll('.reveal').forEach(el => io.observe(el));

  // Email copy (execCommand first, clipboard fallback — reliable in sandboxes)
  const emailBtn = document.getElementById('emailCopy');
  if (emailBtn) {
    const labelEl = emailBtn.querySelector('.email-copy-label');
    const original = labelEl ? labelEl.textContent : '';
    let timer = null;
    const copyText = text => {
      const tmp = document.createElement('textarea');
      tmp.value = text; tmp.setAttribute('readonly','');
      tmp.style.cssText = 'position:fixed;top:0;left:0;width:1px;height:1px;opacity:0;border:0;padding:0;';
      document.body.appendChild(tmp);
      const sel = document.getSelection();
      const prev = sel && sel.rangeCount ? sel.getRangeAt(0) : null;
      tmp.focus({ preventScroll: true }); tmp.select(); tmp.setSelectionRange(0, text.length);
      let ok = false; try { ok = document.execCommand('copy'); } catch (_) {}
      document.body.removeChild(tmp);
      if (prev) { sel.removeAllRanges(); sel.addRange(prev); }
      if (ok) return Promise.resolve();
      if (navigator.clipboard && navigator.clipboard.writeText) return navigator.clipboard.writeText(text);
      return Promise.reject();
    };
    const flash = txt => {
      emailBtn.classList.add('is-copied');
      if (labelEl) labelEl.textContent = txt;
      clearTimeout(timer);
      timer = setTimeout(() => { emailBtn.classList.remove('is-copied'); if (labelEl) labelEl.textContent = original; }, 1600);
    };
    emailBtn.addEventListener('click', e => {
      e.preventDefault();
      copyText(emailBtn.dataset.email || '').then(() => flash('Copied!')).catch(() => flash('Press Ctrl+C'));
    });
  }
</script>
</body>
</html>