# dubare.co

Static rebuild of the DuBare homepage (previously hosted via Gamma), ready for GitHub Pages.

## Files
- `index.html` — page content
- `style.css` — styles
- `CNAME` — tells GitHub Pages to serve this repo under `dubare.co`

## Deploy (GitHub Pages)
1. Create a new **public** GitHub repo (e.g. `dubare-site`).
2. Upload these three files to the repo root (drag-and-drop on the GitHub web UI works, or `git push`).
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/root`.
4. Under **Settings → Pages → Custom domain**, enter `dubare.co` and save (this also verifies the CNAME file).
5. At your domain registrar/DNS provider for dubare.co, point the domain at GitHub Pages:
   - Add an `A` record for the apex (`@`) to each of GitHub's IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Optional: add a `CNAME` record for `www` pointing to `<your-github-username>.github.io`
6. Wait for DNS to propagate (can take a few minutes to a few hours), then check "Enforce HTTPS" in Pages settings once GitHub shows the domain as verified.

## Before you deploy: add the 5 images
The `assets/` folder is empty. Save these 5 files from their current (Gamma-hosted) URLs and drop them into `assets/` using these exact names, then the site has zero dependency on Gamma:

| Save as | Source URL |
|---|---|
| `assets/portfolio-1.jpg` | https://cdn.gamma.app/lhynkfg7b8tw5pv/generated-images/62Hhj1L-UROm8re4lZbSA.jpg |
| `assets/portfolio-2.jpg` | https://cdn.gamma.app/lhynkfg7b8tw5pv/generated-images/SDXs7y924jQHBS6Mv7Eh5.jpg |
| `assets/portfolio-3.jpg` | https://cdn.gamma.app/lhynkfg7b8tw5pv/generated-images/wPW6jncJsFUE1jg2XIg4g.jpg |
| `assets/portfolio-4.jpg` | https://cdn.gamma.app/lhynkfg7b8tw5pv/generated-images/H0fwEXuWoJ6c6WFZVinzq.jpg |
| `assets/contact-banner.jpg` | https://cdn.gamma.app/lhynkfg7b8tw5pv/generated-images/KuBSUMS1SC2sqD2uaPkl1.jpg |

Easiest way: open each URL in a browser tab, right-click → "Save image as…", save with the name above into the `assets` folder before uploading to GitHub. (I couldn't fetch these myself — my sandbox's network allowlist doesn't include Gamma's asset CDN.)

Once those 5 files are in `assets/`, this site has no runtime or hosting dependency on Gamma at all — it's plain HTML/CSS served by GitHub Pages.
