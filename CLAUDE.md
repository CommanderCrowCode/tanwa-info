# tanwa.info Project Instructions

> **Recovery**: Run `bd onboard` after clear or new session

## Project Overview

**tanwa.info** is a static portfolio website for Asst. Prof. Tanwa Arpornthip, Ph.D.

- **Domain**: https://tanwa.info
- **Hosting**: Render.com (static site, auto-deploys on push to main)
- **Stack**: Pure HTML/CSS/JS (no build step)

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Homepage - identity and expertise |
| `blog.html` | Blog listing page |
| `articles/*.html` | Individual article pages |
| `assets/css/main.css` | Compiled CSS (from SASS) |
| `assets/sass/` | SASS source files |
| `checklist.md` | Design Bible - brand guidelines |
| `ARCHITECTURE.md` | Technical architecture reference |

## Design Guidelines

Follow the **Design Bible** in `checklist.md`. Key principles:

1. **Authority First**: Lead with credentials ("Asst. Prof.", "Ph.D.") and metrics
2. **Results Over Rhetoric**: Quantify everything (85.3M THB, $700M, etc.)
3. **Professional Appearance**: Dark theme with quantum-purple accents (#8a2be2)
4. **Progressive Disclosure**: Summary → Details → Deep Dive

## Development Workflow

### Making Changes

1. Edit HTML files directly (no build step for HTML)
2. For style changes, edit SASS then compile to `assets/css/main.css`
3. Test locally before committing
4. Push to `main` triggers auto-deploy on Render

### Adding New Articles

1. Create HTML file in `articles/`
2. Add entry to `blog.html` grid
3. Update `sitemap.xml`
4. Include proper Schema.org Article markup

### Updating Metrics

Key metrics appear in multiple locations - update consistently:
- `index.html` (Impact section)
- `blog.html` (credentials in header/sidebar)
- `<meta>` descriptions

## SEO Checklist

When adding/modifying pages:
- [ ] Meta title and description
- [ ] Open Graph tags (og:title, og:description, og:image)
- [ ] Twitter Card tags
- [ ] Schema.org structured data
- [ ] Update sitemap.xml

## Session End Checklist

```
[ ] git status              (check what changed)
[ ] git add <files>         (stage changes)
[ ] bd sync                 (commit beads changes)
[ ] git commit -m "..."     (commit code)
[ ] bd sync                 (commit any new beads)
[ ] git push                (push to remote - MANDATORY)
```

Work is NOT complete until `git push` succeeds.
