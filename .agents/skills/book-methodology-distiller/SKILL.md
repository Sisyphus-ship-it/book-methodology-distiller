---
name: book-methodology-distiller
description: Use when the user wants to distill books, theory systems, schools of thought, author ideas, or literature into a reusable Codex methodology skill; trigger on 学习这些书, 蒸馏成方法论, 创建思想体系 Skill, 把理论变成现实问题解决工具, or 建立决策框架.
---

# 书籍方法论蒸馏器

## Overview

Transform books, theory systems, schools of thought, author ideas, or literature collections into usable Codex methodology skills. Do not summarize books; encode scattered, implicit, and verbose knowledge into structured, explicit, compact instructions that let an agent reproduce expert-like judgment in a specific scene.

## Core Rule

Always convert source material through this chain:

```text
source claim -> methodology principle -> diagnostic question -> operating step -> real-world use
```

The final output must help Codex analyze, decide, act, verify, and review when the user brings a real problem. It must not become chapter notes, quote collections, background essays, or a replacement for the original books.

Keep the main `SKILL.md` compact. Move detailed atomic rules, eval plans, source maps, concept cards, and long examples into `references/` or `templates/`.

## Source Status

Classify every source before distilling:

| Status | Meaning | Allowed Work | Forbidden Work |
|---|---|---|---|
| Full text read | PDF, EPUB, TXT, MD, notes, or pasted text has been inspected | Source-grounded cards, source map, calibrated skill | Fabricating missing pages |
| Metadata only | User only gave title, author, list, or theme | Pre-distillation framework, extraction templates, tentative skill skeleton | Precise quotations, page claims, "I read chapter..." claims |
| Public-knowledge inference | The work is known but not supplied in this session | Clearly labeled tentative framework | Treating inference as textual evidence |
| Needs verification | Source, edition, or interpretation is uncertain | Ask for source or mark needs-calibration | Hiding uncertainty |

If only titles are available, state:

```markdown
当前资料状态：

- 已有：书名列表
- 缺少：原文、版本、目录、重点章节
- 可以先做：方法论框架设计、阅读提取模板、Skill 骨架
- 不能直接做：精确引文、逐章来源映射、严格原典校准
```

## Distillability Gate

Before building or optimizing a methodology skill, decide whether the target is worth distilling.

Distill when at least one condition is true:

- The task, judgment, or explanation has repeated three or more times.
- The user repeatedly gives the same instruction to AI.
- The agent repeatedly makes the same class of mistake.
- There is a clear standard for what "good" looks like.
- There are 3-5 high-quality samples, expert traces, or source passages to align with.

Do not distill when the task is one-off, too variable to standardize, or already handled well by the base agent.

## Workflow

Follow this six-step distillation loop:

1. Identify the target: clarify or infer the target skill name, source list, problem domain, output language, depth, citation needs, and required artifacts.
2. Collect raw material: create `references/source_map.md`; prefer 3-5 high-quality samples, source passages, expert traces, decision logs, or repeated user feedback over many weak examples.
3. Extract source knowledge: process each source through the five layers below and write concept cards into `references/concept_cards.md`.
4. Extract atomic rules: convert concepts, cases, feedback, and failures into behavior rules, decision rules, and thinking frameworks. Use `references/atomic_rules.md`.
5. Package the skill: merge principles into `references/methodology_matrix.md`, record conflicts in `references/conflict_notes.md`, and generate the final `SKILL.md` as a problem-solving engine.
6. Verify and evolve: run baseline, activated-skill, and delta checks. Use `references/evaluation.md`, then revise vague, conflicting, unsupported, or non-actionable rules.

## Distillation Modes

Choose the mode by available material:

| Mode | Use When | Procedure |
|---|---|---|
| Cold-start distillation | The user has a clear workflow but no skill yet | Record the complete workflow, mark decision points and judgment standards, package, test on 3-5 real tasks, revise |
| Sample-based distillation | The user has high-quality outputs or reference passages | Compare commonalities and differences; common points become core rules, differences become conditional rules |
| Feedback distillation | A skill already exists but needs optimization | Collect good/bad outputs, diagnose missing/murky/wrong rules, update rules, re-test |

## Five-Layer Extraction

### 1. Structure Layer

Identify the table of contents, argumentative sequence, central question, opposed misconception, core standard of judgment, and real-world problem class.

Ask:

- What problem does this source try to solve?
- What false view or bad practice does it oppose?
- What judgment standard does it introduce?
- Which real-world situations can it handle?

### 2. Concept Layer

Convert key terms, distinctions, repeated criteria, and oppositions into concept cards. Use `references/concept_cards.md`.

Each card must include source, original meaning, methodology conversion, applicable problems, diagnostic questions, action implication, and common misuse.

After each concept card, add candidate atomic rules in `references/atomic_rules.md`. A useful rule is decidable, unambiguous, and conditional.

### 3. Principle Layer

Turn repeated ideas into judgment rules. A principle is not a slogan; it is a conditional rule.

Use this shape:

```markdown
## Principle Name

Principle:
Problem solved:
Applicable when:
Not applicable when:
Decision rules:
- If ..., prioritize ...
- If ..., avoid ...
Real-world uses: research / work / relationships / projects / learning / decisions
```

### 4. Model Layer

Combine principles into models with input, analysis steps, output, standards, and misuse warnings.

Every model must output a diagnosis, key contradiction or bottleneck, options, action advice, and validation indicators.

### 5. Action Layer

Convert every useful model into an action plan:

- first step
- why this comes first
- low-cost pilot
- risks
- validation indicators
- review method

## Atomic Rules

Use `references/atomic_rules.md` to store rules that future agents can actually follow and evaluators can check.

| Level | Purpose | Example Shape |
|---|---|---|
| Level 1 - Behavior rule | Concrete output behavior | "Keep each diagnostic paragraph under 3 sentences." |
| Level 2 - Decision rule | Conditional choice | "When source status is title-only, build a tentative framework instead of claiming source calibration." |
| Level 3 - Thinking framework | High-value reasoning pattern | "Separate facts, assumptions, and value judgments before applying theory." |

Good methodology skills contain all three levels, but avoid overwhelming the main file with too many rules.

## Methodology Matrix

After processing all sources, build `references/methodology_matrix.md`.

| Module | Sources | Core Concepts | Applicable Scene | Key Question | Action Mode |
|---|---|---|---|---|---|
| Problem diagnosis | B001/B003 | Concept A | Confusion/decision | What is the real problem? | Separate facts and assumptions |
| Contradiction analysis | B002 | Concept B | Stalled project | What is the main constraint? | Locate the binding bottleneck |
| Action testing | B004 | Concept C | Execution difficulty | How can this be verified? | Run a small pilot |

This matrix is the skeleton of the final skill.

## Final Skill Requirements

When generating a concrete methodology skill, include:

- YAML frontmatter with `name` and a trigger-focused `description`
- Chinese skill name when useful
- skill positioning
- theoretical sources and source status
- applicable and non-applicable scenes
- core methodology modules
- overall analysis flow
- fixed output template
- citation and traceability rules
- prohibitions and safety boundaries
- quality checklist
- example problems and at least one short example answer

Use `templates/answer_template.md` for the default answer shape.

For longer skills, keep core principles at 3-7 items, make each phase produce a named artifact, and move long examples or checklists into references.

## Conversion Rules

| Weak Output | Required Conversion |
|---|---|
| "The book emphasizes systems thinking." | When variables affect each other, map the variable relationships before assigning single-point blame. |
| "The author values long-termism." | If short-term gains damage compounding capacity, protect the long-term system; if survival or cash flow is constrained, resolve the short-term bottleneck first. |
| "Theory should connect with practice." | List facts, map theory explanations, identify unexplained parts, run a small test, revise the theory with feedback. |
| "People matter." | In organizational issues, first distinguish ability gaps, incentive misalignment, information asymmetry, and goal conflict; choose actions by cause. |
| Case retelling | Extract background, key variables, decision nodes, success conditions, failure risks, transferable scenes, and non-transferable boundaries. |

## Multi-Source Fusion

When sources agree, merge them into one methodology module, keep all sources, extract shared principles, and note differences.

When sources conflict, do not force unity. Record:

```markdown
## Conflict Record

Theme:
View A:
Source:
Applicable when:
View B:
Source:
Applicable when:
Boundary:
Use A when ...
Use B when ...
Do not mix them because ...
```

## Source Types and Safety Boundaries

For medicine or health books, add boundaries: do not replace clinicians, diagnose, prescribe, or suggest self-medication; help organize symptoms, understand concepts, prepare questions, interpret reports cautiously, and identify urgent care signals.

For astrology, divination, feng shui, fate analysis, or other metaphysical systems, present them as culture, symbolic systems, or decision aids; do not claim certain prediction, replace medical/legal/financial decisions, or encourage dependency.

For philosophy, political theory, ideology, or major thinker systems, avoid extremist mobilization, illegal action advice, hatred, or absolutizing theory. Emphasize historical context and separate description, explanation, and recommendation.

## Prohibitions

Do not:

- write chapter-by-chapter summaries as the final skill
- copy long copyrighted passages
- fabricate citations, page numbers, editions, or source access
- confuse user-provided titles with texts actually read
- treat books as absolute truth
- force incompatible theories into one framework
- produce empty slogans without action steps
- omit validation indicators
- ignore safety boundaries for high-stakes domains

## Quality Check

Before marking a distillation complete, verify the short checklist here and the full checklist in `references/evaluation.md`:

1. The skill can answer real-world problems.
2. It is not merely a book summary.
3. Trigger scenes are clear.
4. The analysis flow is concrete.
5. It separates facts, assumptions, and unknowns.
6. It includes action steps and validation indicators.
7. It preserves source mapping and uncertainty.
8. It avoids long copied source text.
9. It has misuse warnings and safety boundaries.
10. A user can invoke it with `$skill-name 我现在遇到的问题是...`.
11. Atomic rules are decidable, unambiguous, and conditional.
12. The main skill has one clear responsibility and no hard-coded local paths.
13. Baseline vs activated-skill testing shows a visible improvement, or the weak spots are recorded for iteration.

## Output Location Pattern

Create concrete distilled skills in this structure unless the user specifies another path:

```text
.agents/skills/[skill-name]/
├── SKILL.md
├── references/
│   ├── source_map.md
│   ├── concept_cards.md
│   ├── methodology_matrix.md
│   ├── conflict_notes.md
│   ├── atomic_rules.md
│   └── evaluation.md
└── templates/
    └── answer_template.md
```
