# Tiffany Masterclass Proposal — Deploy Notes

A static, single-page proposal site. Drop it anywhere that hosts static HTML.

## Fastest path — Netlify Drop (60 seconds, no account needed)

1. Open **https://app.netlify.com/drop**
2. Drag this entire folder onto the page
3. You'll get a URL instantly: `https://[random-name].netlify.app`
4. Optional — claim the site to rename it to something like `tiffany-masterclass-preview.netlify.app`

Send that URL to Tiffany. Done.

## Cleaner path — Vercel via CLI

```bash
cd tiffany-masterclass-site
npx vercel
# Follow prompts — first deploy will ask you to log in
# You'll get a tiffany-masterclass-site.vercel.app URL
```

## GitHub Pages path (if you want it under ebeprstudios)

1. Create a new repo: `ebeprstudios/tiffany-masterclass-proposal`
2. Push `index.html` to `main`
3. Settings → Pages → Source: `main` → `/ (root)` → Save
4. URL: `https://ebeprstudios.github.io/tiffany-masterclass-proposal`

## Custom domain (optional, after Tiffany approves)

Both Netlify and Vercel support custom domains in Settings. Point a subdomain like `preview.tiffanyhaynes.co` at it.

## Notes

- This is a static page — no backend, no build step
- The form is a placeholder. When she approves, wire it to her actual provider (Kajabi/Kartra/ConvertKit/etc.)
- Fonts are Google-hosted (Fraunces + EB Garamond + Public Sans). Swap to licensed TAN Angleton + The Youngest Serif when going live.
