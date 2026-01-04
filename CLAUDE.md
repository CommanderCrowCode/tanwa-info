# tanwa.info Project Instructions

Static HTML portfolio site for Asst. Prof. Tanwa Arpornthip, Ph.D.

## Quick Start

```bash
# Local development
uv run python -m http.server 8999

# Access at http://localhost:8999
```

## Project Overview

- **Domain**: https://tanwa.info
- **Hosting**: Render.com (static site)
- **Base Template**: HTML5 UP (heavily customized)
- **Dev Port**: 8999

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Homepage - identity, expertise, ventures |
| `404.html` | Custom error page |
| `ARCHITECTURE.md` | Detailed site structure documentation |
| `checklist.md` | Design specifications and guidelines |
| `render.yaml` | Render.com deployment config |

## Directory Structure

```
├── index.html              # Main page
├── 404.html                # Error page
├── articles/               # Blog articles (if created)
├── assets/
│   ├── css/main.css        # Compiled styles
│   ├── js/                 # JavaScript
│   └── sass/               # SASS sources
├── images/                 # Site images
└── specs/                  # Design specs
```

## Design System

**Color Palette**:
- Coral accent: `#f56a6a`
- Light background: `#ffffff`
- Dark text: `#333333`

**Fonts**:
- Body: Inter
- Headings: Poppins

## Making Changes

### Adding Content
1. Edit HTML files directly
2. Test locally with `python -m http.server 8999`
3. Commit and push (Render auto-deploys)

### Modifying Styles
1. Edit SASS in `assets/sass/`
2. Compile to `assets/css/main.css`
3. Test before deploying

### Key Sections in index.html
- Hero (`.intro`)
- Impact Numbers (`#impact`)
- Core Expertise (`#expertise`)
- Ventures (`#ventures`)
- Contact (`#contact`)

## Deployment

Push to `main` triggers automatic Render deployment. PR previews are enabled.

## External Services

- **Blog**: Linked to external Ghost blog at flight-notes.ghost.io
- **Contact**: mailto: links (no form backend)

## Reference Docs

- `ARCHITECTURE.md` - Full technical documentation
- `checklist.md` - Design bible and specifications
- `specs/personal_specs.md` - Personal branding guidelines
