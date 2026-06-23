---
type: domain-moc
domain: glossary
status: template
tags: [moc, glossary]
---

# GLOSSARY — {{WORLD_NAME}} Entity Index & Spelling Authority

The A-to-Z lookup for every named entity in the canon, and the **spelling authority** for live play, the published wiki, and any prose set in this world. In an Obsidian vault you mostly don't *maintain* this by hand — Dataview builds it from the entity notes. What you maintain here is the **confusion table** (the part a query can't infer) and the provenance note.

## Provenance (this sets the trust level)

Entries are generated from the notes in `entities/`, which cite the primary sources. **This glossary is a navigation aid, not a primary source** — for anything load-bearing, open the entity note and follow its sources. It inherits each entity's `status`: a `provisional` entity yields a provisional line here. It does **not** override the canon-authority hierarchy in `[[CLAUDE]]`.

## The index (auto-built)

```dataview
TABLE WITHOUT ID file.link AS "Canonical name", entity_type AS "Type", aka AS "Aka / variants", status AS "Status"
FROM "entities"
WHERE type = "entity"
SORT file.name ASC
```

> Without Dataview this block shows as code. Either install the plugin, or keep a hand-written A–Z list below in the format:
> `**Canonical Term** *(type; not Misspelling; aka Alias)*. Definition. ↳ [[Entity Note]] · Sources: source.pdf.`

## Near-homophones and easy confusions (maintain this by hand)

The most dangerous failure in a growing world: one slip forks a single entity into two, or merges two into one. A query can't catch that — *you* record it here. Per `[[CLAUDE]]` §10, a misspelling/variant is an `aka` redirect to **one** canonical note, never its own note.

| Looks like / sounds like | These are actually… |
|---|---|
| {{Name-A}} / {{Name-B}} | **{{Name-A}}** = {{what it is}}. **{{Name-B}}** = {{the different thing}} — OR a misspelling of {{Name-A}} (record as `aka`, never a second note). |
| {{add rows as you discover collisions}} | |

## Conventions

- One **canonical title** per entity note; every other spelling goes in that note's `aliases:` (so it autocompletes) and `aka:` (so it's human-visible) — and, if dangerous, in the confusion table above.
- When a new named entity enters any domain during ingestion, it gets its own note in `entities/` the same session; it then appears here automatically.
