# Atomic Rules Template

Atomic rules convert source ideas, expert habits, examples, failures, and user feedback into instructions that an agent can actually follow.

## Rule Quality Criteria

Each rule must be:

- Decidable: an evaluator can tell whether the output obeyed or violated it.
- Unambiguous: it should not allow several incompatible interpretations.
- Conditional: it states when it applies and when it does not.

## Rule Template

```markdown
## Rule ID: R001

Rule:

Condition:

Do instead of:

Positive example:

Negative example:

Source:

Eval signal:

Applies to skill section:
```

## Three Rule Levels

| Level | Meaning | Use For | Example |
|---|---|---|---|
| Level 1 - Behavior rule | Concrete output requirement | Formatting, structure, local actions | Keep the final action plan to first step, pilot, metric, risk, review |
| Level 2 - Decision rule | Conditional choice | Tradeoffs, routing, source handling | If only titles are available, produce a pre-distillation framework and mark it uncalibrated |
| Level 3 - Thinking framework | Abstract but reusable reasoning pattern | High-value expert judgment | Separate facts, assumptions, values, and unknowns before applying a theory |

Good distilled skills usually include all three levels. Level 1 is easiest to verify; Level 3 carries the most expert value.

## Extraction Sources

| Source Type | What to Extract | Method |
|---|---|---|
| Book or paper | core rules, concepts, anti-patterns, cases | close reading -> concept cards -> atomic rules |
| Expert material | decisions, emails, notes, documents | classify by scene -> extract judgment standards |
| Agent trace | successful and failed execution logs | mark outcome -> extract reusable behavior |
| Best-practice document | official guidance and common mistakes | deduplicate -> keep only task-critical rules |
| User workflow | repeated manual steps | record sequence -> identify decision points |
| Feedback | "good", "not like this", "change this" | positive feedback validates rules; negative feedback creates boundary rules |

## Rule Inventory

| Rule ID | Level | Rule | Condition | Anti-pattern | Source ID | Eval Signal |
|---|---|---|---|---|---|---|
| R001 | L2 |  |  |  | B001 |  |

## Compression Pass

Before packaging rules into `SKILL.md`:

1. Merge duplicate rules.
2. Convert vague rules into observable behavior.
3. Add conditions to over-broad rules.
4. Remove rules that the base agent already handles reliably.
5. Keep only 3-7 core principles in the main skill; move the rest here.
