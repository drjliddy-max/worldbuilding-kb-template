---
type: domain-moc
domain: players
status: template
tags: [moc]
---

# PLAYERS — player characters

> Domain MOC (a *view*). Entity data lives in one note per entity under `entities/` with `domain: players`; this page aggregates them. Add a narrative overview and groupings; let Dataview list the rows. Delete this banner once populated.

## Overview

{{2–4 sentences orienting the reader to PLAYERS. Link the key entities and related domains with [[wikilinks]].}}

## All players entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "players"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "players" AND status != "canon"
SORT file.name ASC
```

## Open questions

See [[gaps]] for anything OPEN in this domain.
