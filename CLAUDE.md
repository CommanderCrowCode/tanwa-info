# tanwa.info Project Instructions

Static HTML portfolio site for Asst. Prof. Tanwa Arpornthip, Ph.D.

## Quick Start

```bash
# Local development
python -m http.server 8999

# Access at http://localhost:8999
```

## Project Overview

- **Domain**: https://tanwa.info
- **Hosting**: Render.com (static site)
- **Design**: Custom minimal design (evolved from HTML5 UP template)
- **Dev Port**: 8999

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Homepage - hero, metrics, ventures, roles, contact |
| `404.html` | Custom error page |
| `ARCHITECTURE.md` | Detailed site structure documentation |
| `checklist.md` | Design specifications and guidelines (source of truth) |
| `BLACKLIST.md` | Content/design items to avoid |
| `render.yaml` | Render.com deployment config |

## Directory Structure

```
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

**Color Palette** (inline CSS in index.html):
- Background: `#FAF9F7` (warm off-white)
- Text: `#2E2E2E` (dark charcoal)
- Accent: `#E6524A` (coral)
- Accent hover: `#F77B72`
- Secondary: `#D7D7CF` (muted gray)
- Gold: `#E9A74B` (special accents)

**Fonts**:
- Primary: Manrope (500, 700, 800)
- Secondary: Inter (400, 500)

## Making Changes

### Adding Content
1. Edit HTML files directly
2. Test locally with `python -m http.server 8999`
3. Commit and push (Render auto-deploys)

### Modifying Styles
Current design uses inline CSS in index.html. Legacy SASS files exist in `assets/sass/` but the site has evolved to custom inline styles.

### Key Sections in index.html
- Hero statement (title + tagline)
- Metrics bar (value generated, VC fund, citations, attendees)
- Ventures (`#ventures`)
- Roles (`#speaking`)
- Speaking Engagements (`#engagements`)
- Contact form (Formspree)
- Newsletter (Ghost embed)

## Deployment

Push to `main` triggers automatic Render deployment. PR previews are enabled.

## External Services

| Service | Purpose | Details |
|---------|---------|---------|
| Formspree | Contact form | form ID: `mgovrvqp` |
| Ghost | Blog/Newsletter | flight-notes.ghost.io |
| Umami | Analytics | analytics.lumicello.com |

## Reference Docs

- `ARCHITECTURE.md` - Full technical documentation
- `checklist.md` - Design bible and specifications
- `specs/personal_specs.md` - Personal branding guidelines
