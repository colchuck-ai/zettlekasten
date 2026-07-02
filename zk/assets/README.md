# ZK skill assets

## zk-template/

Minimal filesystem layout that turns any directory into a Zettelkasten slip-box.

**When to use:** User wants a slip-box folder, or "initialize zettelkasten / agent memory notes."

**What to copy:** Everything inside `zk-template/` into the target directory (not the wrapper folder itself), so the destination gets:

- **template-zettel.md** — Body template for new notes
- **inbox/** — Quick captures (keep empty or with `.gitkeep`)

Conventions, procedures, and the full method live in [../SKILL.md](../SKILL.md) and [../references/zettelkasten.md](../references/zettelkasten.md). Do **not** copy those into the slip-box; the skill applies wherever the layout is detected.

See [../SKILL.md](../SKILL.md) section "Bootstrap from template."
