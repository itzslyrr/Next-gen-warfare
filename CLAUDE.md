# CLAUDE.md — Next-gen-warfare Knowledge Base

## Prime Directive
**NON-SENSITIVE DATA ONLY.**

Every piece of content in this knowledge base must follow these rules:

1. **Public sources only** — all facts must come from openly published, encyclopedic sources (Wikipedia, official defense ministry press releases, reputable news outlets). Nothing classified, leaked, or restricted.
2. **No technical uplift** — never include design details, engineering schematics, guidance algorithms, propellant chemistry, or anything that could help someone build or improve a weapon. Specs are limited to headline figures already in the public record (range, speed class, length, operator, status).
3. **Educational framing** — this is a reference wiki for studying defense technology trends, not an operations manual.
4. **Cite sources** — every entry ends with a `Sources` section linking where the information came from.

## Structure & Conventions

```
Next-gen-warfare/
├── CLAUDE.md            ← you are here (AI instructions)
├── README.md            ← knowledge base index / entry point
├── inventory/           ← one file per missile system (kebab-case names)
├── classes/             ← one file per weapon category
├── armory/              ← one file per country/bloc arsenal overview
├── templates/           ← copy these to create new entries
├── assets/
│   ├── images/          ← photos (Wikimedia Commons, freely licensed)
│   └── infographics/    ← custom SVG charts
├── presentation/        ← HTML slide deck for presenting this project
└── .claude/skills/      ← AI skills (add-missile-entry)
```

- **File naming:** kebab-case, e.g. `rs-28-sarmat.md`
- **Every inventory entry** starts with a quick-facts table (Origin, Type, Range, Speed, Status, First deployed), then Overview, Why it matters, and Sources.
- **Cross-link** related entries with relative markdown links.
- **When adding a new missile:** use the `add-missile-entry` skill, or manually: copy `templates/inventory-entry.md`, fill it, then wire it into `inventory/index.md`, its class file, its armory file, and `README.md`.

## The Eight Moves

This vault is organized around eight knowledge-base moves. Follow all of them:

| Move | How it works here |
|---|---|
| **Vault** | This folder is one plain-text home, under git. Everything is markdown + assets — portable, diffable, greppable. |
| **Frontmatter** | Every page opens with YAML (`type`, `class`, `country`, `range_km`, `speed`, `status`, `tags`) — labels an AI can filter on ("list all in-service ICBMs over 12,000 km"). |
| **Wikilink** | `related:` frontmatter carries `[[wikilinks]]` between entries; body text uses relative markdown links. A connection the AI walks. |
| **Index** | `README.md` is the front door; `inventory/index.md` is the hub. Every new page gets wired into both. |
| **Template** | `templates/` holds the skeletons. New entries start from a template, never from a blank file — structure by default. |
| **Skill** | `.claude/skills/add-missile-entry/` teaches the AI the whole add-an-entry pipeline so it runs it consistently. |
| **CLAUDE.md** | This file. Standing rules — the non-sensitive-only policy travels with the vault. |
| **The doorway** | A human reviews every AI write before it's committed. The AI presents what changed; the human approves. |
