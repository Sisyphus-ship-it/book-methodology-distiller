# Evaluation Template

Use this file to test whether a distilled skill improves agent behavior rather than merely documenting ideas.

## Test Loop

### 1. Baseline Test

Run the same realistic task without the skill.

Record:
- task prompt
- output quality
- missing steps
- repeated mistakes
- unsupported claims
- actionability score

### 2. Skill Activation Test

Run the same task with the distilled skill active.

Record:
- whether the skill was triggered correctly
- which methodology modules were used
- which atomic rules were followed or violated
- output quality
- remaining failure modes

### 3. Delta Check

Compare baseline vs skill output.

The skill is useful only if it produces a visible improvement in routing, reasoning, actionability, source discipline, or verification. If improvement is weak, revise rules or add clearer conditions.

## Scenario Set

Test at least five realistic tasks:

| Scenario | Prompt | Expected Skill Behavior | Pass / Fail | Notes |
|---|---|---|---|---|
| Personal confusion |  | Separates facts, assumptions, values, and next experiment |  |  |
| Project stalled |  | Finds bottleneck and gives a low-cost pilot |  |  |
| Research blocked |  | Distinguishes missing evidence from unclear framing |  |  |
| Relationship conflict |  | Avoids theory overreach and asks for concrete facts |  |  |
| Major decision |  | Produces tradeoff criteria, risks, and validation path |  |  |

## 13-Point Quality Checklist

| # | Check | Standard | Result |
|---|---|---|---|
| 1 | Metadata complete | `name` and trigger-focused `description` exist |  |
| 2 | Description routable | Agent can tell when to activate the skill |  |
| 3 | Core principles limited | Main skill has 3-7 core principles |  |
| 4 | Clear phases | Workflow phases are easy to follow |  |
| 5 | Each step has an artifact | Agent knows what to produce after each step |  |
| 6 | Quality standards exist | Good output can be judged |  |
| 7 | Boundaries exist | The skill says what not to do |  |
| 8 | Examples or templates exist | Correct and incorrect patterns are visible where useful |  |
| 9 | No hard-coded paths | No user-specific absolute paths in reusable skill output |  |
| 10 | Tool declarations are honest | Only required tools/resources are mentioned |  |
| 11 | Main file remains compact | Long references are moved out of `SKILL.md` |  |
| 12 | No internal contradictions | Rules do not conflict silently |  |
| 13 | Evaluable | Tests can check whether behavior improved |  |

## Iteration Signals

| Signal | Action |
|---|---|
| Agent repeatedly violates a rule | Make the rule more concrete, conditional, or easier to evaluate |
| Skill fails in a specific scene | Add a boundary, routing rule, or example |
| Rule overload causes confused output | Merge, delete, or move rules to references |
| Output quality is unstable | Add quality standards and named phase artifacts |
| User says "don't do this" | Add a negative rule or misuse warning |
| User says "this is good" | Preserve the pattern and link it to the rule that caused it |
| Base agent improves | Simplify rules that are no longer necessary |
