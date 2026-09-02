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
arac-international-main/
├── index.html                                  # Homepage (self-contained, all CSS and JS inline)
├── README.md                                   # This file
├── logos/                                      # Logo and brand image assets
│   └── arac-logo1.jpg
└── programs/                                   # Program detail pages (one file per program)
    ├── sdg-16-advocacy.html                    # Program 01
    ├── conflict-prevention.html                # Program 02
    ├── continuing-education.html               # Program 03
    ├── humanitarian-support.html               # Program 04
    ├── safety-security-risk-management.html    # Program 05
    └── research-analysis.html                  # Program 06
```

> Every page is self-contained. CSS and JavaScript are inlined in each file for zero-dependency portability, so any single page can be uploaded or replaced independently without breaking the others. All internal links are relative, so the site works both at `arac-international.org` and at the `github.io` project path.

---

## Sections

| Section | ID | Description |
|---|---|---|
| Navigation | — | Fixed dark navbar with dropdown menus and mobile hamburger |
| Hero | `#home` | Full-viewport headline, key statistics, and primary CTAs |
| Ticker | — | Auto-scrolling keyword bar in brand sage green |
| About / Mission | `#about` | Organization overview, founding principles, and four-pillar grid |
| Programs & Services | `#services` | Six-card grid linking to the six program detail pages |
| Our Impact | `#impact` | SDG showcase grid and key organizational metrics |
| Positive Peace | `#peace` | Animated IEP framework diagram with advocacy pillars |
| Founder Quote | — | Pull quote, credentials, and partner affiliations |
| Humanitarian Support | `#humanitarian` | Displacement data visualization and economic cost of violence |
| Get Involved | `#involve` | Mission and Vision, Partner, Donate, and Subscribe calls to action |
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

The `Programs` dropdown in the `<nav>` block links directly to the six files under `programs/`. A parallel mobile menu (`#mobilePanel`) carries the same links and is toggled by the hamburger button. When adding or renaming a program page, update three places: the desktop dropdown, the mobile panel, and the footer `Programs` column. On the program pages themselves, the same three blocks appear plus the pager near the foot of the page.

---

## Program Pages

Six program detail pages are live under `/programs/`. Each carries its own SEO metadata, Open Graph tags, Schema.org `WebPage` and `BreadcrumbList` markup, a breadcrumb trail, a cross-link pager to three sibling programs, and a closing call-to-action band.

| # | Page | File |
|---|---|---|
| 01 | SDG 16 Advocacy & Consulting | `programs/sdg-16-advocacy.html` |
| 02 | Conflict Prevention & Mediation | `programs/conflict-prevention.html` |
| 03 | Continuing Education | `programs/continuing-education.html` |
| 04 | Humanitarian Support | `programs/humanitarian-support.html` |
| 05 | Safety & Security Risk Management | `programs/safety-security-risk-management.html` |
| 06 | Research & Analysis | `programs/research-analysis.html` |

### Language Convention

Public-facing copy on this site uses nonprofit and NGO register throughout. The words *intelligence* and *tradecraft* are deliberately not used anywhere in site copy. Program 05 is titled **Safety & Security Risk Management** and Program 06 is titled **Research & Analysis**. Analytical method is described as *structured research* or *structured analysis*, with the Quanta Analytica process referenced as an analytical practice rather than as an intelligence function.

---

## Outbound Links

Canonical destinations used across the site. Update these in one pass if any change.

| Purpose | URL |
|---|---|
| Mission and Vision | `https://global.arac-international.org/about` |
| Donate / Support Us | `https://www.paypal.com/donate/?hosted_button_id=N48F8784BCPEE` |
| Newsletter subscribe | `https://newsletter.arac-international.org/subscribe` |
| Partner With Us / Contact | `mailto:info@arac-international.org` |
| Resources / Learn More | `https://discover.arac-international.org/information` |
| U.S. Institute of Diplomacy and Human Rights | `https://usidhr.org/` |
| IEP Ambassador Program | `https://www.economicsandpeace.org/training/iep-ambassador-program/` |
| INSSA | `https://inssa.org/about-us/` |
| IOSI Global | `https://iosi.global` |
| Lladner Business Solutions | `http://www.lladner.com/about.html` |
| Quanta Analytica | `https://quanta-analytica.com` |
| MNS Consulting | `https://mnshakoor.com` |

> **Note on Lladner.** The Lladner Business Solutions site does not serve over HTTPS. Its links are intentionally written as `http://`. Browsers may show a "not secure" notice when a visitor follows them. Do not rewrite these to `https://` unless the site adds a certificate, since doing so will break the link.

---

## Still To Build

- `/about` — Full organizational history, team bios, and governance (currently routed to `global.arac-international.org/about`)
- `/resources` — On-site research archive (currently routed to `discover.arac-international.org/information`)
- `/press` — Media coverage and press releases
- `/contact` — Contact form (currently routed to `mailto:info@arac-international.org`)

---

## Partners & Affiliations

- [Institute for Economics and Peace (IEP)](https://www.economicsandpeace.org/training/iep-ambassador-program/) — IEP Ambassador Program
- [INSSA — International NGO Safety & Security Association](https://inssa.org/about-us/)
- [IOSI Global](https://iosi.global) — International security think tank and practitioner network
- [U.S. Institute of Diplomacy and Human Rights](https://usidhr.org/) — Certified Human Rights Consultant
- [Lladner Business Solutions LLC](http://www.lladner.com/about.html) — Senior partner, global development and risk management
- [Quanta Analytica](https://quanta-analytica.com) — Structured research and analysis practice
- [MNS Consulting](https://mnshakoor.com/) — Research and analysis consulting affiliate

---

## License

© 2026 ARAC International Inc. All rights reserved.

This repository is maintained for the operational purposes of ARAC International Inc. The source code structure and design system may be reused for nonprofit and peacebuilding purposes with attribution. Content, branding, and organizational materials remain the exclusive property of ARAC International Inc.

---

## Contact

**ARAC International Inc.**
Website: [arac-international.org](https://arac-international.org)
Founded and maintained by M. Nuri Shakoor, Founder & Senior Research Analyst

For partnership, research, or consulting inquiries, visit the Contact page or reach out through the organizational website.
