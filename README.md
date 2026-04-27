# skills

Personal agent skills library.

Skills have a `scope` — **global** skills work anywhere, **per-project** skills are intended to be installed in a specific project's agent config directory.

## Installation

```bash
npx skills@latest add ausernamedtom/skills/<skill-name>
```

Example:
```bash
npx skills@latest add ausernamedtom/skills/grill-me
```

---

## Skills

| Skill | Category | Scope | Description | Source |
|-------|----------|-------|-------------|--------|

---

## Contributing a Skill

Skills live at `<skill-name>/SKILL.md`. Each `SKILL.md` starts with frontmatter:

```yaml
---
name: skill-name
description: Use when… (≤1024 chars, third-person)
scope: global          # global | per-project
category: planning     # for README grouping only
source: https://github.com/original-author/repo/path  # omit if original work
---
```

Guidelines:
- Keep `SKILL.md` under ~100 lines. Split overflow into `REFERENCE.md`, `EXAMPLES.md`, or topic `.md` files in the same directory.
- The `description` field determines when the skill loads — make it precise and trigger-driven.
- Add a `scripts/` subfolder only for deterministic, repeatable operations that would otherwise regenerate the same code each run.
- When `source` is present, the skill is a personalized adaptation. The README credits the original; the `SKILL.md` content is the local version.
