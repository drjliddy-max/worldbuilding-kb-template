# Getting started — start to finish

The hold-your-hand walkthrough: from no accounts at all to your first ingested source document. If you already know GitHub/Obsidian, the condensed version is in the [README](README.md#quick-start--30-minutes-to-a-working-skeleton).

---

## What you're setting up (the mental model)

Three pieces, all pointing at **one folder on your computer** (the "vault"):

- **The vault** — a folder of plain-text files. *This is your world.* It's yours, offline, no lock-in.
- **[Obsidian](https://obsidian.md)** (free) — the **viewer**. Shows the dashboards, the graph of how everything connects, and lets you read/edit notes.
- **An AI assistant** (optional) — the **worker**. Point it at the same folder and it reads your source docs and writes the organized, cited notes, following the rules already in the folder (`CLAUDE.md` + `AGENTS.md`).

The AI writes the notes → Obsidian displays them. **GitHub** is just where you got this template and where you can back up / share your copy.

**Cost:** the vault + Obsidian + the Dataview plugin are **100% free**. Using an AI assistant to do the ingestion is optional and may require a paid plan for that assistant — but you can also fill notes in by hand for free. The AI only speeds up the tedious part.

---

## A. Get your own copy of the template

**With a GitHub account (gives you a cloud backup):**
1. Go to **[github.com](https://github.com)** → **Sign up** (free) → confirm your email.
2. Open the template: **https://github.com/drjliddy-max/worldbuilding-kb-template**
3. Click the green **“Use this template” → “Create a new repository.”** Name it (e.g. `my-world`), choose Public or Private, **Create**. You now have your own copy.
4. On *your* new repo: green **“Code” → “Download ZIP.”** Unzip somewhere memorable, e.g. `Documents/my-world`.

**Without an account (simplest):** skip 1–3, open the template link, click **“Code” → “Download ZIP”**, unzip. (You only give up the cloud backup.)

---

## B. Set up Obsidian (the viewer) — free

5. Install **[Obsidian](https://obsidian.md)**.
6. **“Open folder as vault”** → pick your unzipped `my-world` folder.
7. Enable the dashboards: **Settings → Community plugins →** turn on community plugins → **Browse →** search **“Dataview” →** Install → Enable.
8. Open **`HOME.md`**. The dashboards should render — there's one example entry included so nothing looks empty.

> Without the Dataview plugin the vault still works as plain Markdown; the dashboard blocks just show as code instead of tables.

---

## C. (Optional) Wire up an AI assistant (the worker)

Any file-capable AI assistant works — the rules live in the folder, not in the tool. See [`AGENTS.md`](AGENTS.md) for how different assistants load them. The short version by type:

- **A terminal/coding agent** that auto-reads `CLAUDE.md`: just open it in the vault folder — it follows the rules automatically.
- **A desktop / knowledge-work agent** you grant a folder to: grant it your `my-world` folder, then give it this once —
  > *“This folder is a worldbuilding knowledge base. Before doing anything, read `CLAUDE.md` and `AGENTS.md` and follow those rules exactly. Start at `HOME.md`. Never invent facts — only use what's in the source documents, cite every fact, and when two sources disagree, stop and ask me instead of guessing.”*
- **A chat assistant** with no folder access: paste the contents of `CLAUDE.md` in at the start of the session.

9. Whichever you use, then have it **personalize the template** — replace the `{{WORLD_NAME}}`, `{{REGION}}`, `{{SYSTEM}}`, `{{OWNER}}`, and `{{SOURCE_ROOT}}` placeholders in `CLAUDE.md` and `HOME.md` with your specifics. (Or edit them by hand in Obsidian.)
10. **Set your authority order** — the single most important one-time decision. Decide which source wins when two docs conflict, especially your “source of record” for who's alive / who holds what / what happened when. Write it into the table in `CLAUDE.md`.

---

## D. Start ingesting your world

11. Put your source docs (PDFs, notes, spreadsheets) in a folder; point the assistant (or yourself) at it.
12. Work **one document at a time**:
    > *“Read [this doc]. For each character, place, faction, item, etc., create a note from `entities/_TEMPLATE_ENTITY.md`, fill in the details with a citation for each fact, link related things with `[[wikilinks]]`, and log any contradictions as notes in the `gaps/` folder. Ask me about anything that conflicts.”*
13. Flip to Obsidian and watch `HOME.md` and the graph fill in.
14. Once you've seen a finished note, **delete the demo** `entities/_EXAMPLE_aldric-thorne.md`. (Keep the `_TEMPLATE_` files — those are your blanks.)

---

## E. (Later) Publish for players

15. When your canon is solid, `notes/canon/` has a ready-made web-page template (`index.html`, `canon.css`, `_TEMPLATE_page.html`). Hand-pick what players are allowed to know and you've got a shareable world wiki — without exposing GM secrets. Open `index.html` in a browser, or host the `notes/canon/` folder anywhere static.

---

## The one rule that makes it all work

**It's better to have ten facts that each cite a source than a hundred that don't.** Go slow. Sourced facts compound; guesses metastasize. Keep the discipline and your world stays coherent no matter how big it grows — coherent enough to publish.
