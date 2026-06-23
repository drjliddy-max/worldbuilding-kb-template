---
type: domain-moc
domain: sheets
status: template
tags: [moc]
---

# CHARACTER_SHEETS — index of which characters have stat sheets and where they live

> Domain MOC (a *view*). Entity data lives in one note per entity under `entities/` with `domain: sheets`; this page aggregates them. Add a narrative overview and groupings; let Dataview list the rows. Delete this banner once populated.

## Overview

{{2–4 sentences orienting the reader to CHARACTER_SHEETS. Link the key entities and related domains with [[wikilinks]].}}

## All sheets entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "sheets"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "sheets" AND status != "canon"
SORT file.name ASC
```

## Open questions

See [[gaps]] for anything OPEN in this domain.
