---
type: moc
status: template
tags: [moc, home]
---

# {{WORLD_NAME}} — Home

The master **Map of Content** for the world of **{{WORLD_NAME}}**. Start here. Open this folder as an [Obsidian](https://obsidian.md) vault and enable the **Dataview** plugin so the queries below render as live tables.

> New here? Read `[[CLAUDE]]` (the rules) and `[[README]]` (the quick start) first. The rules are the whole point — they're what make this canon trustworthy enough to publish.

## Domains (the views)

- `[[COSMOLOGY]]` — planes, divine architecture, metaphysics
- `[[PANTHEON]]` — gods and divine politics
- `[[HISTORY]]` — timeline and major events
- `[[GEOGRAPHY]]` — regions, cities, locations
- `[[FACTIONS]]` — orders, governments, organizations
- `[[CHARACTERS]]` — major NPCs
- `[[PLAYERS]]` — player characters
- `[[MAGIC]]` — magic systems
- `[[ARTIFACTS]]` — items and relics
- `[[CREATURES]]` — monsters, races, beings
- `[[PROPHECIES]]` — prophecies and foretellings
- `[[CURRENT_EVENTS]]` — the campaign present
- `[[GLOSSARY]]` — A–Z entity index + spelling authority

## Discipline dashboards (live queries)

These turn the Hard Rules in `[[CLAUDE]]` into things you can *see*. They require the Dataview plugin.

### Everything not yet verified (Rule §6 — provisional content)

```dataview
TABLE entity_type AS "Type", domain AS "Domain", status AS "Status"
FROM "entities"
WHERE status != "canon"
SORT status ASC, file.name ASC
```

### Entities missing sources (Rule §3 — source citation mandatory)

```dataview
TABLE entity_type AS "Type", status AS "Status"
FROM "entities"
WHERE !sources OR length(sources) = 0
SORT file.name ASC
```

### Open conflicts & questions (Rule §4 — flag, don't guess)

```dataview
TABLE WITHOUT ID file.link AS "Item", status AS "Status", glossary AS "Glossary key"
FROM "gaps"
WHERE type = "gap" AND status = "OPEN"
SORT file.name ASC
```
<!-- If you keep gaps as one file with sub-items rather than one note per gap,
     just read gaps.md directly. The query above assumes one-note-per-gap in a gaps/ folder. -->

### Entity count by domain (is the world filling in?)

```dataview
TABLE length(rows) AS "Entities"
FROM "entities"
WHERE type = "entity"
GROUP BY domain
SORT length(rows) DESC
```

## Source material & ingestion

- `[[INDEX]]` — catalog of every raw source file, topic-tagged
- `[[gaps]]` — the open-conflicts ledger
- `notes/ingestion-tracker/` — read-pass logs (what you read, what conflicted)
- `external/` — drop-zone for AI exports to ingest

## Publishing (player-facing)

- `notes/canon/index.html` — the publishable hub
- `notes/canon/canon.css` — the shared theme
- See `[[README]]` → *Publishing for players*. (Obsidian's own **Publish** service is an alternative to the static HTML — see `[[CLAUDE]]`.)
