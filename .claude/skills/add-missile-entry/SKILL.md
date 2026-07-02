---
name: add-missile-entry
description: Add a new missile system to the Next-gen-warfare knowledge base following its rules and conventions. Use when the user asks to add, profile, or document a missile/weapon system in this vault.
---

# Add Missile Entry

Add one missile system to the knowledge base, end to end.

## Steps

1. **Read the rules first:** `CLAUDE.md` at the vault root. Non-sensitive, public data only; cite sources.
2. **Copy the template:** `templates/inventory-entry.md` → `inventory/<kebab-name>.md`. Fill every `{{placeholder}}` including the YAML frontmatter (title, class, country, range_km, speed, status, tags, related wikilinks).
3. **Fetch a photo (optional):** query the Wikipedia REST summary API for a freely-licensed thumbnail:
   `https://en.wikipedia.org/api/rest_v1/page/summary/<Article_Title>` → download `thumbnail.source` (bump the `NNNpx` in the URL for higher resolution) to `assets/images/<kebab-name>.jpg`. Skip if no free image exists (e.g., North Korean systems).
4. **Wire it into the vault (the Index move):**
   - Add a row to the matching table in `inventory/index.md`
   - Reference it from its class file in `classes/`
   - Add it to the country's table in `armory/`
   - If it's a headline system, consider the featured table in `README.md`
5. **Update infographics if warranted:** if the system's range or speed is chart-worthy, add a bar to `assets/infographics/range-comparison.svg` / `speed-comparison.svg` (hand-edit the SVG; scale is noted in comments).
6. **The doorway:** present a summary of what was added and where, so the human can review before committing.
