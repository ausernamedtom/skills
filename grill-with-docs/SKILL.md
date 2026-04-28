---
name: grill-with-docs
description: Conduct intensive design review sessions that stress-test plans against the project's domain model, refine terminology, and update documentation (CONTEXT.md, ADRs) as decisions solidify. Use when user wants to review a design against docs, stress-test a plan with domain context, or mentions "grill me with docs".
category: planning
source: https://github.com/mattpocock/skills
---

# grill-with-docs

A Claude prompt designed to conduct intensive design reviews by stress-testing plans against a project's domain model and documented decisions.

## Core Purpose

The tool interviews users "relentlessly" about their plans, walking through design decisions systematically. It aims to resolve dependencies between choices while maintaining alignment with existing project language and architectural records.

## Key Mechanics

**Documentation Integration:**
- Explores `CONTEXT.md` for domain glossary and terminology
- References ADRs (Architecture Decision Records) in `docs/adr/`
- Supports multi-context repos via `CONTEXT-MAP.md`
- Creates files lazily only when decisions crystallize

**Active Challenges:**
- Flags terminology conflicts between user statements and existing glossary
- Converts vague language into precise canonical terms
- Tests domain relationships through invented edge-case scenarios
- Cross-references stated behavior against actual codebase implementation

**Documentation Updates:**
- Captures term resolutions in `CONTEXT.md` *during* the session (not batched)
- Proposes ADRs only when decisions meet three criteria: hard to reverse, surprising without context, and result from genuine trade-offs

**Question Approach:**
Asks one question at a time, awaiting feedback before proceeding. When applicable, explores the codebase rather than asking.

The session prioritizes shared understanding through iterative refinement of both language and decisions.

See also: [ADR-FORMAT.md](ADR-FORMAT.md), [CONTEXT-FORMAT.md](CONTEXT-FORMAT.md), [DOMAIN-AWARENESS.md](DOMAIN-AWARENESS.md)
