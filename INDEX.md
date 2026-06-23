---
type: source-index
status: template
tags: [moc, sources]
---

# {{WORLD_NAME}} Source File Index

Topic-tagged catalog of every file in `{{SOURCE_ROOT}}`. Use this to find source material when `knowledge/*.md` doesn't already have what you need. This is a **map of your raw documents**, not the canon itself — the canon lives in `knowledge/`.

## Conventions

- Paths are relative to `{{SOURCE_ROOT}}` unless absolute.
- Format hints in brackets: `[PDF]` `[Pages]` `[Numbers]` `[DOCX]` `[RTF]` `[CSV]` `[XML]` `[IMG]` `[MAP]` `[EPUB]`.
- **Topic tags** (adapt to your world): `#world` `#cosmos` `#magic` `#pantheon` `#history` `#geography` `#faction` `#npc` `#pc` `#creature` `#prophecy` `#politics` `#war` `#artifact` `#location` `#calendar` `#trade` `#current` `#map` `#image` `#sheet` `#ref` `#book`
- `★` marks priority / canonical-authority reading.

---

## Top-level reference

| Path | Topics | Notes |
|---|---|---|
| `{{your-master-index.pdf}}` ★ | `#world #ref` | {{e.g. the GM's own table of contents — read first}} |
| `{{world-definition.pdf}}` ★ | `#world` | {{the latest, authoritative world-overview doc}} |
| `{{state-of-record-doc}}` ★ | `#calendar #current` | {{your state-of-record source — wins on dated/state questions per CLAUDE.md §2}} |

<!-- Add a section per source-folder. Keep the same table shape. Example grouping below. -->

## {{Source folder name}} (e.g. "Lore / world-defining docs") ★★★

| Path | Topics | Notes |
|---|---|---|
| `{{path/to/file.pdf}}` ★ | `#cosmos #magic` | {{one-line note}} |
| `{{path/to/file.pages}}` | `#history` | {{source of the above / variant}} |

## {{Source folder name}} (e.g. "Characters")

| Path | Topics | Notes |
|---|---|---|
| `{{path/to/file.pdf}}` | `#npc` | {{one-line note}} |

---

## How to maintain this index

- When you add a source to `{{SOURCE_ROOT}}`, add a row here with its topic tags.
- When a source introduces a new named entity, tag it and add a stub to `GLOSSARY.md` + the relevant domain file.
- Tag generously — the index earns its keep when you can grep `#prophecy` and find every relevant doc at once.
