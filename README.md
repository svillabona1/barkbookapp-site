# barkbookapp.com

The **public** marketing + legal site for **Barkbook** — a gamified "Pokédex for
real dogs" PWA (scan the dogs you meet, ID the breed, collect them in a journal).

This repo is intentionally **public** because GitHub Pages' free tier only serves
public repos. It contains **no application code, no secrets, and no user data** —
just static HTML/CSS and two image assets. The Barkbook app itself (and its
backend) lives in a separate **private** repo and is served from its own origin;
nothing here talks to it.

## What it hosts

Plain static HTML/CSS — no framework, no build step, no JavaScript.

- `index.html` — the landing page (pitch + feature blurbs; the app is in
  friends & family testing, so there's no install link yet).
- `privacy.html` — the COPPA-oriented privacy policy (**v0.1 DRAFT**, under
  review).
- `consent/success.html`, `consent/already.html`, `consent/expired.html`,
  `consent/revoked.html`, `consent/invalid.html` — the five parental-consent
  outcome pages. A future change to the backend's `confirm-consent` function
  will **302-redirect** parents here instead of rendering HTML inline (this
  fixes a shared-domain content-type limitation on `*.supabase.co`). Every
  outcome state gets a real page so no parent ever lands on a bare 404.
- `404.html` — branded not-found (GitHub Pages serves it automatically).
- `assets/` — shared stylesheet, the Barkbook banner, and a 512px square mark.

## Hosting

GitHub Pages, deployed from `main` (root). `CNAME` points the site at the custom
domain `barkbookapp.com`; DNS is configured at the registrar separately. Until
DNS resolves, the site is reachable at the `*.github.io` URL.

Contact for the site (privacy/COPPA requests): **privacy@barkbookapp.com**.
