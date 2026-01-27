# tanwa.info

Professional portfolio site for Asst. Prof. Tanwa Arpornthip, Ph.D.

**Live**: https://tanwa.info

## Quick Start

```bash
# Local development
python -m http.server 8999
# Access at http://localhost:8999
```

## Overview

Static HTML portfolio showcasing expertise at the intersection of AI, fintech, and venture capital. Features a minimal, typography-focused design with custom cursor interactions.

- **Hosting**: Render.com (auto-deploys on push to `main`)
- **Dev Port**: 8999

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Homepage - hero, about, metrics, ventures, roles, contact |
| `404.html` | Custom error page |
| `ARCHITECTURE.md` | Full technical documentation |
| `checklist.md` | Design bible and specifications |
| `BLACKLIST.md` | Content/design items to avoid |
| `render.yaml` | Render.com deployment config |

## Directory Structure

```
tanwa.info/
├── index.html              # Main page
├── 404.html                # Error page
├── articles/               # Case studies
│   └── ai-transformation-scb10x.html
├── assets/
│   ├── css/main.css        # Compiled styles (legacy)
│   ├── js/                 # JavaScript
│   ├── sass/               # SASS sources
│   └── webfonts/           # Font Awesome icons
├── images/
│   └── og-image.jpg        # Open Graph social image
├── research/               # Content research and sources
├── specs/                  # Design specifications
├── robots.txt              # Crawler directives
└── sitemap.xml             # SEO sitemap
```

## Design System

**Current Color Palette** (inline CSS in index.html):
- Background: `#FAF9F7` (warm off-white)
- Text: `#2E2E2E` (dark charcoal)
- Accent: `#E6524A` (coral)
- Accent hover: `#F77B72`
- Secondary: `#D7D7CF` (muted gray)
- Gold: `#E9A74B` (special accents)

**Fonts**:
- Primary: Manrope (500, 700, 800)
- Secondary: Inter (400, 500)

## Page Sections

| Section ID | Content |
|------------|---------|
| Hero | Title + tagline + credentials |
| About | Personal narrative (physics → VC journey) |
| Metrics Bar | Key numbers (Value Generated, VC Fund, Citations, Years Research) |
| `#ventures` | Company portfolio (Two Flamingos, Flamingo 492, Lumicello) |
| `#speaking` | Professional roles (SCB 10X, PSU Phuket, Redefine) |
| `#engagements` | Speaking events |
| Contact | Formspree-powered form ("GET IN TOUCH") |
| Newsletter | Ghost-embedded signup ("FLIGHT NOTES") |

## External Services

| Service | Purpose | Details |
|---------|---------|---------|
| Formspree | Contact form | form ID: `mgovrvqp` |
| Ghost | Blog/Newsletter | flight-notes.ghost.io |
| Umami | Analytics | analytics.lumicello.com |
| Web Vitals | Performance monitoring | Real-user metrics (LCP, INP, CLS, FCP, TTFB) → Umami |

### Analytics & Performance

**Umami Dashboard**: Access at `analytics.lumicello.com` to view:
- Page views, referrers, devices
- Custom events: `web-vitals-*` (performance metrics)
- Custom events: `js-error`, `promise-rejection` (error tracking)

**Tracked Performance Metrics**:
- **LCP** (Largest Contentful Paint) - Loading performance
- **INP** (Interaction to Next Paint) - Interactivity
- **CLS** (Cumulative Layout Shift) - Visual stability
- **FCP** (First Contentful Paint) - Initial render
- **TTFB** (Time to First Byte) - Server response

## Deployment

Push to `main` triggers automatic Render deployment. PR previews are enabled.

## Reference Docs

- `ARCHITECTURE.md` - Complete technical documentation
- `checklist.md` - Design specifications (source of truth)
- `specs/personal_specs.md` - Personal branding guidelines
- `research/positioning-strategy.md` - Strategic positioning guide
