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
├── index.html              # Homepage - identity and expertise
├── blog.html               # Blog listing page
├── 404.html                # Custom error page
├── articles/               # Individual article pages
│   └── ai-transformation-scb10x.html
├── assets/
│   ├── css/
│   │   ├── main.css        # Compiled stylesheet
│   │   └── fontawesome-all.min.css
│   ├── js/
│   │   ├── jquery.min.js   # jQuery 3.x
│   │   ├── jquery.scrolly.min.js  # Smooth scrolling
│   │   ├── browser.min.js  # Browser detection
│   │   ├── breakpoints.min.js  # Responsive breakpoints
│   │   ├── util.js         # Utility functions
│   │   └── main.js         # Site interactions
│   ├── sass/               # SASS source files
│   │   ├── main.scss       # Main entry point
│   │   ├── base/           # Reset, typography
│   │   ├── components/     # Buttons, forms, etc.
│   │   ├── layout/         # Page layouts
│   │   └── libs/           # Third-party SASS
│   └── webfonts/           # Font Awesome icons
├── images/
│   ├── gallery/            # Gallery images
│   ├── pic01.jpg, pic02.jpg
│   ├── first.png, second.png
├── specs/
│   └── personal_specs.md   # Design specifications
├── favicon.svg             # Vector favicon
├── manifest.json           # PWA manifest
├── robots.txt              # Search crawler rules
├── sitemap.xml             # SEO sitemap
├── render.yaml             # Deployment configuration
└── checklist.md            # Design bible
```

---

## Page Architecture

### Homepage (index.html)

The homepage follows a single-page application pattern with section-based navigation:

| Section | ID | Purpose |
|---------|-----|---------|
| Navigation | `#main-nav` | Fixed top nav with anchor links |
| Hero | `.intro` | Identity statement + CTAs |
| Impact Numbers | `#impact` | Key metrics (85.3M, $700M, etc.) |
| Core Expertise | `#expertise` | AI, Web3, Quantum capabilities |
| Ventures | `#ventures` | Company portfolio |
| Current Roles | `#roles` | Professional positions |
| Speaking | `#speaking` | Recent engagements |
| Case Studies | `#cases` | Implementation examples |
| Services | `#services` | Consulting offerings |
| Publications | `#publications` | Academic citations |
| Contact | `#contact` | CTA and contact info |
| Footer | N/A | Social links + copyright |

**Design Patterns**:
- Results-first presentation (metrics before descriptions)
- Progressive disclosure (summary → details)
- Authority anchors (credentials always visible)

### Blog (blog.html)

- Compact header with credentials
- Featured article banner
- Article grid (3-column responsive)
- Sidebar with topics, popular posts, newsletter
- Article series section

**Custom Styles**: Uses `blog-focus` body class for:
- Narrower left sidebar (24vw vs default)
- Wider content area
- Custom article card styling

### Articles (articles/*.html)

Long-form content pages with:
- Full-width reading experience
- Author bio sidebar
- Related articles
- Schema.org Article markup

---

## Design System

### Color Palette

```css
--quantum-purple: #8a2be2;     /* Primary accent */
--midnight-depth: #0a0e27;     /* Deep backgrounds */
--trust-navy: #1a237e;         /* Secondary accent */
--success-green: #00c853;      /* Metrics, achievements */
--caution-amber: #ff6f00;      /* Warnings */
--neutral-silver: #b0bec5;     /* Body text */
--pure-white: #ffffff;         /* Headlines, CTAs */
--theme-color: #f56a6a;        /* Theme accent (from template) */
```

### Typography

| Use | Font | Weight |
|-----|------|--------|
| Body | Inter | 300, 400, 600, 700 |
| Headings | Poppins | 600, 700 |
| Code | JetBrains Mono | - |

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
| Blog Index | blog.html | Complete |
| Featured Article | articles/ai-transformation-scb10x.html | Complete |
| Placeholder Articles | Linked from blog | Not created |

---

## Design Decisions

### 1. Static Site Over SPA/SSG

**Decision**: Pure HTML/CSS/JS without build framework
**Rationale**:
- Maximum performance (no hydration delay)
- Simple deployment (no build step)
- Easy maintenance (edit HTML directly)
- SEO-friendly (content in HTML)

### 2. HTML5 UP Base Template

**Decision**: Started from HTML5 UP template, heavily customized
**Rationale**:
- Proven responsive design patterns
- Cross-browser compatibility
- Accessible foundation
- Faster initial development

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

## Future Considerations

1. **Search Functionality**: Static search (Lunr.js/Pagefind)
2. **Article CMS**: Consider headless CMS for content management
3. **Image Optimization**: Implement responsive images with srcset

---

*Last updated: January 2026*
