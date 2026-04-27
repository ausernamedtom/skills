---
name: validate-skill
description: Tests whether a skill's trigger accuracy, output behavior, and the user's understanding of its purpose are all aligned. Automatically generates and runs 3-5 test cases. Use when validating whether a skill behaves as intended, checking trigger description precision, or verifying skill alignment before publishing.
category: knowledge
---

# Validate Skill

Verify that a skill's description triggers correctly, its behavior matches its stated purpose, and the user's mental model of the skill is accurate. Fully automated — no user input required.

## What it checks

- **Trigger accuracy** — does the description load the skill in the right situations (and not wrong ones)?
- **Output alignment** — when triggered, does the skill actually do what it claims?
- **User understanding** — does the user's likely interpretation of the skill name/description match actual behavior?

## Workflow

### 1. Read the skill

Read `SKILL.md` of the target skill. Extract: name, description, stated purpose, workflow.

### 2. Surface the purpose plainly

Before generating test cases, state in one sentence what this skill actually does and — critically — what it does NOT do. This anchors the test cases and makes misunderstandings visible.

```
✔ This skill does: [one sentence]
✘ This skill does NOT: [common misread based on name/wording]
```

### 3. Generate test cases

Generate 3-5 test prompts automatically. No user input.

Mix:
- **True positives** (2-3): prompts that SHOULD trigger and produce expected output
- **False positives** (1-2): prompts that look superficially similar but SHOULD NOT trigger — exploit literal or naive readings of the skill name or domain

Define expected outcome before running each case:
```
Prompt: "..."
Expected: triggered | not triggered
If triggered: [what the output should look like]
```

### 4. Run each test case

Execute each prompt as if received by an agent with only this skill loaded:

- **False positives**: does the description clearly exclude this prompt, or would a naive reading of the name trigger it?
- **True positives**: run the skill's workflow. Does output match stated purpose?

### 5. Report alignment

Per test case:
```
✓ ALIGNED    "grill me on my microservices decision" → triggered, produced design interview
✗ MISALIGNED "grill me a burger" → triggered incorrectly (description too broad)
```

Final verdict covering all three axes:
- **Aligned** — triggers correctly, output matches purpose, name/description communicate intent clearly
- **Partially aligned** — some cases fail; call out specific gaps with fix suggestions for the description
- **Misaligned** — fundamental mismatch between name, description, and/or behavior; rewrite recommended

## Example

Skill: `grill-me` — "Interview the user relentlessly about a plan or design..."

```
✔ This skill does: interrogate ideas, plans, and design decisions through relentless questioning
✘ This skill does NOT: grill food, answer cooking questions, or handle anything literal about "grilling"
```

| # | Prompt | Expected | Result |
|---|--------|----------|--------|
| 1 | "grill me on my microservices plan" | triggered → design interview | ✓ |
| 2 | "is GraphQL a good fit for our API?" | triggered → interrogation of fit/tradeoffs | ✓ |
| 3 | "grill me a burger" | NOT triggered | ✓ description says "plan or design" |
| 4 | "what should I have for dinner?" | NOT triggered | ✓ |
