# zk-skill

**Zettelkasten** (atomic, linked markdown notes) as a standalone **[Agent Skill](https://agentskills.io/home)** and **template**—an on-disk **knowledge graph / memory extension** for agents and humans.

## Contents

| Path | Purpose |
|------|---------|
| `zk/SKILL.md` | When to apply ZK, conventions, provenance, bootstrap steps, pointer to full method. |
| `zk/assets/zk-template/` | Slip-box layout: README, AGENTS, `zettelkasten.md`, `template-zettel.md`, `inbox/`. |

## Quick start

1. Add `zk` to your agent skills path (e.g. symlink or copy `zk/` into `.cursor/skills/zk/`).
2. **Bootstrap:** copy everything under `zk/assets/zk-template/` into your chosen slip-box folder; optionally add the root `AGENTS.md` snippet from [zk/SKILL.md](zk/SKILL.md) so the repo points agents at that path.

License: GPL-3.0 (see [zk/SKILL.md](zk/SKILL.md)).

## Development

| Path | Purpose |
|------|---------|
| `package.json` | Optional workspace metadata (private package; no runnable scripts). |
