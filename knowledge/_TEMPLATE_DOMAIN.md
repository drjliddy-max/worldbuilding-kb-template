---
type: domain-moc
domain: {{domain-key}}        # must match the `domain:` field on entities that belong here
status: template
tags: [moc]
---

# {{DOMAIN}} — {{One-line description of this domain}}

> Copy this file to start any new domain MOC. A domain MOC is a *view*: it doesn't hold entity data itself — each entity is its own note in `entities/` — it **aggregates** them with Dataview and adds the connective tissue (narrative overview, groupings, cross-domain links). Delete this banner once it's yours.

## Overview

{{2–4 sentences orienting the reader to this domain: what it covers, the big shape of it, where the tension/interest is. Link out with `[[wikilinks]]` to the most important entities and to related domains like `[[HISTORY]]`.}}

## All {{domain}} entities

```dataview
TABLE status AS "Status", current_state AS "State", aka AS "Aka"
FROM "entities"
WHERE domain = "{{domain-key}}"
SORT status ASC, file.name ASC
```

## Not yet verified

```dataview
LIST
FROM "entities"
WHERE domain = "{{domain-key}}" AND status != "canon"
SORT file.name ASC
```

## Groupings / structure

{{Optional: organize the domain into named groups with `[[wikilinks]]`. Examples:
- CHARACTERS: "Major Antagonists", "Allies", "Court of X"
- GEOGRAPHY: by region/kingdom
- HISTORY: by era (and consider one [[entity]] note per major event)
Delete if not needed.}}

## Open questions in this domain

```dataview
LIST
FROM "gaps"
WHERE type = "gap" AND status = "OPEN" AND domain = "{{domain-key}}"
```
<!-- Assumes one-note-per-gap. If you keep a single gaps.md, just link [[gaps]] here. -->
