---
name: zk
description: >-
  Maintains a Zettelkasten—atomic linked markdown notes as an on-disk knowledge
  graph and agent memory extension: inbox → permanent notes, date+slug IDs,
  markdown links with explicit context, object tags, structure and buffer notes.
  Use when the user wants zettelkasten, slip-box, linked notes, persistent agent
  memory, knowledge capture, or initializing a notes-only layout; when working
  in any directory that holds the slip-box layout (`template-zettel.md`,
  `inbox/`, and `YYYY-MM-DD-slug.md` permanent notes); when copying the
  zk-template assets to bootstrap a slip-box.
license: GPL-3.0
---

# Zettelkasten (ZK) as memory extension

Treat the note archive as **durable hypertext**: small files, stable filenames as IDs, **meaningful links** (always say why a link matters). Agents use it to accumulate structured knowledge across sessions without stuffing context—**retrieve by path/tag and follow links** like a graph.

This skill is the **single source of truth** for slip-box conventions and procedures. Slip-boxes hold *only* notes; there is no per-slip-box `AGENTS.md` or agent-facing procedure doc—apply this skill wherever the layout is detected.

## Where the slip-box lives

**No fixed path.** The slip-box root is **whichever directory** holds the Zettel layout: `template-zettel.md`, `inbox/`, and permanent notes named `YYYY-MM-DD-slug.md` in that directory's root. Users may place that folder anywhere (e.g. `docs/zk/`, `knowledge/notes/`, `zettelkasten/`). There is no separate config key—the chosen path is the contract.

Resolve the slip-box by **user instruction**, by **opening a file** whose sibling files match the layout above, or by **project docs** that state the path. When operating in a nested repo, still read parent `AGENTS.md` files from repo root down; this skill refines slip-box behavior on top of them.

## Conventions (quick reference)

- **IDs / filenames:** `YYYY-MM-DD-slug.md` (kebab-case slug). Markdown links only: `[text](path/to/note.md)`—no `[[wikilinks]]`.
- **Permanent notes:** root of the slip-box folder. **inbox/** for fleeting captures; process regularly into permanent notes or discard.
- **Tags:** include `#YYYY/MM/DD` for creation date; prefer **object** tags (concrete concept) over broad topic tags. See [references/zettelkasten.md](references/zettelkasten.md).
- **New notes:** use [assets/zk-template/template-zettel.md](assets/zk-template/template-zettel.md); **link to at least one existing note with context**; avoid orphans.

### Source lines (provenance)

When a note records where content was captured:

1. Use `*Source: …*` (italic line).
2. **Hyperlink** the originating artifact—never prose-only dates. Example: `*Source: [design review](../meetings/2026-05-01.md).*`
3. Multiple origins → multiple links, comma-separated.

## Procedures

### Create a permanent note

1. Name the file `YYYY-MM-DD-slug.md` (date + kebab-case slug).
2. Fill from [template-zettel.md](assets/zk-template/template-zettel.md): title, tags (include `#YYYY/MM/DD`), Summary, Notes, Links.
3. Body in your own words; every link states **why** it matters.
4. Save in the slip-box root (not `inbox/`).
5. Link to at least one existing note; avoid orphans.

### Process the inbox

1. Open each item in `inbox/`.
2. Promote to a permanent note (steps above), merge into an existing note, or discard. When promoting, preserve or add a hyperlinked `*Source:*` line pointing at the originating artifact.
3. Remove processed items so `inbox/` stays for quick capture only.

## Summary for agents

| Decision | Prefer |
|----------|--------|
| Linking | Always add link context (why this link). |
| Note size | One thought per note; split when a note is hard to use or mixes ideas. |
| Organization | Object tags (not topic); structure notes that emerge; no upfront categories. |
| New material | Process into notes and links soon; avoid collecting without processing. |
| Note content | Your own words; add context and relevance. |
| Structure | Let layers emerge (content → structure notes → main structure); buffer notes for project staging. |
| Evidence layers | Keep phenomenon, interpretation, and synthesis distinct in or between notes; check primary sources. |
| Writing | Outline first (attach note refs), then paste and rewrite; separate research and drafting; outlines/buffers per project. |

When in doubt, favor **connection with explicit meaning** over more notes or more links without context. Principles over techniques; less clutter, more clarity.

## Full method

Principles (connectivity, atomicity, no collector's fallacy, structure over time, buffer notes, writing workflow) live in **[references/zettelkasten.md](references/zettelkasten.md)**. Read when editing note quality, splits/merges, or structure-note strategy.

## Bootstrap from template

1. Copy the **contents** of `assets/zk-template/` into the user-chosen directory, preserving `inbox/` and `template-zettel.md`.
2. Do **not** copy `AGENTS.md`, `README.md`, or the full method into the slip-box—this skill owns them, and duplicating invites drift. If a human-facing overview is wanted, add a short `README.md` that describes only what the folder is (do not restate conventions).

Agents pick up this skill from the layout itself or from the user mentioning a Zettelkasten. No breadcrumb snippet in the repo root `AGENTS.md` is required.

See [assets/README.md](assets/README.md).
