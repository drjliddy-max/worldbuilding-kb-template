---
type: domain-moc
domain: cosmology
status: template
tags: [moc]
---

# COSMOLOGY — planes, divine architecture, metaphysics of {{WORLD_NAME}}

> Domain MOC (a *view*). Entity data lives in one note per entity under `entities/` with `domain: cosmology`; this page aggregates them. Add a narrative overview and groupings; let Dataview list the rows. Delete this banner once populated.

## Overview

{{2–4 sentences orienting the reader to COSMOLOGY. Link the key entities and related domains with [[wikilinks]].}}

## All cosmology entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "cosmology"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "cosmology" AND status != "canon"
SORT file.name ASC
```

## Open questions

See [[gaps]] for anything OPEN in this domain.
