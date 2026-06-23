---
type: domain-moc
domain: magic
status: template
tags: [moc]
---

# MAGIC — magic systems and how power works in {{WORLD_NAME}}

> Domain MOC (a *view*). Entity data lives in one note per entity under `entities/` with `domain: magic`; this page aggregates them. Add a narrative overview and groupings; let Dataview list the rows. Delete this banner once populated.

## Overview

{{2–4 sentences orienting the reader to MAGIC. Link the key entities and related domains with [[wikilinks]].}}

## All magic entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "magic"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "magic" AND status != "canon"
SORT file.name ASC
```

## Open questions

See [[gaps]] for anything OPEN in this domain.
