# Agent instructions

This repository's operating rules for any AI assistant live in **[`CLAUDE.md`](CLAUDE.md)**.

**Before doing any work in this vault, read `CLAUDE.md` and follow it.** It defines the hard rules that keep the knowledge base trustworthy:

- never invent facts — the source documents are the only truth;
- cite a source for every fact;
- flag conflicts instead of guessing, and ask the owner to resolve them;
- label provisional/unverified content;
- follow the canon-authority hierarchy when sources disagree.

`AGENTS.md` and `CLAUDE.md` are kept intentionally in sync: this file is the pointer, `CLAUDE.md` is the full contract. If they ever differ, `CLAUDE.md` wins.

Start at [`HOME.md`](HOME.md) for the map of the vault.

## How different assistants load these rules

This vault is plain Markdown in folders, so any file-capable AI assistant can author it. The only difference between tools is *how the rules get loaded*:

- **Assistants that auto-read `CLAUDE.md`** (e.g. terminal coding agents that treat it as project instructions): nothing to do — open the assistant in this folder and it follows the rules automatically.
- **Assistants that auto-read `AGENTS.md`**: this file points them to `CLAUDE.md`, so they also load the rules hands-free.
- **Desktop / knowledge-work agents that operate on a folder you grant them** (point-and-go agents, not terminal-based): grant access to this vault folder, then tell the assistant once: **"Read `CLAUDE.md` and follow it before doing any work."** It will honor the rules as visible files even if it doesn't auto-load them.
- **Chat assistants with no folder access**: paste the contents of `CLAUDE.md` into the conversation (or into a custom-instructions / project-instructions field) at the start of the session.

Two things are true for every assistant: it can **author** the notes, but it does **not render** the Dataview dashboards or graph view — that is [Obsidian](https://obsidian.md)'s job. The AI writes the notes; Obsidian displays them.
