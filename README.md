# pulsin.network

Static website of Pulsin Network, ready for GitHub Pages. No build step: every file is final.

## Structure

```
index.html            Home
about.html            About
hubs.html             Hubs
residencies.html      Residencies
manifesto.html        Manifesto
404.html              Page not found
images/               WebP images with SEO names + world map (SVG) + share image
fonts/                VioletSans, Hipnouma, PulsinInter (woff2, Latin subset)
robots.txt            Open to Google and AI crawlers
sitemap.xml           The 5 pages
llms.txt              Site summary for AI assistants
site.webmanifest, favicon.svg, apple-touch-icon.png
CNAME                 pulsin.network
.nojekyll             Serves files as they are
```

Every internal link is relative (`about.html`, `images/...`). Only `404.html` uses root paths, because GitHub serves it from any URL.

## Publishing on GitHub Pages

1. Upload the whole contents of this folder to the root of the repository (branch `main`), including the hidden files `CNAME` and `.nojekyll`.
2. In the repository: **Settings → Pages → Build and deployment**, set Source to *Deploy from a branch*, Branch to `main`, folder `/ (root)`. Save.
3. In **Custom domain**, type `pulsin.network` and save.
4. Where the domain was bought, add these DNS records:
   - `A` records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www` → `YOUR-USER.github.io`
5. When GitHub confirms the DNS (it can take up to a few hours), check **Enforce HTTPS**.

## Testing locally

Open `index.html` in the browser. Fonts and links work without a server.

## How it works

Each page contains the desktop design (1100 px and up) and the mobile design (tablet and phone). A small script (under 1 KB) picks the right one for the screen width, and it switches again if the window is resized. The desktop design scales proportionally between 1100 and 1440 px. All animations are CSS and respect *reduce motion*.
