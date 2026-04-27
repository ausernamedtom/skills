# skills

Personal agent skills library.

Skills are organized by functional category. Each skill has a `scope` — **global** skills work anywhere, **per-project** skills are intended to be installed in a specific project's agent config directory.

## Installation

```bash
npx skills@latest add tomhofman/skills/<category>/<skill-name>
```

Example:
```bash
npx skills@latest add tomhofman/skills/planning/grill-me
```

---

## Communication

> Tone, output style, and compression.

| Skill | Scope | Description | Source |
|-------|-------|-------------|--------|

---

## Planning

> Design reviews, PRDs, architecture decisions.

| Skill | Scope | Description | Source |
|-------|-------|-------------|--------|

---

## Development

> TDD, code review, refactoring, security.

| Skill | Scope | Description | Source |
|-------|-------|-------------|--------|

---

## Knowledge

> Memory management, documentation, writing.

| Skill | Scope | Description | Source |
|-------|-------|-------------|--------|

---

## Tooling

> Git hooks, CI, project scaffolding.

| Skill | Scope | Description | Source |
|-------|-------|-------------|--------|

---

## Contributing a Skill

Skills live at `<category>/<skill-name>/SKILL.md`. Each `SKILL.md` starts with frontmatter:

```yaml
---
name: skill-name
description: Use when… (≤1024 chars, third-person)
scope: global          # global | per-project
category: communication
source: https://github.com/original-author/repo/path  # omit if original work
---
```

Guidelines:
- Keep `SKILL.md` under ~100 lines. Split overflow into `REFERENCE.md`, `EXAMPLES.md`, or topic `.md` files in the same directory.
- The `description` field determines when the skill loads — make it precise and trigger-driven.
- Add a `scripts/` subfolder only for deterministic, repeatable operations that would otherwise regenerate the same code each run.
- When `source` is present, the skill is a personalized adaptation. The README credits the original; the `SKILL.md` content is the local version.
