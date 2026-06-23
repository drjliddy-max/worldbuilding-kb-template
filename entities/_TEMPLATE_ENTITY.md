---
type: entity
entity_type: character      # character | location | faction | deity | artifact | creature | event | concept | prophecy | player
domain: characters          # the domain MOC this rolls up into (matches a knowledge/ file)
status: stub                # stub | provisional | proposed | speculation | canon
aliases: []                 # Obsidian aliases — variant spellings autocomplete to this note
aka: []                     # human-readable variant/misspelling list (also add to GLOSSARY)
current_state:              # alive | dead | destroyed | held-by-[[X]] | active … (dated-state entities only)
as_of:                      # the date current_state is true as of
sources: []                 # e.g. ["WorldBible.pdf p.12", "owner ruling 2026-01-01"]
tags: []
---

# {{Entity Name}}

> One copy of this file per entity. This is a *row* in the database. Fill the frontmatter (those are the queryable *columns*), then write the prose below. Delete these instruction lines once real.
>
> **Set `status: canon` only after a primary source confirms it.** Until then `provisional` / `proposed` / `speculation` keeps it visible in the `[[HOME]]` "not yet verified" dashboard (Rule §6).

**{{Entity Name}}** — {{short epithet / role / one-line tag}}.

## Identity

{{One-to-three-sentence definition of what/who this is.}} (source: {{file.pdf}} p.{{N}})

## Key facts

- {{fact}} (source: {{file}} p.{{N}})
- {{fact}} (source: {{file}} p.{{N}})

## Current state (as of {{DATE}})

{{Anything time-sensitive — alive/dead, who holds it, where it is now.}} Cite the state-of-record source. ({{state-of-record}} {{date}})

## Relationships

Write these as `[[wikilinks]]` — each one is a foreign key that shows up in the linked note's backlinks and the graph.

- {{Relationship, e.g. "Half-brother of"}} [[{{Other Entity}}]]
- {{e.g. "Located in"}} [[{{Place}}]]
- {{e.g. "Member of"}} [[{{Faction}}]]

## Variants / aka

{{None, or list non-canonical spellings — also recorded in [[GLOSSARY]]. Per Rule §10, these are redirects, never separate notes.}}

## Open questions

{{None, or summarize — and mirror into [[gaps]] so it shows on the conflicts dashboard.}}

## Sources

- {{file.pdf}}
- {{owner ruling DATE, if any}}
