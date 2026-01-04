# check-blacklist

Check that no blacklisted items appear on the tanwa.info website.

## Instructions

1. Read `BLACKLIST.md` to get the list of blacklisted items from the table
2. Search `index.html` for each blacklisted item (case-insensitive)
3. Also check `404.html` if it exists
4. Report findings:
   - If violations found: List each violation with file and line number
   - If clean: Confirm "No blacklisted items found on website"

## Example Output

```
Checking website against blacklist...

Blacklisted items:
- WikiExpo
- WikiExpo 2024

Scanning index.html...
Scanning 404.html...

✓ No blacklisted items found on website
```

Or if violations:

```
Checking website against blacklist...

⚠️ VIOLATIONS FOUND:

index.html:418: "WikiExpo 2024 Award Winner"
index.html:43: "WikiExpo 2024 - Most Influential"

Fix these before deploying!
```
