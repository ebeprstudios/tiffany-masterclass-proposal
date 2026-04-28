# Tiffany Haynes & Co. — Site Proposal

A modernized, full multi-page rebuild of tiffanyhaynesco.com. Static HTML, deploys anywhere.

## Pages

| Path | File | Purpose |
|---|---|---|
| `/` | `index.html` | Home — full landing page |
| `/about` | `about.html` | Tiffany's full story, fun facts, the quiz |
| `/gods-math` | `gods-math.html` | The God's Math framework — **proposal copy, needs review** |
| `/masterclass` | `masterclass.html` | Free masterclass registration — replaces tiffanysmasterclass.com |

## Brand color merge

Existing site (Showit) leaned soft pink + airy cream. THCO official brand evolves toward warm cream, dusty stone, deep red, and charcoal. The merge:

- **#FFFDF5** warm cream → primary background
- **#FAF3E5** warm cream variant → soft accent backgrounds
- **#F4F0EB** linen → section variation
- **#E3D3C8** dusty blush stone → carries the "pink" warmth without being saccharine
- **#D4BFB1** stone deep → gradients, hover states
- **#A00605** deep red → CTAs, accents, conviction moments
- **#414141** charcoal → primary text + dark sections

The old site's feminine warmth is preserved through the stone/blush. The deep red and charcoal bring the editorial authority THCO is evolving toward.

## Typography

- **Display:** Fraunces (high-contrast editorial serif — stand-in for TAN Angleton)
- **Body:** EB Garamond (refined serif — stand-in for The Youngest Serif)
- **Utility:** Public Sans (matches THCO brand spec exactly)

When going to production, swap Fraunces and EB Garamond for licensed TAN Angleton + The Youngest Serif.

## Deploy

### Vercel (recommended)

```bash
cd tiffany-site
npx vercel
```

The `vercel.json` enables clean URLs out of the box (`/about` instead of `/about.html`).

If pushing through GitHub instead — push the folder contents to your repo, then import the repo in Vercel. No build settings needed.

### Netlify

Drag the entire `tiffany-site` folder onto **app.netlify.com/drop**. Clean URLs are on by default.

### GitHub Pages

Push to repo → Settings → Pages → Source: `main` → `/` (root). URLs will include `.html` unless you add Jekyll config; for clean URLs, prefer Vercel or Netlify.

## What needs review before going live

1. **All four pages have a `Replace with portrait` placeholder** where Tiffany's actual photos should go. Aspect ratios are 4:5 (or 4:3 for resource cards). Brand rule: no awkward frames, sharp and well-lit.
2. **God's Math page is proposal copy.** I drafted it from the brand framework (`1 + 1 = 10,000`, "It disrupts. It breaks the rules"). Tiffany's actual teaching content should replace the body copy. The visual structure can stay. A red dismiss-able banner appears on the page noting this.
3. **Masterclass form** is currently a placeholder. Wire to Kajabi / Kartra / ConvertKit / whichever provider she's using, and attach her existing Facebook pixel (`943376613232304` per the existing site).
4. **Resources section on home** points to `#` — link these to the actual blog posts when ready.
5. **Footer Contact + Newsletter links** also point to `#`.

## Files

```
tiffany-site/
├── index.html         # Home
├── about.html         # About
├── gods-math.html     # God's Math
├── masterclass.html   # Masterclass
├── styles.css         # Shared design system
├── vercel.json        # Clean URL config
└── README.md
```

## Notes for production

- Subtle SVG paper-grain texture is applied via `body::before` — scales infinitely, very small file footprint
- All images are CSS gradient placeholders — replace with actual `<img>` tags pointing to optimized portraits
- All four pages share the same nav and footer — if you change one, change them in all four files (or refactor into a build process if the site grows)
- Mobile nav uses a simple JS toggle on a hamburger icon
- Scroll-reveal animations use IntersectionObserver — graceful no-JS fallback (content shows immediately if JS disabled)
