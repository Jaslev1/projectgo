# GSTV Brand Identity Guidelines, Refresh 1.0

Static site, three views of the same refresh.

## Routes

| URL | File | Format |
| --- | --- | --- |
| `/` | `index.html` | Interactive scroll doc, full system, all imagery routes |
| `/slides` | `slides.html` | 16-slide landscape deck, same content tightened for screen |
| `/guidelines.pdf` | `guidelines.pdf` | Downloadable PDF, 1280x720 landscape, 16 pages |

All assets (logos, photos, Droplet SVG) are embedded as base64. No external dependencies except Google Fonts (Montserrat).

## Deploy

### Option A: drag and drop

1. Go to https://vercel.com/new
2. Drag this folder onto the page (or zip and drop the zip)
3. Click Deploy

No build step, no environment variables, no framework preset needed. Vercel will detect it as a static site.

### Option B: Vercel CLI

```bash
npm install -g vercel
cd gstv-vercel
vercel
```

Follow the prompts. First deploy creates the project. Subsequent `vercel --prod` pushes to production.

### Option C: GitHub then Vercel

```bash
cd gstv-vercel
git init
git add .
git commit -m "GSTV brand guidelines refresh 1.0"
git remote add origin <your-repo-url>
git push -u origin main
```

Then on https://vercel.com/new, import the repo. Auto-deploys on every push.

## Custom domain

In the Vercel project settings, Domains tab, add the domain you want. Update DNS at the registrar to point to Vercel's nameservers or add the CNAME they provide.

## Files

```
gstv-vercel/
  index.html       Scroll doc, ~1.9 MB
  slides.html      Slide deck, ~1.8 MB
  guidelines.pdf   PDF, ~1.4 MB
  vercel.json      Clean URLs, cache headers, PDF inline disposition
  README.md        This file
```

Total deploy size: about 5 MB. Well under Vercel's free-tier limits.

Prepared by Prosper &amp; Partners.
