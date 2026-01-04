# tanwa.info Content Research

> **Purpose**: Gather accurate, compelling content for tanwa.info from public sources

## Status

| Source | Bead | Status | File |
|--------|------|--------|------|
| LinkedIn | ti-9hb | pending | `sources/linkedin.md` |
| Google Scholar | ti-w8y | pending | `sources/scholar.md` |
| GitHub | ti-wdg | pending | `sources/github.md` |
| Ghost Newsletter | ti-h9b | pending | `sources/newsletter.md` |
| Ventures & Roles | ti-0jt | pending | `sources/ventures.md` |
| Web Search | ti-7zc | pending | `sources/web-search.md` |
| **Compile Brief** | ti-4vx | blocked | `CONTENT_BRIEF.md` |
| **Implement** | ti-hvv | blocked | - |

## Methodology

### Research Principles
1. **Public sources only** - No private/confidential information
2. **Verify claims** - Cross-reference metrics across sources
3. **Cite sources** - Every fact links to its origin
4. **Respect privacy** - Don't include personal details not already public

### Data Extraction Format

Each source file follows this structure:
```markdown
# [Source Name]

**URL**: [link]
**Accessed**: [date]

## Raw Findings
[Extracted content organized by category]

## Key Facts
- Fact 1 (verified/unverified)
- Fact 2 (verified/unverified)

## Content Opportunities
[How this could be used on the site]
```

### Profile Data Schema

`profile-data.yaml` uses this structure:
```yaml
identity:
  name: "Tanwa Arpornthip"
  title: ""
  credentials: []

metrics:
  - label: ""
    value: ""
    source: ""
    verified: false

experience:
  - role: ""
    org: ""
    period: ""
    description: ""

publications:
  - title: ""
    venue: ""
    year: ""
    citations: 0

ventures:
  - name: ""
    description: ""
    url: ""
    role: ""
```

## Output

Final deliverable: `CONTENT_BRIEF.md`
- Proposed hero text
- About section copy
- Venture descriptions
- Speaking topics
- Any new sections to add

**Requires user approval before implementation.**

## Directory Structure

```
research/
├── README.md              # This file
├── sources/
│   ├── linkedin.md
│   ├── scholar.md
│   ├── github.md
│   ├── newsletter.md
│   ├── ventures.md
│   └── web-search.md
├── profile-data.yaml      # Structured data
└── CONTENT_BRIEF.md       # Final approved content
```
