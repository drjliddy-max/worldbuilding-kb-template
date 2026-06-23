---
type: domain-moc
domain: current-events
status: template
tags: [moc]
---

# CURRENT_EVENTS — what is happening right now in the campaign present

> Domain MOC (a *view*). Entity data lives in one note per entity under `entities/` with `domain: current-events`; this page aggregates them. Add a narrative overview and groupings; let Dataview list the rows. Delete this banner once populated.

## Overview

{{2–4 sentences orienting the reader to CURRENT_EVENTS. Link the key entities and related domains with [[wikilinks]].}}

## All current-events entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "current-events"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "current-events" AND status != "canon"
SORT file.name ASC
```

## Open questions

See [[gaps]] for anything OPEN in this domain.
