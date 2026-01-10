---
name: check-blacklist
description: Checks that no blacklisted items appear on the tanwa.info website. Use before deploying or when verifying content compliance.
allowed-tools: Read, Grep, Glob
---

# Check Blacklist Skill

## Overview

This skill verifies that the tanwa.info website does not contain any blacklisted content. Blacklisted items are tracked in `BLACKLIST.md` at the project root.

## Instructions

When this skill is invoked:

1. **Read the blacklist**: Parse `BLACKLIST.md` to extract all blacklisted items from the table
2. **Scan website files**: Search for each blacklisted item (case-insensitive) in:
   - `index.html`
   - `404.html` (if exists)
   - Any other `.html` files in the project root
3. **Report findings**:
   - If violations found: List each with file path and line number
   - If clean: Confirm compliance

## Output Format

### Clean (no violations)
```
Checking website against blacklist...

Blacklisted items:
- WikiExpo
- WikiExpo 2024

Scanning HTML files...
✓ index.html - clean
✓ 404.html - clean

✅ No blacklisted items found. Website is compliant.
```

### Violations found
```
Checking website against blacklist...

Blacklisted items:
- WikiExpo
- WikiExpo 2024

Scanning HTML files...

⚠️ VIOLATIONS FOUND:

index.html:418: Contains "WikiExpo 2024 Award Winner"
index.html:43: Contains "WikiExpo 2024 - Most Influential"

❌ Fix these violations before deploying!
```

## When to use this skill

- Before deploying to production
- After making content updates
- During code review
- When adding new content to verify compliance

## Related files

- `BLACKLIST.md` - Source of truth for blacklisted items
- `index.html` - Main website page
- `404.html` - Error page
