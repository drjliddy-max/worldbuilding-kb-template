---
type: domain-moc
domain: geography
status: template
tags: [moc]
---

# GEOGRAPHY — regions, cities, and locations of {{REGION}}

> Domain MOC (a *view*). Entity data lives in one note per entity under `entities/` with `domain: geography`; this page aggregates them. Add a narrative overview and groupings; let Dataview list the rows. Delete this banner once populated.

## Overview

{{2–4 sentences orienting the reader to GEOGRAPHY. Link the key entities and related domains with [[wikilinks]].}}

## All geography entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "geography"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "geography" AND status != "canon"
SORT file.name ASC
```

## Open questions

See [[gaps]] for anything OPEN in this domain.
