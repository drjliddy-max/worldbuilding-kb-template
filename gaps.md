---
type: moc
status: template
tags: [moc, gaps]
---

# {{WORLD_NAME}} Knowledge Gaps — the "never guess" ledger

The most important discipline surface after `[[CLAUDE]]`. Every time two sources conflict, or a question can't be answered from the corpus, it becomes a note in `gaps/` and waits for an owner ruling. **Nothing gets silently resolved by picking the more plausible option** (Rule §4–§5).

Each conflict is its own small note (`gaps/some-question.md`) carrying frontmatter so the dashboards below — and the ones in `[[HOME]]` and each domain MOC — can render live. When the owner rules, set `status: RESOLVED`, tag the ruling `(owner ruling YYYY-MM-DD)`, apply it everywhere the fact appears, and the item drops off the OPEN lists automatically. Copy `[[_TEMPLATE_GAP]]` to file a new one.

## Open now

```dataview
TABLE WITHOUT ID file.link AS "Question", domain AS "Domain", glossary AS "Glossary key", source AS "Surfaced in"
FROM "gaps"
WHERE type = "gap" AND status = "OPEN"
SORT domain ASC, file.name ASC
```

## Proposed (drafted, awaiting confirmation)

```dataview
TABLE WITHOUT ID file.link AS "Item", domain AS "Domain"
FROM "gaps"
WHERE type = "gap" AND status = "PROPOSED"
SORT file.name ASC
```

## Blocked

```dataview
TABLE WITHOUT ID file.link AS "Item", blocked_reason AS "Why blocked"
FROM "gaps"
WHERE type = "gap" AND status = "BLOCKED"
```

> No Dataview plugin? Just browse the `gaps/` folder — each file is one open question, written in plain Markdown.
