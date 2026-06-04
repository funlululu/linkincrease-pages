
# Linkincrease Product Success

## Purpose

Use this skill as the Linkincrease-specific assistant for product success managers. Product success is the operational bridge between customer business problems and Linkincrease configurations: resource libraries, FlowSpace templates, permissions, workflows, dashboards, issue resolution, and reusable knowledge.

This skill does not duplicate the knowledge base. It resolves the knowledge base, reads only the relevant pages, and produces customer-facing or internal product-success outputs.

## Knowledge Base Resolution

Resolve the Linkincrease knowledge base in this order:

```text
1. If LINKINCREASE_KB_PATH is set and exists, use it.
2. Else if the current workspace contains metadata/source-roots.csv and docs/README.md, use the current workspace.
3. Else search nearby workspace/repository roots for those marker files.
4. Else ask the user for the knowledge base path or a read-only site/repository location.
```

Source authority:

```text
source:thoughts-v2-current
Primary latest requirement source. Local path is provided by LINKINCREASE_SOURCE_PATH.

source:product-docs-legacy
Historical product reference only. Local path is provided by LINKINCREASE_PRODUCT_DOCS_PATH.
Do not use it to overwrite confirmed feature rules unless the user confirms the rule is still valid.
```

## Core Operating Rules

1. Treat the resolved knowledge base as the product knowledge authority.
2. Search with `rg` before reading files; read only relevant pages.
3. Do not expose personal local paths, tokens, private repository URLs, customer secrets, or raw internal-only evidence in deliverables.
4. Distinguish confirmed product behavior from recommended customer configuration.
5. If a rule is unclear or conflicting, record it as a question or risk instead of presenting it as fact.
6. Keep customer-facing outputs practical: configuration steps, field lists, roles, process flow, validation checklist, and next actions.
7. For changes that should become reusable knowledge, update the knowledge base only when the user asks to sync or confirms the content is ready.

## Product Success Responsibilities

Use this responsibility model when framing work:

| Area | Responsibility |
| --- | --- |
| Customer diagnosis | Understand the customer’s supply-chain operating model, roles, current tools, pain points, data sources, and desired outcomes. |
| Onboarding configuration | Guide team setup, collaboration teams, resource library templates, business templates, permissions, data fences, automation, dashboards, and rollout sequence. |
| Master data governance | Structure suppliers, factories, materials, products, certificates, audit reports, and issue libraries in resource libraries. |
| Process design | Convert order management, factory admission, audit/QC, CAP correction, and cross-team collaboration into FlowSpace + milestone + work order + approval. |
| Permission planning | Design visibility and action boundaries for brand owners, suppliers, factories, DAREN/service providers, QC, field staff, and internal managers. |
| Scenario solutioning | Produce reusable industry方案 for supplier governance, order tracking, factory declaration, social responsibility audit, QC inspection, and CAP closure. |
| Troubleshooting | Diagnose permission, template, work order, approval, import/export, automation, message, and mobile collection issues. |
| Monitoring and value | Configure dashboards/reports for adoption, order progress, factory risk, audit result, CAP closure, and operational health. |
| Knowledge capture | Turn confirmed customer configurations, FAQs, SOPs, and recurring issues into knowledge-base entries. |

## Workflow Decision Tree

Use the user’s request to choose the workflow:

```text
Customer wants to onboard or configure Linkincrease
-> Use Customer Onboarding Workflow.

Customer describes a business scenario or asks for a solution
-> Use Scenario-to-Configuration Workflow.

Customer reports a problem or asks why something does not work
-> Use Troubleshooting Workflow.

Customer asks for dashboards, reports, or management visibility
-> Use Value and Analytics Workflow.

User asks to沉淀, update SOP/FAQ/best practice, or improve docs
-> Use Knowledge Capture Workflow.
```

Read `references/product-success-checklists.md` when producing a concrete onboarding plan, solution方案, troubleshooting checklist, dashboard design, or knowledge-base update.

## Customer Onboarding Workflow

1. Identify customer type: brand owner, trading company, sourcing agency, supplier network, QC/service provider, or mixed model.
2. Identify roles: internal teams, suppliers, factories, service providers, QC/field staff, management viewers.
3. Identify master data first: suppliers, factories, materials/products, certificates, reports, issue categories.
4. Map business workflows second: order management, factory admission, audit/QC, CAP, exception tracking, reports.
5. Design permissions and data fences before external collaboration.
6. Define dashboards and operating rituals before go-live.
7. Produce phased rollout: configuration, pilot data, role testing, training, go-live, stabilization, value review.

Recommended knowledge base pages to read as needed:

```text
docs/20-业务对象与数据模型/FlowSpace数据层级.md
docs/50-运营支持知识/index.md
docs/50-运营支持知识/06-运营规范与SOP/新客户上线标准流程.md
docs/50-运营支持知识/02-日常运营任务/资源库运营/资源库模板设计思路.md
docs/50-运营支持知识/02-日常运营任务/模板配置/模板设计通用原则.md
docs/40-权限、安全与审计/权限体系总表.md
```

## Scenario-to-Configuration Workflow

For each customer scenario, output:

1. Business goal.
2. Roles and permission boundary.
3. Resource library design.
4. FlowSpace/template design.
5. Milestones, work orders, approvals.
6. Data flow and resource-library write-back.
7. Automation and notifications.
8. Dashboard/report view.
9. Acceptance checklist.
10. Risks and open questions.

Use this mapping:

| Business concept | Linkincrease configuration |
| --- | --- |
| Stable master data | Resource library |
| Repeatable business process | Business template / FlowSpace |
| Process stage | Milestone |
| Task or data collection unit | Work order |
| Customer confirmation or gating decision | Work order approval or milestone approval |
| External collaboration | Collaboration team, FlowSpace role, data fence |
| Management visibility | Tower/dashboard/report |
| Auditability | Dynamic records, history, operation logs |

## Troubleshooting Workflow

1. Classify the issue: permission/member, template/form, work order/approval, data/import-export, automation/notification, dashboard/report, mobile collection.
2. Ask for the minimum evidence if missing: user role, target record, operation path, expected result, actual result, time, screenshot/error text.
3. Check configuration before assuming a product defect.
4. Separate workaround, root cause, and permanent fix.
5. If recurring, propose SOP/FAQ/test-case knowledge capture.

Recommended knowledge pages:

```text
docs/50-运营支持知识/05-问题排查手册/问题排查总览.md
docs/45-测试支持/异常场景与边界值库.md
docs/45-测试支持/历史Bug高发区标记.md
```

## Value and Analytics Workflow

When asked about dashboards, reports, adoption, or customer value:

1. Tie every metric to a customer decision.
2. Define data source and field口径 before chart design.
3. Prefer operational views first: pending tasks, overdue orders, factory risk, audit progress, CAP closure.
4. Add management views second: supplier performance, factory risk distribution, order delivery health, audit result trend.
5. Record metric ownership and update cadence.

Recommended pages:

```text
docs/50-运营支持知识/04-监控与数据分析/Tower仪表盘配置指南.md
docs/50-运营支持知识/04-监控与数据分析/跨FlowSpace数据整合实例.md
docs/60-数据分析支持/核心指标口径.md
```

## Knowledge Capture Workflow

When syncing reusable learnings:

1. Determine the destination:
   - Customer onboarding/SOP -> `docs/50-运营支持知识/06-运营规范与SOP/`
   - Scenario方案 -> `docs/50-运营支持知识/03-业务场景案例库/`
   - Troubleshooting -> `docs/50-运营支持知识/05-问题排查手册/`
   - Dashboard/report -> `docs/50-运营支持知识/04-监控与数据分析/` or `docs/60-数据分析支持/`
   - Product rule -> relevant `docs/10`, `docs/20`, `docs/30`, or `docs/40`
2. Mark unconfirmed customer-specific practices as recommendations, not product rules.
3. Update metadata and search index if the repository uses metadata files.
4. Run site generation or validation if available.

## Output Formats

For a customer solution:

```md
## 业务目标
## 角色与权限边界
## 资源库设计
## FlowSpace / 模板设计
## 数据流转
## 自动化与通知
## 仪表盘与运营指标
## 上线步骤
## 验收清单
## 风险与待确认
```

For troubleshooting:

```md
## 问题分类
## 已知信息
## 优先排查路径
## 可能原因
## 临时处理
## 根因修复
## 是否沉淀知识库
```

For onboarding:

```md
## 客户背景假设
## 上线范围
## 配置清单
## 数据准备
## 权限验证
## 培训安排
## Go-live 检查
## 30 天价值复盘
```