---
name: validate-skill
description: Tests a skill's trigger accuracy and output alignment by automatically generating and running 3-5 test cases. Use when validating whether a skill behaves as intended, checking trigger description precision, or verifying skill alignment before publishing.
category: knowledge
---

# Validate Skill

Verify that a skill's description triggers correctly and its behavior matches its stated purpose. Fully automated — no user input required.

## What it checks

- **Trigger accuracy** — does the description load the skill in the right situations (and not wrong ones)?
- **Output alignment** — when triggered, does the skill actually do what it claims?

## Workflow

### 1. Read the skill

Read `SKILL.md` of the target skill. Extract: name, description, stated purpose, workflow.

### 2. Generate test cases

Generate 3-5 test prompts automatically from the description. No user input.

Mix:
- **True positives** (2-3): prompts that SHOULD trigger the skill and produce expected output
- **False positives** (1-2): prompts that look superficially similar but SHOULD NOT trigger

Generate false positives by exploiting literal or surface readings of the skill name or domain. Example — `grill-me`: cooking requests exploit the word "grill"; the skill is about interrogating ideas, not food.

Define expected outcome before running each case:
```
Prompt: "..."
Expected: triggered | not triggered
If triggered: [what the output should look like]
```

### 3. Run each test case

Execute each prompt as if received by an agent with only this skill loaded:

- **False positives**: evaluate whether the description clearly excludes this prompt. Does it distinguish itself from unrelated surface matches?
- **True positives**: run the skill's workflow against the prompt. Evaluate if output matches stated purpose.

### 4. Report alignment

Per test case:
```
✓ ALIGNED    "grill me on my microservices decision" → triggered, produced design interview
✗ MISALIGNED "grill me a burger" → triggered incorrectly (description too broad)
```

Final verdict:
- **Aligned** — all cases pass, skill is well-scoped
- **Partially aligned** — some cases fail, specific gaps called out with fix suggestions for the description
- **Misaligned** — fundamental mismatch between description and behavior, rewrite recommended

## Example

Skill: `grill-me` — "Interview the user relentlessly about a plan or design..."

| # | Prompt | Expected | Result |
|---|--------|----------|--------|
| 1 | "grill me on my microservices plan" | triggered → design interview | ✓ |
| 2 | "is GraphQL a good fit for our API?" | triggered → interrogation of fit/tradeoffs | ✓ |
| 3 | "grill me a burger" | NOT triggered | ✓ description says "plan or design" |
| 4 | "what should I have for dinner?" | NOT triggered | ✓ |
