---
type: rules
status: template
tags: [rules, canon-authority, moc]
---

# {{WORLD_NAME}} — Campaign Knowledge Project

> **This is an Obsidian vault.** Open this folder as a vault in [Obsidian](https://obsidian.md) and install the **Dataview** community plugin. Then the frontmatter on each note becomes queryable columns, `[[wikilinks]]` become navigable relationships, and the graph view becomes your entity map. See `[[HOME]]` for the master map of content (MOC).

> **This is a template.** Replace every `{{PLACEHOLDER}}` with your own world's specifics, then delete this line.
> `{{WORLD_NAME}}` = your world (e.g. "Aurelia"). `{{REGION}}` = primary continent/region. `{{SYSTEM}}` = your game system (D&D 5e, Pathfinder, homebrew, etc.). `{{SOURCE_ROOT}}` = where your raw source files live. `{{OWNER}}` = you (the canon authority). `{{ORIGINAL_AUTHOR}}` = whoever first authored the lore, if not you.

**Purpose:** A persistent, navigable knowledge base for the {{SYSTEM}} campaign set in the world of **{{WORLD_NAME}}**, primarily the region of **{{REGION}}**. Built so any reader — or any AI assistant — can answer questions about the world (cosmos, history, current events, characters, factions, magic, geography, prophecies, ongoing arcs) and route back to the source material when needed.

This knowledge base is also the **canonical source for anything published for player or reader consumption** (handouts, a player wiki, a published-world site, a novel set in this world). Nothing reaches players that isn't grounded here first.

**Status:** Phase 1 (scaffold) — fill in as you ingest.

---

## Operating Rules (HARD RULES — read first)

These are the rules that make this knowledge base *trustworthy*. They are the whole point. A fast knowledge base that invents facts is worse than no knowledge base. **The goal is to be correct, not fast.**

1. **Never make anything up.** The source documents are the only truth. If the sources are silent, the answer is "not established," not a plausible guess.

2. **Define your canon-authority hierarchy and follow it.** When two sources disagree, you need a *predetermined* rule for which one wins — decided once, applied everywhere, never re-litigated per conflict. A sensible default order (highest authority first):
   1. **Owner's direct statement** — when {{OWNER}} states a fact (in conversation, a note, a ruling), that is canon. Tag it `(owner ruling YYYY-MM-DD)`.
   2. **The authoritative dated-state document** — pick your single source of record for *who holds what, who is alive, what happened when* (e.g. a campaign calendar, a session log, a "current state" doc). This wins on all dated/state questions. → set this to: `{{STATE_OF_RECORD_DOC}}`
   3. **Newest dated document wins** — when two canonical docs conflict and neither is the owner's word or the state-of-record, the more recently dated one is the refined version.
   4. **Primary authored sources** ({{ORIGINAL_AUTHOR}}'s originals, the GM's own docs) — the substrate everything builds on.
   5. **Derivative syntheses** (this KB, a glossary, an AI summary) — lowest authority; they inherit, never override.
   - Write your final order into the table in the next section and **stop re-deciding it mid-task.**

3. **Source citation is mandatory.** Every fact in a knowledge file must cite the source file it came from, in `(source: path/to/file p.N)` notation. No fact-by-vibes. A claim with no citation is a claim that needs verifying — mark it so.

4. **Conflicts are flagged, not papered over.** When two sources disagree, both go into `gaps.md` with the conflict named explicitly. The owner decides. Never silently pick the more plausible-sounding option and move on — that is how a knowledge base quietly fills with invented canon.

5. **When in doubt — ASK.** Before writing a fact when sources are silent or in conflict, ask the owner. Do not infer, synthesize-and-hope, or default to the likelier option. This is a per-conflict discipline, not a suggestion.

6. **Provisional content must be labelled.** Anything populated from a *derivative* source (an AI summary, a draft, another writer's working canon) before it has been checked against a primary source is **provisional**. Give it a visible banner at the top of the file:
   > **PROVISIONAL — derived from {{SOURCE}}, pending verification against primary source.**
   Remove the banner only after a primary source confirms it.

7. **Owner corrections are canon.** When {{OWNER}} states a fact that corrects the KB, that fact wins over any document. Tag it `(owner YYYY-MM-DD)` and propagate the correction everywhere the old fact appeared — don't fix one file and leave three stale.

8. **READ-FIRST MODE.** When the task is "read/understand source X first," do **not** write knowledge files during the read pass. Read the source, log findings and contradictions to `notes/ingestion-tracker/read-pass-YYYY-MM-DD.md`, and **ask before resolving conflicts**. Synthesize into `knowledge/*.md` only *after* the read pass is complete and confirmed. Writing while reading produces drift-by-inference — the exact failure this rule prevents.

9. **Distinguish intent from event.** Documents that record what a character *thought, planned, intended, feared, or believed* (musings, interior monologue, planning notes) are **not** records of what actually happened. Only your state-of-record source (Rule §2.2) documents events. A villain's plan to attack a city is not the same as the city being attacked. Frame interior/planning material as *intent / motivation / capability*, never as history.

10. **Names matter — track variants.** Worlds accrete near-homophones, misspellings, and renamed-across-versions entities. Pick **one canonical spelling** per entity and record every variant as an `aka`/redirect, never as a second canonical entity. Keep a "easily confused" table in `GLOSSARY.md`. A single wrong name can fork your canon into two people who are really one.

11. **(Optional) Name-translation layer for published works.** If your published novel/wiki renames canon entities to avoid real-world collisions, keep the **canon name in this KB** and maintain the canon→published-name mapping in *one* table owned by the publishing side. Never rename in the KB itself.

These rules supersede any speed-vs-thoroughness tradeoff.

---

## Your canon-authority hierarchy (FILL THIS IN)

Decide this once. This is the single most important configuration choice in the whole system.

| Rank | Authority | Your specific source | Wins on |
|---|---|---|---|
| 1 | Owner's direct ruling | {{OWNER}}, dated | everything, when explicit |
| 2 | State-of-record | `{{STATE_OF_RECORD_DOC}}` | all dated/state questions (who holds what, who's alive, sequence of events) |
| 3 | Newest dated document | (by date) | refinements of older canon |
| 4 | Primary authored sources | `{{SOURCE_ROOT}}/...` | original lore substrate |
| 5 | Derivative syntheses | this KB, glossary, AI exports | nothing — they inherit |

---

## Project Layout (an Obsidian vault)

```
{{WORLD_NAME}}-kb/                ← open THIS folder as an Obsidian vault
├── HOME.md               ← master Map of Content (start here in Obsidian)
├── CLAUDE.md             ← this file (the rules; read first)
├── README.md             ← what this is, quick start
├── INDEX.md              ← catalog of every raw source file, topic-tagged
├── gaps.md               ← open conflicts + unanswered questions (Dataview-queryable)
├── entities/             ← ONE note per entity = the "rows" of the database
│   ├── _TEMPLATE_ENTITY.md  ← copy this to create any character/place/item/etc.
│   └── …                 ← your characters, places, factions, artifacts, gods…
├── knowledge/            ← domain MOCs ("views") — each auto-lists its entities via Dataview
│   ├── _TEMPLATE_DOMAIN.md  ← the domain-MOC template
│   ├── COSMOLOGY.md  PANTHEON.md  HISTORY.md  GEOGRAPHY.md  FACTIONS.md
│   ├── CHARACTERS.md  PLAYERS.md  MAGIC.md  ARTIFACTS.md  CREATURES.md
│   ├── PROPHECIES.md  CURRENT_EVENTS.md  CHARACTER_SHEETS.md
│   └── GLOSSARY.md       ← the A–Z entity index (auto-built by Dataview) + spelling authority
├── notes/
│   ├── ingestion-tracker/ ← read-pass logs (one per source-reading session)
│   └── canon/            ← the PUBLISHABLE player-facing layer (HTML + CSS)
├── handouts/             ← player-facing handouts (briefs, maps, item cards)
└── external/             ← drop ChatGPT / Claude / other AI exports here to ingest
```

**The relational model, in Obsidian terms:** each note in `entities/` is a *row*; its frontmatter fields are *columns*; `[[wikilinks]]` between notes are *foreign keys*; the Dataview queries in the domain MOCs are *SQL views*; the graph view is your *entity-relationship diagram*. Rename/trim the domain MOCs to the domains your world actually has — they're a starting point, not a requirement.

---

## The Obsidian vault model (how the "database" works)

**Every entity is its own note** in `entities/`, with a frontmatter block that makes it queryable. The standard schema (copy from `[[_TEMPLATE_ENTITY]]`):

```yaml
---
type: entity
entity_type: character   # character | location | faction | deity | artifact | creature | event | concept | prophecy | player
domain: characters       # which domain MOC this rolls up into
status: canon            # canon | provisional | proposed | speculation | stub
aka: [Alias, Misspelling] # variant spellings — search/redirect, never separate notes
current_state:           # e.g. alive / dead / destroyed / held-by-X (for dated-state entities)
as_of:                   # the date your current_state is true as of
sources:                 # the documents the facts trace to
  - "WorldBible.pdf p.12"
tags: [npc, antagonist]
---
```

- **Link, don't retype.** When this entity relates to another (parent, ally, ruler-of, located-in), write it as a `[[wikilink]]` in the body or a frontmatter field. That link *is* the relationship — Obsidian's graph and backlinks make it navigable both ways.
- **`status` drives trust.** `provisional` / `proposed` / `speculation` are the Dataview-visible equivalents of the PROVISIONAL banner in Rule §6. A query in `[[HOME]]` lists everything not yet `canon` so you always know what still needs verifying.
- **One note per entity, one canonical title.** Variants go in `aka`, never as separate notes (Rule §10). Obsidian aliases (`aliases:` frontmatter) make `aka` names autocomplete to the canonical note.
- **Folders are cosmetic.** Dataview classifies by the `entity_type`/`domain` fields, not by folder. Keep `entities/` flat, or subfolder by type — your call.

This means the disciplines in the Hard Rules above are now *enforceable by query*: "show me every fact with no source," "every provisional entity," "every OPEN gap" are one Dataview block each. See `[[HOME]]` for the starter queries.

---

## Source Material Roots (FILL THIS IN)

**Primary canonical corpus** (read-only — never modify the originals):
- `{{SOURCE_ROOT}}/` — your raw GM docs, PDFs, spreadsheets, maps, character sheets.
  - Keep this **outside** the KB repo if it's large or contains material you don't want version-controlled. The KB *points to* sources; it does not copy them.

**Derivative / working sources:**
- `external/` — drop AI-assistant exports (ChatGPT, Claude) here as `.md` / `.txt` / `.pdf` for ingestion. Treat everything here as **provisional** (Rule §6) until verified against a primary source.

---

## File-Format Quirks (common source formats)

- **.pdf** — readable directly; for long PDFs, read by page range.
- **.docx / .rtf** — convert with `textutil -convert txt "file.docx" -output "file.txt"` (macOS).
- **.pages / .numbers** (Apple) — often contain a `QuickLook/Preview.pdf` inside the package; read that. Or a matching `.pdf` usually sits next to the source — prefer it.
- **.csv / .xml** — plain text; read or grep directly. Good for timelines and stat blocks.
- **images** — read visually for maps, portraits, sigils.
- **.epub** — unzip and read the content `.html` / `.xhtml` inside.

---

## How to Answer a Question About {{WORLD_NAME}}

1. **Check `knowledge/`** first — the relevant domain file should have the answer or a route to the source.
2. **Check `INDEX.md`** for source files tagged with that topic if the knowledge file is thin.
3. **Read the source file directly** if needed.
4. **Be honest about what you've actually read.** If the answer comes from a synthesis you didn't re-open this session, say so.
5. **Cite the source path** for every claim.
6. **If unanswerable from the corpus**, say so and log it in `gaps.md`.

---

## How to Ingest a New Source File

1. **Read it.** (In read-first mode, log to `notes/ingestion-tracker/` and stop — do not write knowledge files yet.)
2. Decide which `knowledge/*.md` file(s) it informs.
3. Add facts **with source citation**: `... (source.pdf p.12)`.
4. New named entity (character, place, item, deity, faction)? Add it to `GLOSSARY.md` and tag it in `INDEX.md`.
5. Conflict with existing canon? → `gaps.md`. Do not resolve it yourself.
6. Don't rewrite or move the source. The source corpus stays read-only.

---

## House Style — Knowledge Files

- **One synthesized `.md` per domain.** Don't sprawl; don't duplicate.
- **Every fact cites its source path.**
- **Mark uncertainty.** Conflicts are documented, not hidden.
- **Cross-link liberally with `[[wikilinks]]`:** `[[The Sundering]]`, `[[Some Character]]`. Every link strengthens the graph and creates a backlink on the other note. A `[[link]]` to a note that doesn't exist yet is fine — it's a stub marker, not an error.
- **Don't invent.** Speculation is allowed *only* if labelled `(speculation — no source)`.
- **Update `gaps.md`** whenever a question can't be answered from the corpus.

---

## What This Project Is NOT

- Not a game-rules reference — use your system's rulebooks for mechanics.
- Not the published novel/manuscript — that lives in its own repo and is *derivative* of this one.
- Not a session-by-session play log (unless you choose to make `CURRENT_EVENTS.md` serve that role).
- Not a place to edit source material — the source corpus is read-only canon.
