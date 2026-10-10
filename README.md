# AerOps

The official website for **AerOps** — an early-stage aviation operations and technology studio building supply-chain analytics, spare-parts tracking and operational tools for narrowbody fleets.

**Live:** [aerops.space](https://aerops.space)
**Contact:** [devresources@aerops.space](mailto:devresources@aerops.space)

---

## Overview

A single-page, static website built with vanilla HTML, CSS and JavaScript. No build step, no dependencies, no backend. Open `index.html` in any browser and the site runs.

The site uses hash-based routing to serve five views (Home, Solutions, About, Contact, Privacy) from one file, with per-route `<title>` and meta-description updates.

## Project Structure

```
.
├── index.html      Main site file — markup, styles, scripts, and inline SVG
├── CNAME           Custom domain declaration for GitHub Pages
├── .gitignore      Local artefact exclusions
└── README.md       This file
```

## Configuration

All content that changes often is centralised in a `CONFIG` object at the bottom of `index.html`. Edit values there and the entire site updates on next load.

| Key | Purpose |
|-----|---------|
| `CONFIG.email` | Business email used in contact form, footer, privacy policy and all `mailto:` links |
| `CONFIG.domain` | Public domain displayed in footer and contact section |
| `CONFIG.updatedDate` | Last-revised date shown on the Privacy page |
| `CONFIG.tiers` | Status badge labels and descriptions (`LIVE`, `PROTOTYPE`, `CONCEPT`) |
| `CONFIG.team` | Founding team members — name, title, bio, email and LinkedIn |
| `CONFIG.solutions` | Three solution areas with their capabilities and per-capability status |

## Status System

Every capability carries one of three statuses, applied consistently across the site:

- **LIVE** — working and usable today
- **PROTOTYPE** — functional early version, in internal testing
- **CONCEPT** — planned or being explored

Promote a capability by changing its `status` string in `CONFIG.solutions`. All badges, legend entries and the "Status at a glance" table update automatically.

## Deployment

The site deploys unchanged to any static host.

### GitHub Pages

1. Push this repository to GitHub
2. In the repository settings, open **Pages**
3. Under *Source*, select the `main` branch and `/ (root)` folder
4. Save; the site will be served from `https://<user>.github.io/<repo>`
5. The included `CNAME` file maps the site to `aerops.space`; configure DNS records with your registrar accordingly

### Cloudflare Pages

1. In the Cloudflare dashboard, open **Pages** and connect this repository
2. Framework preset: *None*; build command: *(leave blank)*; output directory: `/`
3. Add `aerops.space` and `www.aerops.space` as custom domains
4. SSL is provisioned automatically

### Other hosts

Netlify, Vercel, Firebase Hosting, S3 + CloudFront, or any traditional web server will serve the site without modification. Point the host at the repository root.

## Local Development

No tooling is required. Open `index.html` directly in a browser, or serve the directory locally:

```bash
python3 -m http.server 8080
# or
npx serve .
```

Then visit `http://localhost:8080`.

## Accessibility

- Semantic HTML with a logical heading order
- Visible focus states on all interactive elements
- Skip-to-content link for keyboard users
- Hamburger menu with `aria-expanded` and `aria-controls`
- Form fields with associated labels and inline error messages
- Colour palette tested for WCAG AA contrast against the dark background
- `prefers-reduced-motion` honoured

## Browser Support

Verified in current versions of Chrome, Safari, Firefox and Edge, including mobile Safari and Chrome on Android. Minimum supported viewport width: 320 px.

## Privacy

The site has no backend, database or analytics. The contact form validates input locally and opens the visitor's own email client via a pre-filled `mailto:` link; no data is submitted or stored. External fonts are loaded from Google Fonts.

See the Privacy page on the live site for the full policy.

## Pre-Deployment Checklist

Before publishing to production:

1. Confirm `CONFIG.email` is the final production address
2. Review and promote `CONFIG.solutions` statuses as capabilities ship
3. Update `CONFIG.updatedDate` whenever the Privacy policy changes
4. Review the Privacy policy with counsel appropriate to your jurisdiction
5. Verify DNS A/CNAME records resolve to the chosen host
6. Confirm SSL certificate provisioning on the custom domain

## Licence

Proprietary. All rights reserved © 2026 AerOps.

## Contact

For questions about this repository or the project:
[devresources@aerops.space](mailto:devresources@aerops.space)
