# skills

Personal agent skills library.

## Planning

- **[grill-me](grill-me/SKILL.md)** — Get relentlessly interviewed about a plan or design until every branch of the decision tree is resolved. Originally by [github.com/mattpocock/skills](https://github.com/mattpocock/skills/tree/main/grill-me).

  ```
  npx skills@latest add mattpocock/skills/grill-me
  ```

## Knowledge

- **[validate-skill](validate-skill/SKILL.md)** — Tests a skill's trigger accuracy and output alignment by automatically generating and running 3-5 test cases.

  ```
  npx skills@latest add ausernamedtom/skills/validate-skill
  ```

- **[write-a-skill](write-a-skill/SKILL.md)** — Create new skills with proper structure, progressive disclosure, and bundled resources. Originally by [github.com/mattpocock/skills](https://github.com/mattpocock/skills/tree/main/write-a-skill).

  ```
  npx skills@latest add mattpocock/skills/write-a-skill
  ```

- **[ubiquitous-language](ubiquitous-language/SKILL.md)** — Extract a DDD-style glossary from the current conversation, flagging ambiguities and proposing canonical terms. Originally by [github.com/mattpocock/skills](https://github.com/mattpocock/skills/tree/main/ubiquitous-language).

  ```
  npx skills@latest add mattpocock/skills/ubiquitous-language
  ```

## Development

- **[tdd](tdd/SKILL.md)** — Test-driven development with a red-green-refactor loop. Builds features one vertical slice at a time. Originally by [github.com/mattpocock/skills](https://github.com/mattpocock/skills/tree/main/tdd).

  ```
  npx skills@latest add mattpocock/skills/tdd
  ```

---

## Contributing a Skill

Skills live at `<skill-name>/SKILL.md`. Each `SKILL.md` starts with frontmatter:

```yaml
---
name: skill-name
description: Use when… (≤1024 chars, third-person)
category: planning     # for README grouping only
source: https://github.com/original-author/repo/path  # omit if original work
---
```

Guidelines:
- Keep `SKILL.md` under ~100 lines. Split overflow into `REFERENCE.md`, `EXAMPLES.md`, or topic `.md` files in the same directory.
- The `description` field determines when the skill loads — make it precise and trigger-driven.
- Add a `scripts/` subfolder only for deterministic, repeatable operations that would otherwise regenerate the same code each run.
- When `source` is present, the skill is a personalized adaptation. Use the original author's install line above the skill entry.
