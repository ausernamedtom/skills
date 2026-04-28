# ADR Format Summary

Architecture Decision Records (ADRs) are stored in `docs/adr/` with sequential numbering like `0001-slug.md`.

## Core Template
The minimal ADR needs just a title and 1-3 sentences explaining context, the decision, and reasoning. That's sufficient—the goal is documenting *that* a choice was made and *why*, not completing elaborate forms.

## Optional Additions
Include these sections only when they genuinely serve the reader:
- Status indicators (proposed, accepted, deprecated, superseded)
- Considered Options (when rejected paths deserve remembering)
- Consequences (for non-obvious downstream effects)

## When to Create an ADR
Document a decision only if all three criteria apply:

1. **Hard to reverse** — meaningful cost to changing course later
2. **Surprising without context** — future readers will question the approach
3. **Result of trade-offs** — genuine alternatives existed and you chose deliberately

Skip decisions that are easily reversible, obvious in context, or represent the only sensible path.

## Worthy Topics
ADRs should capture architectural shape, integration patterns between systems, high-lock-in technology selections, boundary definitions, deliberate deviations from convention, hidden constraints, and non-obvious rejections of alternatives.

## Numbering
Identify the highest number in `docs/adr/` and increment sequentially for each new record.
