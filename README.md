# ARAC International — arac-international.org

**ARAC International Inc.** is a 501(c)(3) nonprofit organization dedicated to advocating for global security, human rights, and peacebuilding efforts. This repository contains the source code for the organization's public-facing website at [arac-international.org](https://arac-international.org).

> *"For a world of peace, let humanity take the lead."*

---

## Overview

The site is built as a single-file, dependency-free HTML homepage using vanilla HTML5, CSS3, and minimal JavaScript. No build toolchain, no frameworks, no npm. It is designed to be deployed directly to any static hosting environment — GitHub Pages, Netlify, Cloudflare Pages, or a standard web server — without a compilation step.

The design system draws from ARAC International's existing brand: cream and soft olive-green backgrounds, sage and charcoal accent colors, Cormorant Garamond serif headlines, and DM Sans body copy. Layout inspiration was drawn from mission-driven nonprofit sites prioritizing clarity, credibility, and calls to action.

---

## Repository Structure

```
arac-international/
├── index.html          # Main homepage (self-contained — all CSS and JS inline)
├── README.md           # This file
└── assets/             # Optional: place logo, images, and favicon here
    ├── logo.png
    └── favicon.ico
```

> All CSS and JavaScript are currently inlined in `index.html` for zero-dependency portability. As the site grows into multi-page architecture, styles should be extracted to `assets/css/main.css`.

---

## Sections

| Section | ID | Description |
|---|---|---|
| Navigation | — | Fixed dark navbar with dropdown menus and mobile hamburger |
| Hero | `#home` | Full-viewport headline, key statistics, and primary CTAs |
| Ticker | — | Auto-scrolling keyword bar in brand sage green |
| About / Mission | `#about` | Organization overview, founding principles, and four-pillar grid |
| Programs & Services | `#services` | Six-card grid covering all ARAC program areas |
| Our Impact | `#impact` | SDG showcase grid and key organizational metrics |
| Positive Peace | `#peace` | Animated IEP framework diagram with advocacy pillars |
| Founder Quote | — | Pull quote, credentials, and partner affiliations |
| Humanitarian Support | `#humanitarian` | Displacement data visualization and economic cost of violence |
| Get Involved | `#involve` | Partner, Donate, and Subscribe calls to action |
| Partners | — | Affiliation and partner logo strip |
| Footer | `#contact` | Site navigation, social links, and legal line |

---

## Design System

### Color Palette

| Token | Hex | Usage |
|---|---|---|
| `--cream-light` | `#fafaf0` | Page background |
| `--cream` | `#f5f4e8` | Section backgrounds, hero wave |
| `--sage` | `#8b9a5b` | Primary brand accent, buttons, borders |
| `--sage-dark` | `#6b7a3e` | Hover states, deep accent |
| `--sage-muted` | `#b8c485` | Secondary text on dark backgrounds |
| `--sage-bg` | `#a8b870` | Section fills (Impact, Get Involved) |
| `--olive` | `#7a8c4a` | Gradient endpoints |
| `--charcoal` | `#2a2a22` | Navigation, dark sections, footer |
| `--charcoal-mid` | `#3d3d30` | Quote section background |
| `--text-dark` | `#1e1e16` | Headings on light backgrounds |
| `--text-body` | `#3a3a2e` | Body copy |
| `--text-muted` | `#6a6a56` | Secondary body copy, captions |

### Typography

| Role | Family | Weight |
|---|---|---|
| Display / Headlines | Cormorant Garamond | 300, 400, 600 (italic variants included) |
| Body / UI | DM Sans | 300, 400, 500, 600 |

Fonts are loaded from Google Fonts. For offline or self-hosted deployment, download and serve from `assets/fonts/`.

### Responsive Breakpoint

The single breakpoint at `768px` collapses all multi-column grid layouts to single-column stacks and activates the mobile hamburger menu.

---

## Deployment

### GitHub Pages

1. Push this repository to GitHub.
2. In **Settings → Pages**, set the source to the `main` branch and `/ (root)`.
3. Rename `index.html` if not already named `index.html`.
4. The site will be live at `https://<your-org>.github.io/<repo-name>/`.

For a custom domain (`arac-international.org`):
1. Add a `CNAME` file to the repository root containing `arac-international.org`.
2. Configure your DNS provider with the appropriate `A` records or `CNAME` pointing to GitHub Pages.

### Netlify / Cloudflare Pages

Drag and drop the repository folder into the Netlify UI, or connect the GitHub repo directly. No build command required. Publish directory: `/` (root).

### Traditional Web Hosting (FTP / cPanel)

Upload `index.html` and the `assets/` folder to the `public_html` or `www` directory of the hosting account.

---

## Customization

### Updating Copy

All text content lives directly in `index.html`. Search for the relevant section comment (e.g., `<!-- MISSION -->`, `<!-- SERVICES -->`) to locate and edit text.

### Replacing the Logo

The About section currently renders a CSS text fallback. To replace it with the actual ARAC logo:

```html
<!-- Inside .mission-img-inner, replace the fallback div with: -->
<img src="assets/logo.png" alt="ARAC International" style="width:200px;height:200px;object-fit:contain;">
```

### Adding a Favicon

Add a `favicon.ico` or `favicon.png` to the `assets/` directory and insert into `<head>`:

```html
<link rel="icon" type="image/png" href="assets/favicon.png">
```

### Navigation Links

Update `href` values in the `<nav>` block to point to internal section IDs or separate pages as the site expands.

---

## Planned Expansions

The following pages are referenced in navigation but not yet built:

- `/about` — Full organizational history, team bios, and governance
- `/programs/sdg-16` — SDG 16 Advocacy & Consulting detail page
- `/programs/conflict-prevention` — Conflict Prevention & Mediation detail page
- `/programs/humanitarian` — Humanitarian Support Initiatives detail page
- `/programs/education` — Continuing Education program page
- `/resources` — Research reports, intelligence briefs, and Flashpoints & Frameworks archive
- `/press` — Media coverage and press releases
- `/contact` — Contact form and organizational contact information
- `/donate` — Donation page

---

## Partners & Affiliations

- [Institute for Economics and Peace (IEP)](https://www.economicsandpeace.org/) — IEP Ambassador Program
- [INSSA — International NGO Safety & Security Association](https://www.inssa.org/)
- [IOSI Global](https://www.iosiglobal.org/) — International security think tank and intelligence sharing network
- US Institute of Diplomacy and Human Rights — Certified Human Rights Consultant
- [Lladner Business Solutions LLC](https://lladner.com/) — Global development and risk management partner
- [MNS Consulting](https://mnshakoor.com/) — Research and intelligence consulting affiliate

---

## License

© 2024 ARAC International Inc. All rights reserved.

This repository is maintained for the operational purposes of ARAC International Inc. The source code structure and design system may be reused for nonprofit and peacebuilding purposes with attribution. Content, branding, and organizational materials remain the exclusive property of ARAC International Inc.

---

## Contact

**ARAC International Inc.**
Website: [arac-international.org](https://arac-international.org)
Founded and maintained by M. Nuri Shakoor, Founder & Senior Research Analyst

For partnership, research, or consulting inquiries, visit the Contact page or reach out through the organizational website.
