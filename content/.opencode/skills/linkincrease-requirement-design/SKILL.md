
# Linkincrease Requirement Design

## Purpose

Use this skill as the Linkincrease-specific requirement design assistant. The skill does not duplicate the full knowledge base. It points opencode to the canonical knowledge base and defines how to use it during iteration planning, PRD writing, requirement review, impact analysis, and confirmed requirement ingestion.

Knowledge base path resolution:

```text
1. If LINKINCREASE_KB_PATH is set and exists, use it.
2. Else if the current workspace contains Linkincrease knowledge base files such as metadata/source-roots.csv and docs/README.md, use the current workspace.
3. Else search nearby workspace/repository roots for those marker files.
4. Else ask the user for the knowledge base path or read-only site/repository location.
```

Canonical latest requirement source:

```text
source:thoughts-v2-current
Local path is provided by LINKINCREASE_SOURCE_PATH.
```

Historical product reference source:

```text
source:product-docs-legacy
Local path is provided by LINKINCREASE_PRODUCT_DOCS_PATH.
Use this only for product strategy, user roles, metrics, roadmap, or historical PRD comparison. It must not override confirmed feature rules from source:thoughts-v2-current or docs/.
```

## Core Rules

1. Treat the resolved Linkincrease knowledge base path as the product knowledge authority.
2. Treat `source:thoughts-v2-current` as the primary latest raw requirement source.
3. Treat `source:product-docs-legacy` as secondary historical context only; do not use it to overwrite current rules unless the user confirms the rule is still valid.
4. Use `FlowSpace（流空间）` as the standard product term. Historical source filenames may still contain `SCCS`; preserve them in source references.
5. Do not copy the whole knowledge base into the answer. Search and read only the relevant pages.
6. For strategic or early-stage product work, read the entry pages for product strategy, user roles, and metrics/roadmap before proposing scope.
7. For every requirement, check object, flow, permission, state, data, notification, log, import/export, exception, and multi-end impact.
8. If a rule is unclear or conflicting, record it as a question instead of turning it into a final conclusion.

## When Starting a Requirement

1. Identify the target product end: 运营端, 贸易端, 采集端, or public capability.
2. Identify impacted objects: FlowSpace, 订单, 里程碑, 工单, 资源库, 模板, 自动化, 仪表盘, 报告, 权限, 日志.
3. Resolve the knowledge base path using the path resolution rules above.
4. Search the knowledge base with grep before reading files.
5. For product positioning, user, roadmap, or priority questions, read:
   - `docs/00-产品总览与规划/产品战略与定位.md`
   - `docs/00-产品总览与规划/用户角色与场景.md`
   - `docs/00-产品总览与规划/产品指标与路线图.md`
6. Read only the relevant documents.
7. Produce background, existing rules, likely impact scope, risks, and suggested PRD structure.

Read the detailed knowledge map only when needed:

```text
references/knowledge-base-map.md
```

## When Reviewing a Draft Requirement

1. Read the user's draft or referenced file.
2. Search the knowledge base for matching terms, objects, and source files.
3. If the draft appears to come from historical product documents, compare it against `docs/90-版本历史与来源治理/历史产品文档评估.md` and treat it as reference until confirmed.
4. Check the draft against the design checklist.
5. Return concrete gaps, conflicts, missing decisions, and suggested additions.
6. Prefer actionable PRD edits or section-level suggestions over broad advice.

Read the checklist when doing a review:

```text
references/requirement-checklist.md
```

## When Syncing Confirmed Requirements Back

1. Confirm the requirement is approved or explicitly ready to ingest.
2. If it should become part of the latest source set, ensure it exists under the local path represented by `LINKINCREASE_SOURCE_PATH` / `source:thoughts-v2-current`.
3. If it comes from historical product docs, decide whether to:
   - keep it as `source:product-docs-legacy` reference,
   - promote it into the latest requirement source after confirmation,
   - or record it as a question.
4. Run from the knowledge base root:

```powershell
# Optional: set these only when the source roots are outside the knowledge base repository.
# $env:LINKINCREASE_SOURCE_PATH="<local latest requirement source path>"
# $env:LINKINCREASE_PRODUCT_DOCS_PATH="<local historical product docs path>"
python scripts\scan_source_manifest.py
```

5. Update source ledger, relevant knowledge pages, metadata, questions, and version records.
6. Keep source filenames and `source:` references faithful to the original source files.
7. Validate metadata files and search index after edits.

Read the ingestion workflow when syncing:

```text
references/ingestion-workflow.md
```

## Useful User Prompts

For new design:

```text
基于 Linkincrease 知识库，帮我设计这个迭代功能：{功能描述}
```

For review:

```text
请用 Linkincrease 需求设计 Skill 检查这个需求文档：{文件路径}
```

For impact analysis:

```text
基于知识库分析这个需求会影响哪些模块、权限、状态、通知、日志和数据。
```

For ingestion:

```text
这个需求已经确认，请同步回 Linkincrease 知识库。
```