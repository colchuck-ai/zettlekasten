# Zettelkasten

**Zettelkasten** (atomic, linked markdown notes) as a standalone **[Agent Skill](https://agentskills.io/home)** (the **ZK** skill) and **template**—an on-disk **knowledge graph / memory extension** for agents and humans.

## Contents

| Path | Purpose |
|------|---------|
| `zk/SKILL.md` | Single source of truth: when to apply ZK, conventions, procedures, bootstrap. |
| `zk/references/zettelkasten.md` | Full method (principles, linking, structure, writing). Skill-owned; read on demand. |
| `zk/assets/zk-template/` | Minimal slip-box layout: `template-zettel.md` and `inbox/`. |

## Quick start

1. Add `zk` to your agent skills path (e.g. symlink or copy `zk/` into `.cursor/skills/zk/`).
2. **Bootstrap:** copy the contents of `zk/assets/zk-template/` into your chosen slip-box folder. Nothing else needs to be copied—the skill applies wherever the layout is detected.

License: GPL-3.0 (see [zk/SKILL.md](zk/SKILL.md)).

## Development

| Path | Purpose |
|------|---------|
| `package.json` | Optional workspace metadata (private package; no runnable scripts). |
