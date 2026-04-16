# Stel Sites

Static landing pages for the Stel Global brand family. Pure HTML + CSS, deployed via Cloudflare Pages.

## Sites

| Folder | Domain | Purpose |
|--------|--------|---------|
| `clubloop-ai/` | clubloop.ai | "ClubLoop powers HoopsLoop" landing page |
| `stelcollective/` | stelcollective.com | App development umbrella, links to products |

Redirects (configured in Cloudflare dashboard, no code needed): clubloop.app → clubloop.ai, tryclubloop.com → clubloop.ai.

## Structure

```
stel-sites/
├── CLAUDE.md
├── _shared/
│   ├── styles.css        # Design tokens, typography, base styles
│   └── reset.css         # Minimal CSS reset
├── clubloop-ai/
│   └── index.html
├── stelcollective/
│   └── index.html
└── README.md
```

## Constraints

- **No JavaScript.** These are static pages. HTML + CSS only.
- **No build tools.** No bundlers, no preprocessors, no npm. Files serve as-is.
- **No frameworks.** No Tailwind, no React, no nothing. Vanilla CSS with custom properties from `_shared/styles.css`.
- **Shared design tokens via CSS custom properties.** Both sites import `_shared/styles.css` and `_shared/reset.css`. All colors, fonts, spacing, and breakpoints are defined as custom properties so the sites stay visually cohesive.
- **Mobile-first.** Every page must look good on a phone. Start with mobile layout, add desktop breakpoints.
- **Fast.** Target sub-second load. Inline critical CSS if needed. Google Fonts (Inter or similar) is the only external resource allowed.

## Design direction

Clean, modern, minimal. These are single-page brand presence sites, not marketing funnels.

- Warm white base (not clinical blue-white, think `#FAFAF8` territory)
- Generous whitespace, clear hierarchy
- Typography-forward: size and weight do the hierarchy work, not decoration
- One call to action per page
- No stock photos, no illustrations. Text and layout carry the design.
- Dark text on light background. Simple accent color for interactive elements.

## Page content

**clubloop.ai:**
- ClubLoop wordmark (text treatment, no logo asset yet)
- Tagline: "AI-powered club management for youth sports"
- "Currently powering" section with a HoopsLoop card (name, one-line description, link to hoopsloop.com)
- Footer: "A Stel Global company" with link to stelglobal.com

**stelcollective.com:**
- Stel Collective wordmark
- One-liner positioning the practice (building focused, polished apps for underserved communities)
- Product cards: HoopsLoop (→ hoopsloop.com), ClubLoop (→ clubloop.ai)
- Footer: "A Stel Global company" with link to stelglobal.com

## Deployment

Each site folder is its own Cloudflare Pages project. No build command. Output directory is the site folder. Custom domain configured in the Pages project settings.

## Brand context

- **Stel Global LLC** is the legal entity (stelglobal.com)
- **Stel Collective** (stelcollective.com) is the app development practice under Stel Global
- **ClubLoop** (clubloop.ai) is the technology umbrella that powers sport-specific apps
- **HoopsLoop** (hoopsloop.com) is the first product: youth basketball club management
- hoopsloop.com's own landing page is a separate, richer effort in the HoopsLoop repo. Don't build it here.
