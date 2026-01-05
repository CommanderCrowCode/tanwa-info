# tanwa.info BLACKLIST

Things to avoid in this project. Extracted from the design bible (checklist.md) and project experience.

## Design Don'ts

- Cluttered layouts without breathing room
- Generic corporate stock photography
- Vague value propositions ("innovative solutions")
- Multiple font families beyond Manrope + Inter
- Bright/unprofessional colors
- Centered body text (left-align for readability)
- Auto-playing videos or music
- Pop-ups on first visit
- Dark themes (site has evolved to light minimal aesthetic)

## Content Don'ts

- "Innovative solutions" (meaningless)
- "Cutting-edge" without proof
- Long paragraphs without breaks
- Technical jargon without context
- Claims without metrics

## Technical Don'ts

- Heavy JavaScript frameworks (site is pure HTML/CSS/JS)
- Build tools requiring npm/webpack (keep simple)
- Image-heavy layouts (current design is text-focused)
- External dependencies beyond essentials (fonts, analytics, form handler)
- Breaking the custom cursor experience

## Theme Constraints

- DO NOT revert to dark purple theme
- DO NOT use `#8a2be2` (quantum purple) - this is deprecated
- DO NOT use `#0a0e27` (midnight depth) - this is deprecated
- KEEP coral accent `#E6524A` as primary brand color
- KEEP warm off-white `#FAF9F7` as background

## Typography Constraints

- DO NOT introduce Poppins (removed in redesign)
- DO NOT use decorative fonts
- KEEP Manrope for headings/body
- KEEP Inter for secondary elements (nav, labels)

## External Services - Approved Only

| Service | Purpose | Status |
|---------|---------|--------|
| Formspree | Contact form | Approved |
| Ghost | Newsletter + Blog | Approved |
| Umami | Analytics | Approved |
| Google Fonts | Typography | Approved |

DO NOT add new external services without explicit approval.

---

*This blacklist protects design consistency. When in doubt, refer to checklist.md (design bible).*
