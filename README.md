# sgarciatorres.com

Personal academic website of Sebastian Garcia-Torres. Static HTML, no build step.

## Files

- `index.html` — main page (About, News, Research, CV, Contact)
- `imprint.html` — imprint and privacy policy
- `CNAME` — custom domain for GitHub Pages (`www.sgarciatorres.com`)
- `assets/` — add these two files here:
  - `photo.jpg` — your portrait (roughly 400×500 px or larger; the page crops it to 180×220). If missing, the page simply hides the image slot.
  - `garcia_torres_cv.pdf` — your CV (the "Download CV" button links to it)

## Deploy on GitHub Pages

1. Create a repository, e.g. `sgarciatorres/sgarciatorres.github.io` (or any repo name).
2. Put all files from this folder at the repository root and push.
3. In the repo: Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Still under Settings → Pages, set Custom domain to `www.sgarciatorres.com` and, once DNS has propagated, enable "Enforce HTTPS".

## DNS (at your domain registrar)

Since the domain currently points at Google Sites, replace those records with:

- `CNAME` record: host `www` → `<your-github-username>.github.io`
- Four `A` records for the apex (`sgarciatorres.com`) → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
  (These are GitHub Pages' published IPs — verify them against the current GitHub Pages docs before setting, as they can change.)

GitHub will then redirect `sgarciatorres.com` → `www.sgarciatorres.com` automatically. Also remove the custom-domain mapping inside Google Sites so it releases the domain.

## Editing content

Everything is plain HTML in `index.html`. To add a news item, copy one `<li>` block in the `ul.news` list. To add a paper, copy one `<article class="pub">` block.
