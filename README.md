# shrikantganoje.com

Personal website for Shrikant Ganoje — single static page, no build step required.

## Files
- `index.html` — the entire site (HTML + CSS + a few lines of JS for the footer year)
- `headshot.jpg` — your photo, shown in the hero band
- `CNAME` — tells GitHub Pages this repo serves `www.shrikantganoje.com`

## 1. Push to your GitHub repo

From this folder:

```bash
git init
git remote add origin https://github.com/ganojeshrikant/Shrikant-Ganoje.git
git add index.html headshot.jpg CNAME README.md
git commit -m "Add personal website"
git branch -M main
git push -u origin main
```

If the repo already has commits, skip `git init`/`branch -M main` and instead `git clone` it, copy these three files in, then `git add`, `git commit`, `git push`.

## 2. Turn on GitHub Pages

1. On GitHub, go to your repo → **Settings** → **Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Set **Branch** to `main` and folder to `/ (root)`. Save.
4. GitHub will give you a URL like `https://ganojeshrikant.github.io/Shrikant-Ganoje/` — confirm the site loads there first.

## 3. Point your custom domain at it

Still in **Settings → Pages**, under "Custom domain", enter:

```
www.shrikantganoje.com
```

GitHub will re-detect the `CNAME` file already in the repo and use it.

Then, with whoever you registered `shrikantganoje.com` through (GoDaddy, Namecheap, Google Domains, etc.), add these DNS records:

| Type  | Host/Name | Value                          |
|-------|-----------|--------------------------------|
| CNAME | www       | `ganojeshrikant.github.io.`    |
| A     | @         | `185.199.108.153`              |
| A     | @         | `185.199.109.153`              |
| A     | @         | `185.199.110.153`              |
| A     | @         | `185.199.111.153`              |

The four `A` records make the bare domain (`shrikantganoje.com`, no `www`) redirect to `www.shrikantganoje.com`. DNS changes can take anywhere from a few minutes to 24 hours to propagate.

Once GitHub detects the domain is correctly pointed, go back to **Settings → Pages** and check **Enforce HTTPS** so the site serves over `https://`.

## Editing later

Everything is in `index.html` — content, layout, and styling all live in that one file, so you (or Claude) can open it and edit text directly without touching build tooling.
