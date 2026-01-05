# tanwa.info Site Architecture

This document describes the structure, design decisions, and technical implementation of tanwa.info - the professional portfolio website for Asst. Prof. Tanwa Arpornthip, Ph.D.

## Overview

tanwa.info is a static HTML portfolio site designed to position Tanwa as a thought leader and implementation expert at the intersection of AI, Web3, and frontier technology. The site emphasizes quantified achievements and professional authority.

**Domain**: https://tanwa.info
**Hosting**: Render.com (static site)
**Base Template**: HTML5 UP

---

## Directory Structure

```
tanwa.info/
├── index.html              # Homepage - identity, ventures, contact
├── 404.html                # Custom error page
├── articles/               # Individual article pages
│   └── ai-transformation-scb10x.html
├── assets/
│   ├── css/
│   │   ├── main.css        # Legacy stylesheet (template)
│   │   └── fontawesome-all.min.css
│   ├── js/
│   │   ├── jquery.min.js   # jQuery 3.x
│   │   ├── jquery.scrolly.min.js  # Smooth scrolling
│   │   ├── browser.min.js  # Browser detection
│   │   ├── breakpoints.min.js  # Responsive breakpoints
│   │   ├── util.js         # Utility functions
│   │   └── main.js         # Site interactions (cursor, animations)
│   └── webfonts/           # Font Awesome icons
├── images/
│   └── og-image.jpg        # Open Graph social sharing image
├── specs/
│   └── personal_specs.md   # Design specifications
├── favicon.svg             # Vector favicon
├── manifest.json           # PWA manifest
├── render.yaml             # Deployment configuration
├── checklist.md            # Design bible
├── ARCHITECTURE.md         # This file
├── CLAUDE.md               # Claude Code project instructions
├── IMAGE_OPTIMIZATION.md   # Image optimization guidelines
└── README.md               # Quick start guide
```

**Note**: The site has evolved from the original HTML5 UP template to a custom minimal design with inline CSS in index.html.

---

## Page Architecture

### Homepage (index.html)

The homepage follows a minimal single-page design with section-based navigation:

| Section | Purpose |
|---------|---------|
| Header | Fixed nav: Tanwa. logo + VENTURES, SPEAKING, BLOG, CONTACT links |
| Hero | Title + tagline + credentials summary |
| Impact Numbers | Key metrics grid (฿85.3M, $700M, 400+, 5,000+) |
| Ventures | Company portfolio (Two Flamingos, Flamingo 492, Lumicello) |
| Speaking & Roles | Professional positions (SCB 10X, PSU Phuket, Redefine) |
| Contact Form | Formspree-powered contact form ("GET IN TOUCH") |
| Newsletter | Ghost-embedded signup ("FLIGHT NOTES") |
| Footer | Social links + location |

**Design Patterns**:
- Results-first presentation (metrics before descriptions)
- Minimal typography-focused design
- Custom cursor for engagement
- External blog link (Ghost at flight-notes.ghost.io)

### Articles (articles/*.html)

Long-form content pages with:
- Full-width reading experience
- Schema.org Article markup

---

## Design System

### Color Palette (Current - Minimal Design)

```css
--bg: #FAF9F7;                 /* Warm off-white background */
--text: #2E2E2E;               /* Dark charcoal text */
--accent: #E6524A;             /* Coral accent (CTAs, highlights) */
--accent-hover: #F77B72;       /* Lighter coral for hover states */
--secondary: #D7D7CF;          /* Muted gray for borders */
--gold: #E9A74B;               /* Gold for special accents */
```

### Typography

| Use | Font | Weight |
|-----|------|--------|
| Body/Headings | Manrope | 500, 700, 800 |
| Secondary | Inter | 400, 500 |

### Design Features

- **Custom Cursor**: Dot + outline cursor with hover effects
- **Minimal Layout**: Clean single-column sections
- **No Images**: Text-focused design with metrics emphasis
- **Responsive Grid**: CSS Grid for impact metrics

### Responsive Breakpoints

```css
--mobile: 320px;
--tablet: 768px;
--desktop: 1024px;
--wide: 1440px;
```

### Key CSS Classes

- `.intro` - Hero section styling
- `.feature-icons` - Icon + text metric cards
- `.gallery` - Grid layout for cards
- `.article-card` - Blog article styling
- `.button.primary` - CTA buttons
- `.box` - Contained content blocks

---

## Technical Stack

### Frontend Dependencies

| Library | Version | Purpose |
|---------|---------|---------|
| jQuery | 3.x | DOM manipulation, AJAX |
| jquery.scrolly | - | Smooth anchor scrolling |
| Font Awesome | 5.x | Icons |
| Google Fonts | - | Inter, Poppins |

### Build Process

The site uses pre-compiled CSS from SASS sources. The SASS structure:

```
sass/
├── main.scss           # Imports all partials
├── libs/               # Vendor mixins
├── base/               # Variables, reset, typography
├── components/         # UI components
└── layout/             # Page sections
```

**Note**: No build automation in repo - SASS is pre-compiled to `assets/css/main.css`

---

## SEO & Metadata

### Schema.org Markup

The site includes structured data for:
- **Person** (index.html) - Professional profile
- **Blog** (blog.html) - Blog listing
- **Article** (individual articles) - Blog posts

### Meta Tags

Each page includes:
- Standard meta (description, keywords, viewport)
- Open Graph (Facebook, LinkedIn sharing)
- Twitter Cards (Twitter sharing)
- Favicon + Apple touch icons
- PWA manifest

### SEO Files

| File | Purpose |
|------|---------|
| `robots.txt` | Crawler directives |
| `sitemap.xml` | URL listing for search engines |
| `manifest.json` | PWA configuration |

---

## Deployment (Render.com)

### Configuration (render.yaml)

```yaml
services:
  - type: web
    name: tanwa-info
    runtime: static
    staticPublishPath: .
    pullRequestPreviewsEnabled: true
```

### Security Headers

All paths receive:
- `X-Frame-Options: SAMEORIGIN`
- `X-Content-Type-Options: nosniff`
- `X-XSS-Protection: 1; mode=block`
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Strict-Transport-Security: max-age=31536000; includeSubDomains; preload`
- Content-Security-Policy (script-src, style-src, img-src, etc.)

### Custom Routes

- `/assets/**` - Static asset serving
- `/images/**` - Image serving
- 404 fallback to `/404.html`

---

## Content Strategy

### Brand Positioning

**Tagline**: "Builder of AI-driven financial and human-capability systems"

**Key Metrics** (displayed prominently):
- 85.3M THB value generated through AI
- $700M VC fund advisor
- 5,000+ summit attendees
- 500+ research citations

### Ventures Portfolio

1. **Two Flamingos Capital** - Algorithmic trading
2. **Flamingo 492** - Advisory & real estate
3. **Lumicello** - AI-powered learning
4. **Vector** - AI fitness systems

### Content Types

| Type | Location | Status |
|------|----------|--------|
| Homepage | index.html | Complete |
| Blog | External (flight-notes.ghost.io) | Active |
| Featured Article | articles/ai-transformation-scb10x.html | Complete |

---

## Design Decisions

### 1. Static Site Over SPA/SSG

**Decision**: Pure HTML/CSS/JS without build framework
**Rationale**:
- Maximum performance (no hydration delay)
- Simple deployment (no build step)
- Easy maintenance (edit HTML directly)
- SEO-friendly (content in HTML)

### 2. Design Evolution (HTML5 UP → Custom Minimal)

**Original**: Started from HTML5 UP template
**Current**: Complete redesign with custom minimal aesthetic

**Evolution Rationale**:
- Moved from dark theme to warm light background (#FAF9F7)
- Removed images in favor of typography-focused design
- Added custom cursor for interactive feel
- Simplified color palette to coral accent (#E6524A)
- External blog (Ghost) instead of built-in blog pages

### 3. Fixed Navigation

**Decision**: Sticky top nav with anchor links
**Rationale**:
- Single-page experience
- Easy section access
- Clear site structure

### 4. Results-First Content

**Decision**: Lead with metrics, follow with description
**Rationale**:
- Establishes credibility immediately
- Quantifiable achievements > vague claims
- Aligns with "implementation expert" positioning

### 5. Dual Color Theme

**Decision**: Light base (homepage) with dark accents (blog)
**Rationale**:
- Professional appearance for portfolio
- Better readability for long-form content
- Visual distinction between sections

---

## Maintenance Guide

### Adding New Articles

1. Create HTML file in `articles/`
2. Add entry to `blog.html` grid
3. Update `sitemap.xml`
4. Commit and push (Render auto-deploys)

### Updating Metrics

Key metrics appear in multiple locations:
- `index.html` lines 156-170 (Impact section)
- `blog.html` line 174, 318 (credentials)
- Meta descriptions in `<head>`

### Modifying Styles

1. Edit SASS files in `assets/sass/`
2. Compile to `assets/css/main.css`
3. Test locally before deploying

### Deployment

Push to `main` branch triggers automatic Render deployment. PR previews are enabled for testing.

---

## Performance Targets

| Metric | Target |
|--------|--------|
| First Contentful Paint | < 1.5s |
| Time to Interactive | < 3s |
| Lighthouse Score | > 90 |

### Optimization Strategies

- Minified CSS/JS
- WebP images (when added)
- Lazy loading for below-fold images
- Inline critical CSS (future)
- Service worker for offline (PWA manifest ready)

---

## External Services & Integrations

### Analytics (Umami)

Privacy-respecting, cookie-free analytics hosted at `analytics.lumicello.com`.

```html
<script defer src="https://analytics.lumicello.com/script.js"
        data-website-id="31a60b26-0f0a-4c7b-a871-ff8db375f6d2"></script>
```

**Features**:
- No cookies, GDPR compliant
- Self-hosted instance
- Tracks page views, referrers, devices

### Newsletter (Ghost)

Embedded signup form from Ghost blog at `flight-notes.ghost.io`.

```html
<script src="https://cdn.jsdelivr.net/ghost/signup-form@~0.3/umd/signup-form.min.js"
        data-site="https://flight-notes.ghost.io/" async></script>
```

**Features**:
- Weekly "Flight Notes" newsletter
- Managed through Ghost dashboard
- Automatic subscriber sync

### Contact Form (Formspree)

Server-side form handling via Formspree (form ID: `mgovrvqp`).

```html
<form action="https://formspree.io/f/mgovrvqp" method="POST">
```

**Features**:
- No backend required
- Spam filtering
- Email notifications to site owner

### CSP Configuration

Content Security Policy updated in `render.yaml` for external services:

| Service | Domains Allowed |
|---------|-----------------|
| Analytics | `analytics.lumicello.com` |
| Newsletter | `cdn.jsdelivr.net`, `flight-notes.ghost.io` |
| Contact Form | `formspree.io` |
| Fonts | `fonts.googleapis.com`, `fonts.gstatic.com` |

---

## Search Functionality (Pagefind)

The site uses [Pagefind](https://pagefind.app/) for client-side search - a lightweight, WebAssembly-powered search that runs entirely in the browser.

### How It Works

1. **Build time**: Pagefind indexes all HTML pages with `data-pagefind-body` attribute
2. **Runtime**: Search UI loads Pagefind JS lazily on first search interaction
3. **Fragments**: Results load incrementally (5-8KB per result) vs full index download

### Implementation

**Index Markers:**
- `data-pagefind-body` on main content sections (index.html, articles)
- `data-pagefind-ignore` on non-searchable content (marquee, footer)

**Build Command:**
```bash
npx pagefind --site . --output-path pagefind
```

**CSP Requirement:**
Pagefind uses WebAssembly, requiring `wasm-unsafe-eval` in Content-Security-Policy.

### Search UI

- Triggered by search icon in header or `Cmd/Ctrl+K` keyboard shortcut
- Modal overlay with instant search results
- Shows title and excerpt with highlighted matches

### Files

| Path | Purpose |
|------|---------|
| `/pagefind/` | Generated search index (gitignored) |
| `pagefind.js` | Main search library |
| `wasm.*.pagefind` | WebAssembly search engine |
| `fragment/` | Content fragments for results |

---

## Future Considerations

1. **Article CMS**: Consider headless CMS for content management
2. **Image Optimization**: Implement responsive images with srcset

---

*Last updated: January 5, 2026*
