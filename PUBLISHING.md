# Publishing to GitHub Pages — Step by Step

**Goal:** Take `index.html` from local folder → live at `https://<your-username>.github.io/portfolio/`.
**Time:** ~30–45 minutes the first time. ~2 minutes for every update after that.
**Cost:** Free.
**Prerequisite:** A GitHub account. Your handle is `LetiCezar` (from the CLAUDE.md).

---

## Decision before you start: which URL pattern?

GitHub gives you two options. Pick one **before** creating the repo.

### Option A — Project URL (recommended for this sprint)
- Repo name: `portfolio`
- Live URL: `https://leticezar.github.io/portfolio/`
- Pro: Keeps your username available for other things.
- Con: Slightly longer URL.

### Option B — User URL
- Repo name: `leticezar.github.io` (must match handle exactly)
- Live URL: `https://leticezar.github.io/`
- Pro: Shortest possible URL.
- Con: You only get one. If you start another site later, you can't.

**For this sprint, use Option A.** You can always migrate to Option B later.

---

## Step 1 — Create the repo (5 mins)

1. Go to <https://github.com/new>.
2. **Repository name:** `portfolio`
3. **Description:** "Personal portfolio — operations & process improvement, London."
4. **Public** (must be public for free GitHub Pages).
5. **Do not** add a README, .gitignore, or licence yet (you'll do this from your folder).
6. Click **Create repository**.

GitHub will show you a "quick setup" page with commands. Keep that tab open.

---

## Step 2 — Get your folder under version control (10 mins)

Open Terminal on your Mac. Navigate to your portfolio folder:

```bash
cd "/Users/leticiacezar/Documents/leti-projects/12- Web Portfolio"
```

Initialise git and commit everything:

```bash
git init
git branch -M main
git add .
git commit -m "Initial portfolio commit"
```

Connect to your new GitHub repo (copy the exact URL from GitHub's quick-setup page — it will look like the one below):

```bash
git remote add origin https://github.com/LetiCezar/portfolio.git
git push -u origin main
```

If GitHub asks for authentication, use a **Personal Access Token** (not your password). Generate one at <https://github.com/settings/tokens?type=beta> with `repo` scope.

> **Heads up:** Your folder name has a space ("12- Web Portfolio"). That's fine locally — git handles it — but if you ever want to point this folder to a *different* repo name, the folder name doesn't have to match.

---

## Step 3 — Turn on GitHub Pages (3 mins)

1. On GitHub, go to your repo → **Settings** (top-right of the repo).
2. Left sidebar → **Pages**.
3. Under **Build and deployment**:
   - **Source:** Deploy from a branch
   - **Branch:** `main` · `/ (root)`
   - Click **Save**.
4. Wait 1–2 minutes. The page will refresh and show a green box with your URL.

Your site is now live at: **`https://leticezar.github.io/portfolio/`**

---

## Step 4 — Verify it works (5 mins)

Open the URL in a private/incognito window (so you're not relying on cached files).

Check:
- [ ] Hero loads, profile photo loads (if you've put `profile.jpeg` in `assets/`).
- [ ] Nav links scroll to sections.
- [ ] Project card links open the linked tools.

> **Important note about relative paths:** Your current `index.html` links to `../9- KPI Performance/index.html` etc. These will **break on GitHub Pages** because the parent folders aren't in this repo. You have three options:

### Path strategy — choose one

| Option | What you do | Time | Recommendation |
|---|---|---|---|
| **A. Move tools into this repo** | Copy `9- KPI Performance/`, `8- GSW Flow/V2/`, `7- Onboarding Mapping/` into the portfolio repo. Update relative paths. | 30 mins | ✅ Recommended — keeps everything in one place |
| **B. Separate repos, separate Pages** | Publish each tool as its own GitHub Pages site. Update links to absolute URLs. | 2 hours+ | More work; better if tools grow large |
| **C. Disable links, use screenshots only** | Show a screenshot + "Available on request" or "View source" → GitHub repo. | 15 mins | Fastest, weakest evidence |

**Recommended for sprint:** Option A. Copy the three project folders into this repo before publishing.

```bash
# example — adjust paths to your actual project folder names
cp -r "../9- KPI Performance" .
cp -r "../8- GSW Flow" .
cp -r "../7- Onboarding Mapping" .
git add .
git commit -m "Bring linked projects into portfolio repo"
git push
```

---

## Step 5 — Updating the site (every time)

Once set up, deploying a change takes 3 commands:

```bash
git add .
git commit -m "Describe what you changed"
git push
```

GitHub Pages rebuilds within ~60 seconds. Refresh your live URL (hard refresh: Cmd+Shift+R) to see changes.

---

## Step 6 — Add a custom 404 page (optional, 10 mins)

If someone hits a wrong URL on your site, they'll see GitHub's default 404. You can override it.

1. Create `404.html` in the repo root.
2. Use the same `<head>` and nav as `index.html`, with a simple body: "Page not found — back to portfolio."
3. Commit and push.

---

## Step 7 — Add a README for the repo (5 mins)

The README is what people see when they visit `github.com/LetiCezar/portfolio`. Recruiters do check this.

Create `README.md`:

```markdown
# Leticia Cezar — Portfolio

Single-page portfolio. **Live site:** <https://leticezar.github.io/portfolio/>

Operations & process improvement. London.

## What's in this repo
- `index.html` — the site (single-file architecture).
- `assets/` — images, CV, OG share image.
- `9- KPI Performance/` etc. — internal tools linked from the site.

## Stack
HTML, CSS, vanilla JS. CDN-only: Inter font, Font Awesome 6.5, AOS 2.3.4.
No build step. Open `index.html` in any browser.

## Contact
leticiafcezar@gmail.com · [LinkedIn](https://www.linkedin.com/in/leticiafcezar/)
```

---

## Troubleshooting

| Problem | Likely cause | Fix |
|---|---|---|
| 404 on the GitHub Pages URL | Pages still building, or wrong branch selected | Wait 2 mins; check Settings → Pages → branch is `main` |
| Profile photo broken | `assets/profile.jpeg` not committed, or filename case mismatch | `ls assets/` to verify; macOS is case-insensitive but GitHub is case-sensitive |
| Site loads but no styles | Caching, or relative path issue | Hard refresh (Cmd+Shift+R) |
| Project links 404 | Linked folders not in repo | See Step 4 "Path strategy" — likely need Option A |
| `git push` rejected | Auth issue | Use a Personal Access Token, not password |
| Changes not showing | GitHub Pages rebuild in progress | Wait 60s; check Actions tab for build status |

---

## Pre-launch checklist (the final pass before sharing the URL)

- [ ] Live URL opens in incognito with no errors.
- [ ] No console errors (open DevTools → Console).
- [ ] All project links work.
- [ ] Profile photo, OG image, favicon all load.
- [ ] CV downloads.
- [ ] Lighthouse audit (DevTools → Lighthouse → Generate report): Performance ≥ 90, Accessibility ≥ 95.
- [ ] Test on phone (open the URL on your phone, not just DevTools mobile view).
- [ ] LinkedIn Post Inspector shows your OG card: <https://www.linkedin.com/post-inspector/>

When all eight tick → add the URL to your CV and LinkedIn → start applying.

---

## After launch

You don't need to think about hosting again. Every time you `git push`, your site updates. That's it.

If you ever want a custom domain (e.g. `leticiacezar.com`), the steps are:
1. Buy the domain (~£10/year — Namecheap, Porkbun, Cloudflare Registrar).
2. In GitHub Settings → Pages, add custom domain.
3. At your registrar, add CNAME pointing to `leticezar.github.io`.
4. Wait for DNS propagation (15 mins – 24h).

But that's for later. **For this sprint, the `github.io` URL is enough.**
