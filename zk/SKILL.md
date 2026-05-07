---
name: zk
description: >-
  Maintains a Zettelkasten—atomic linked markdown notes as an on-disk knowledge
  graph and agent memory extension: inbox → permanent notes, date+slug IDs,
  markdown links with explicit context, object tags, structure and buffer notes.
  Use when the user wants zettelkasten, slip-box, linked notes, persistent agent
  memory, knowledge capture, or initializing a notes-only layout; when working in
  any directory that holds this slip-box layout and contract; when copying the
  zk-template assets to bootstrap a slip-box or wiring root AGENTS.md to that path.
license: GPL-3.0
---

# Zettelkasten (ZK) as memory extension

Treat the note archive as **durable hypertext**: small files, stable filenames as IDs, **meaningful links** (always say why a link matters). Agents use it to accumulate structured knowledge across sessions without stuffing context—**retrieve by path/tag and follow links** like a graph.

## Where the slip-box lives

**No fixed path.** The slip-box root is **whichever directory** holds the Zettel layout: leaf **AGENTS.md** (from the template), **zettelkasten.md**, **template-zettel.md**, **inbox/**, and permanent notes in that directory’s root. Users may place that folder anywhere (e.g. `docs/zk/`, `knowledge/notes/`, `zettelkasten/`). There is no separate config key—the chosen path is the contract.

When operating in a repo, resolve the slip-box by **user instruction**, by **opening a file under that folder** and applying **AGENTS.md from repo root down to that file’s directory**, or by **project docs** that state the path.

## Repo roles (when nested)

| File | Audience |
|------|----------|
| **README.md** | Humans: what this folder is, how to use it. |
| **AGENTS.md** | Agents: scope, conventions, procedures. |

If the slip-box directory sits inside a larger repo that already defines **AGENTS.md overlay**, **still read parent AGENTS.md files from repo root down to this folder** and merge; this skill + leaf `AGENTS.md` refine slip-box behavior.

## Conventions (quick reference)

- **IDs / filenames:** `YYYY-MM-DD-slug.md` (kebab-case slug). Markdown links only: `[text](path/to/note.md)`—no `[[wikilinks]]`.
- **Permanent notes:** root of the slip-box folder (same directory as leaf AGENTS.md). **inbox/** for fleeting captures; process regularly into permanent notes or discard.
- **Tags:** include `#YYYY/MM/DD` for creation date; prefer **object** tags (concrete concept) over broad topic tags. See [zettelkasten.md](assets/zk-template/zettelkasten.md).
- **New notes:** use [template-zettel.md](assets/zk-template/template-zettel.md); **link to at least one existing note with context**; avoid orphans.

### Source lines (provenance)

When a note records where content was captured:

1. Use `*Source: …*` (italic line).
2. **Hyperlink** the originating artifact—never prose-only dates. Example: `*Source: [design review](../meetings/2026-05-01.md).*`
3. Multiple origins → multiple links, comma-separated.

## Procedures

Use the leaf **AGENTS.md** in the slip-box folder when present; it duplicates the canonical procedure shape (name, **When**, **What to do** as numbered steps). Default actions:

### Create a permanent note

1. Name `YYYY-MM-DD-slug.md`.
2. Fill from template; tags include `#YYYY/MM/DD`.
3. Body in your own words; every link states why it matters.
4. Save in slip-box root (not inbox).
5. Connect to at least one existing note.

### Process the inbox

1. Open each item in `inbox/`.
2. Promote to permanent (follow above), merge into an existing note, or discard; preserve/add hyperlinked `*Source:*` when promoting.
3. Remove processed items so inbox stays for quick capture only.

## Full method

Principles (connectivity, atomicity, no collector’s fallacy, structure over time, buffer notes, writing workflow) live in **[assets/zk-template/zettelkasten.md](assets/zk-template/zettelkasten.md)**. Read when editing note quality, splits/merges, or structure-note strategy.

## Bootstrap from template

1. Copy **contents** of `assets/zk-template/` into the **user-chosen** directory, preserving `inbox/`, **README.md**, **AGENTS.md**, **zettelkasten.md**, **template-zettel.md**.
2. Edit **README.md** so the title matches the actual folder if needed.
3. If the slip-box lives inside a larger repo, optionally append a **bounded block** to the repository root **AGENTS.md** so overlay rules point agents at the slip-box. Replace `PATH/TO/ZK` with the path from repo root to the slip-box folder (no leading slash). If the markers already exist, replace only the inner section between them.

```markdown
<!-- zk-skill:zettelkasten -->
## Zettelkasten (slip-box)

This repository keeps a Zettelkasten (atomic linked markdown notes) under **`PATH/TO/ZK`**. Agent procedures and conventions: **[PATH/TO/ZK/AGENTS.md](PATH/TO/ZK/AGENTS.md)**. Use the **zk** skill when creating, linking, or processing notes there.

<!-- /zk-skill:zettelkasten -->
```

See [assets/README.md](assets/README.md).
