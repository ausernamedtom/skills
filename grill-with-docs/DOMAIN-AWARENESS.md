# Summary: Domain Awareness Guidelines

This document establishes consumer rules for exploring codebases, complemented by producer rules in SKILL.md.

## Key Requirements Before Exploration

Reviewers should consult three document types:
- **CONTEXT.md** (repo root) or **CONTEXT-MAP.md** (if present, directing to multiple context files)
- **ADRs** in `docs/adr/` (and context-specific ADRs in `src/<context>/docs/adr/` for multi-context repos)
- Proceed silently if these files don't exist; avoid flagging absences or suggesting upfront creation

## File Organization Patterns

**Single-context repos** contain CONTEXT.md and docs/adr/ at the root.

**Multi-context repos** use CONTEXT-MAP.md at root with separate CONTEXT.md and docs/adr/ folders under each `src/<context>/` subdirectory for context-scoped decisions.

## Three Core Practices

1. **Vocabulary alignment**: Use terms exactly as defined in CONTEXT.md; recognize gaps as signals for documentation work rather than inventing terminology

2. **Glossary discipline**: When naming domain concepts in outputs (issues, proposals, tests), maintain consistency with established project language

3. **ADR transparency**: Surface contradictions with existing ADRs explicitly, noting rationale for reconsideration rather than silently overriding documented decisions
