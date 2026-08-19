
# Linkincrease Demo Prototype

## Purpose

Use this skill only for demo/prototype work. It helps generate consistent Linkincrease page demos by reading the shared knowledge-base rules, style tokens, and page-pattern metadata.

Do not use this skill for ordinary PRD writing, requirement clarification, customer方案, SOP, or product impact analysis unless the user explicitly asks for a demo, prototype, UI mockup, HTML page, or interaction sample.

## Knowledge Base Resolution

Resolve the Linkincrease knowledge base in this order:

```text
1. If LINKINCREASE_KB_PATH is set and exists, use it.
2. Else if the current workspace contains metadata/documents.csv and docs/README.md, use the current workspace.
3. Else search nearby workspace roots for those marker files.
4. Else ask the user for the knowledge base path.
```

Never require a maintainer's local prototype folder or any other local absolute path. Local prototypes can inspire future maintenance, but generated demo rules must come from the shared knowledge base.

## Required Reads

Before generating a demo, read:

1. `docs/70-产品维护知识/需求Demo输出规范.md`
2. `docs/70-产品维护知识/Demo视觉与页面规范.md`
3. `metadata/ui-style-tokens.csv`
4. `metadata/ui-patterns.csv`
5. The relevant product rule pages from `docs/10`, `docs/20`, `docs/30`, `docs/40`, or `docs/60`

## Workflow

1. Identify product end: 运营端、贸易端、采集端 or 公共能力.
2. Identify page type: 列表、详情、配置、设计器、采集、仪表盘、弹窗 or 抽屉.
3. Select the closest pattern from `metadata/ui-patterns.csv`.
4. Apply visual constraints from `metadata/ui-style-tokens.csv`.
5. Preserve required page areas from the selected pattern.
6. Replace only business content, sample data, fields, states, and local interactions needed by the requirement.
7. Validate against the Demo checklist in `需求Demo输出规范.md`.

## Output Rules

- State which UI pattern was used.
- Keep demo copy consistent with Linkincrease terminology, especially FlowSpace.
- Do not include local absolute paths as dependencies.
- Do not invent product rules that are not supported by knowledge pages.
- If no matching pattern exists, use the closest pattern and add a note recommending a new page-pattern entry.
- If producing a PRD and the user did not ask for a demo, do not output visual design sections; only mention demo needs as a lightweight note.

## Handoff

Use with:

| Related skill | When |
| --- | --- |
| `linkincrease-product-manager` | Clarify the product problem or impact before making a demo |
| `linkincrease-requirement-design` | Write implementation-ready PRD after demo direction is confirmed |
| `linkincrease-product-success` | Turn a customer scenario demo into onboarding or configuration方案 |