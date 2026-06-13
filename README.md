# 书籍方法论蒸馏器 Skill

这个仓库维护一个 Codex Skill：`book-methodology-distiller`。它的目标不是把书做成读书笔记，而是把一本书、一组书、一个理论体系、一个学派或一批文献，蒸馏成 Codex 可以长期调用的方法论 Skill。

核心原则：

```text
source claim -> methodology principle -> diagnostic question -> operating step -> real-world use
```

最终产物应该让 Codex 在面对现实问题时，能够分析、判断、行动、验证和复盘，而不是机械复述书本内容。

## 目录结构

```text
.
├── .agents/
│   └── skills/
│       └── book-methodology-distiller/
│           ├── SKILL.md
│           ├── agents/
│           │   └── openai.yaml
│           ├── references/
│           │   ├── atomic_rules.md
│           │   ├── concept_cards.md
│           │   ├── conflict_notes.md
│           │   ├── evaluation.md
│           │   ├── methodology_matrix.md
│           │   └── source_map.md
│           └── templates/
│               └── answer_template.md
└── distilled-books/
    ├── INDEX.md
    └── _book-template.md
```

## Skill 能做什么

- 判断一个书籍、理论或工作流是否值得蒸馏成 Skill。
- 区分已读取原文、仅有书名、公共知识推断和待校准内容。
- 从书籍中提取核心问题、概念卡、判断原则、分析模型和行动方案。
- 把概念转成可执行的原子规则，包括行为规则、决策规则和思维框架。
- 融合多本书的方法论，并记录冲突观点和适用边界。
- 生成可调用的 Codex Skill 文件结构。
- 用 baseline、Skill 激活测试和 delta 检验持续迭代。

## 使用方式

在支持 skill 调用的 Codex 环境中使用：

```text
$book-methodology-distiller 我想把《书名1》《书名2》《书名3》蒸馏成一个用于解决【具体问题领域】的方法论 Skill。
```

完整输入示例：

```text
$book-methodology-distiller

目标：建立一套项目推进方法论 Skill

书籍列表：
1. 《书名1》
2. 《书名2》
3. 《书名3》

使用场景：
- 我遇到项目卡住时，用这套方法诊断瓶颈
- 我做重大决策时，给出判断流程
- 回答必须包含行动步骤和验证指标

输出要求：
- 生成 Codex Skill
- 包含 SKILL.md
- 包含 source_map.md
- 包含 concept_cards.md
- 包含 atomic_rules.md
- 包含 methodology_matrix.md
- 包含 evaluation.md
```

## 工作流

1. 判断是否值得蒸馏。
2. 建立资料索引。
3. 收集 3-5 个高质量样本或关键文本。
4. 提取结构层、概念层、原则层、模型层和行动层。
5. 生成原子规则。
6. 建立方法论矩阵。
7. 封装为最终 Skill。
8. 用现实问题测试并迭代。

## 书籍收录

`distilled-books/` 用来收录后续要蒸馏的书籍、笔记和输出材料。

建议每个项目使用这样的结构：

```text
distilled-books/
└── [book-or-project-name]/
    ├── source/
    ├── notes/
    ├── extraction_cards.md
    └── outputs/
```

`distilled-books/INDEX.md` 用来维护总索引，`_book-template.md` 用作单书蒸馏记录模板。

## 校验

可用 Codex 的 skill 校验脚本检查结构：

```powershell
python -X utf8 "<path-to-skill-creator>\scripts\quick_validate.py" ".agents\skills\book-methodology-distiller"
```

期望输出：

```text
Skill is valid!
```

## 参考方法论

本 Skill 吸收了以下方法：

- 书籍方法论蒸馏：把书从“内容总结”转成“问题诊断 -> 原则判断 -> 行动方案 -> 验证指标 -> 复盘修正”。
- Skill 蒸馏方法论：把隐性知识压缩成结构化、显性、紧凑的指令包。
- 原子规则三层：行为规则、决策规则、思维框架。
- 验证闭环：baseline 测试、Skill 激活测试、delta 检验和持续迭代。
