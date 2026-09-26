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
├── robots.txt                                  # Crawler rules for search engines
├── sitemap.xml                                 # Indexable URL list for search engines
├── logos/                                      # Logo and brand image assets
│   └── arac-logo1.jpg
├── tools/                                      # Embedded web applications
│   └── inform-severity-dashboard.html          # ARAC INFORM Severity Dashboard (iframe embed)
├── stratcom/                                   # STRATCOM: public communications hub
│   ├── index.html                              # STRATCOM hub (Research, Analysis, Alerts, Community News, SitReps, Frameworks)
│   ├── assets/
│   │   └── ooda-risk-unga81-thumb.jpg          # Shared thumbnail / OG image for the OODA-Risk framework
│   └── frameworks/                             # Field analysis & risk-assessment framework documents
│       ├── index.html                          # Frameworks hub
│       └── ooda-risk-unga81-casestudy.html     # Covering & Monitoring High-Risk Events and Political Protests
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

## Search Engine Indexing

Two files at the repository root control how search engines crawl and index the site: `robots.txt` and `sitemap.xml`. Both must live at the domain root, so on GitHub Pages that means the repository root, not inside `programs/`.

### robots.txt

Allows all crawlers on all paths and points to the sitemap:

```
User-agent: *
Allow: /

Sitemap: https://arac-international.org/sitemap.xml
```

Verify it is reachable at `https://arac-international.org/robots.txt` after deploying. If it 404s, GitHub Pages has not picked up the file, or the custom domain is not yet resolving.

### sitemap.xml

Lists the homepage and all six program pages with their canonical `https://arac-international.org/...` URLs, matching the `<link rel="canonical">` tag on each page. `lastmod` should be updated whenever a listed page's content changes materially; `changefreq` and `priority` are advisory hints most crawlers weight lightly, so they do not need frequent upkeep. When a new page is added to `programs/`, add a matching `<url>` block here at the same time, or search engines will find it only by following the link from the homepage or another page.

### Submitting to Google

1. In [Google Search Console](https://search.google.com/search-console), add `arac-international.org` as a property and verify ownership (DNS TXT record is usually simplest for a custom domain).
2. Under **Sitemaps**, submit `sitemap.xml`.
3. Under **URL Inspection**, request indexing for the homepage and, optionally, each program page, to speed up initial crawl rather than waiting for Google to discover them on its own.
4. Re-submit the sitemap (or request indexing on the specific page) after any significant content change; Google recrawls on its own schedule otherwise, which can take days to weeks for a low-traffic new site.

### THINK is a separate property

`think.arac-international.org` is a distinct subdomain served from its own repository (`mnshakoor/think-site`). Search engines treat subdomains as separate hosts, so this `robots.txt` and `sitemap.xml` do not cover it and cannot list its pages. THINK needs its own `robots.txt`, its own `sitemap.xml`, and its own Google Search Console property and verification.

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

The nav dropdown, mobile panel, and footer Programs column list the six program pages. The INFORM Severity Dashboard under `tools/` is currently reachable from the sitemap and from cross-links on the Safety & Security and Humanitarian program cards on its own page; it is not yet in the site navigation.

### Language Convention

Public-facing copy on this site uses nonprofit and NGO register throughout. The words *intelligence* and *tradecraft* are deliberately not used anywhere in site copy. Program 05 is titled **Safety & Security Risk Management** and Program 06 is titled **Research & Analysis**. Analytical method is described as *structured research* or *structured analysis*, with the Quanta Analytica process referenced as an analytical practice rather than as an intelligence function.

---

## Tools

Pages under `tools/` embed externally hosted ARAC web applications inside the site design system, so a visitor stays on `arac-international.org` while using them.

| Page | Embeds | File |
|---|---|---|
| ARAC INFORM Severity Dashboard | `https://arac-acaps-analytics.nuri-shakoor.workers.dev/` | `tools/inform-severity-dashboard.html` |

### How the embed works

The application is loaded in a full-height `<iframe>` sized with `clamp(560px, calc(100vh - 210px), 1100px)`, so it fills the viewport below the header on a desktop screen and falls back to a fixed height on phones. A loading state sits behind the frame and clears on the iframe's `load` event, with a twelve second ceiling in case that event is missed. A Full Screen button uses the Fullscreen API on the frame wrapper and falls back to opening the application in a new tab where that API is unavailable.

### Before adding another embed

Check that the target application does not send a `X-Frame-Options: DENY` or `SAMEORIGIN` header, and does not set a `Content-Security-Policy` with a restrictive `frame-ancestors` directive. Either one will leave the frame blank with no visible error. Verify with:

```
curl -sSI <application-url> | grep -iE "x-frame-options|content-security-policy"
```

The Cloudflare Worker hosting the INFORM Severity Dashboard sends neither header, so it embeds cleanly. If a future application does send them, the page must link out to it instead of framing it.

---

## STRATCOM

`stratcom/` is ARAC's public communications hub: a home for research, analysis, alerts, local community news and events, SitRep updates (produced with Quanta Analytica, Lladner Business Solutions, and IOSI Global), and field-analysis frameworks. It has its own two-tier structure, each tier with its own `index.html`, full site navigation, header, and SEO metadata:

```
stratcom/index.html                              STRATCOM hub — all six content areas
stratcom/frameworks/index.html                    Frameworks hub — lists every framework document
stratcom/frameworks/ooda-risk-unga81-casestudy.html   the first framework document
```

`stratcom/index.html` is a card-grid landing page for the six content areas (Research, Analysis, Alerts, Local Community News & Events, SitRep Updates, Frameworks) plus a "Latest Framework" spotlight. Only **Frameworks** is live and clickable today; the other five are marked "Coming Soon" with a short description rather than linked to a page that does not exist yet — update a card to `hub-card is-live` and add its `href` once that content area has a real page to point to.

`stratcom/frameworks/index.html` lists every framework document as a card: title, author byline, one-line description, thumbnail, and a link to the full page. Add a new `.fw-card` block here whenever a framework document is published.

Each individual framework document (e.g. `ooda-risk-unga81-casestudy.html`) is a long-form, single-file article page reusing the site design system, with an in-page table of contents, data tables, and inline SVG figures rather than embedded images, so the page stays self-contained apart from its shared thumbnail.

| Page | Author | File |
|---|---|---|
| Covering & Monitoring High-Risk Events and Political Protests (OODA-Risk framework) | M. Nuri Shakoor, SRMP-R | `stratcom/frameworks/ooda-risk-unga81-casestudy.html` |

### Thumbnail / OG image

`stratcom/assets/ooda-risk-unga81-thumb.jpg` is a 1200×630 card rendered from the framework's own OODA-Risk diagram (dark navy/gold/charcoal, matching the diagram inside the page). It is used three ways: the card image on the Frameworks hub, the feature image on the STRATCOM hub, and the `og:image`/`twitter:image` for the framework page itself. A new framework document should get its own thumbnail in the same folder and the same 1200×630 size, so hub cards stay visually consistent; card images use `object-fit: contain` against the card's dark background rather than `cover`, so a differently-proportioned thumbnail won't cut off text at the edges.

### SEO and authorship

Framework documents carry `Article` Schema.org markup (not `WebPage`) so the author is machine-readable: a `Person` node with name, credential, and a link to `mnshakoor.com`, plus `datePublished`, `articleSection`, and `keywords`. The `<meta name="author">` tag and Open Graph `article:author` property carry the same byline. A visible byline row (author, affiliation, publish date, read time) sits under the hero, and an "About the Author" panel near the foot of the page repeats the credential and links out to the author's and partners' sites. The two hub pages carry `CollectionPage` Schema.org markup with a `BreadcrumbList` instead, since they are index pages rather than authored articles.

Like the program pages, STRATCOM pages are reachable from the sitemap and from cross-links on their own pages; they are not yet in the site's main navigation (nav dropdown, mobile panel, footer columns).

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
