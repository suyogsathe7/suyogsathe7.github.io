# Portfolio — Setup & Publish Guide

This is a single-page portfolio site (plain HTML/CSS/JS, no build step) styled as a dark
terminal / git-diff developer theme, built around your Spring Boot upgrade skill work.

## 1. Add your resume

Drop your resume PDF into `assets/resume.pdf` (must be that exact filename, or update the
two `href="assets/resume.pdf"` links in `index.html` if you name it differently).

I intentionally didn't pick which version to include — you have a Netherlands-specific one
(mentions HSM eligibility) and could reasonably want a more country-neutral version for a
public portfolio that any recruiter might land on. Pick whichever fits how you want this
page used, or add a version-selector later if you end up wanting per-country resumes.

## 2. Publish with GitHub Pages

**Option A — personal site at `yourusername.github.io`:**
1. Create a new GitHub repo named exactly `suyogsathe7.github.io`
2. Push these files (`index.html`, `assets/resume.pdf`) to the `main` branch, at the repo root
3. Go to the repo's Settings → Pages — it should already show as deployed from `main`
4. Your site is live at `https://suyogsathe7.github.io`

**Option B — project site at `yourusername.github.io/portfolio`:**
1. Create a repo with any name, e.g. `portfolio`
2. Push these files to `main`
3. Settings → Pages → Source: Deploy from branch → `main` / `/(root)`
4. Live at `https://suyogsathe7.github.io/portfolio`

Either way, it can take a minute or two for the first deploy to go live.

## 3. Local preview before pushing

No build tools needed — just open `index.html` directly in a browser, or serve it locally:

```bash
cd portfolio
python3 -m http.server 8000
# visit http://localhost:8000
```

## 4. Editing content

Everything lives in `index.html` — no templating, no dependencies beyond two Google Fonts
(JetBrains Mono, Inter) loaded via CDN. Search for these sections to update:

- `<header class="hero">` — name, title, tagline
- `#about` — bio + skills import block
- `#work` — featured project (Spring Boot skill) + secondary project (TS migration CLI)
- `#experience` — git-log-styled work history
- `#education`
- `#contact` — email, LinkedIn, GitHub, resume links

If you want a second featured project (e.g. the RAG support chatbot) added to the `#work`
section later, just say the word and I'll slot it in using the same diff/stats layout.
