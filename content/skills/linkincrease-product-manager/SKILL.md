
# Linkincrease Product Manager

## Purpose

Use this skill as the Linkincrease-specific product manager workbench. It turns customer feedback, business scenarios, stakeholder requests, and existing knowledge-base pages into clear product decisions, implementable requirement structures, impact analysis, and knowledge updates.

This skill does not replace `linkincrease-requirement-design` or `linkincrease-product-success`:

| Skill | Use for |
| --- | --- |
| `linkincrease-product-manager` | Clarify product problem, decide scope, assess impact, plan PRD structure, record decisions, and review product knowledge health. |
| `linkincrease-requirement-design` | Produce or review implementation-ready PRDs after the requirement direction is clear. |
| `linkincrease-product-success` | Turn customer scenarios into onboarding/configuration/support outputs. |
| `linkincrease-demo-prototype` | Generate consistent Linkincrease demos or page prototypes only when explicitly requested. |

## Knowledge Base Resolution

Resolve the Linkincrease knowledge base in this order:

```text
1. If LINKINCREASE_KB_PATH is set and exists, use it.
2. Else if the current workspace contains metadata/source-roots.csv and docs/README.md, use the current workspace.
3. Else search nearby workspace/repository roots for those marker files.
4. Else ask the user for the knowledge base path or a read-only site/repository location.
```

Treat `docs/` and `metadata/documents.csv` as the knowledge authority. Treat customer chats, meeting notes, screenshots, and unconfirmed requests as evidence, not product rules, until they are reviewed and recorded.

## Core Rules

1. Start from the product problem, not from a module keyword.
2. Search with `rg` before reading files; read only the pages needed for the current task.
3. Separate product facts, customer-specific practices, assumptions, risks, and decisions.
4. Never convert one customer's workaround directly into a general product rule.
5. For every meaningful product change, check object, flow, permission, data, notification, log, analytics, import/export, compatibility, and test impact.
6. Record unresolved items in `docs/90-版本历史与来源治理/待确认问题.md`.
7. Record durable product tradeoffs in `docs/70-产品维护知识/决策记录.md`.
8. When a request is ready for PRD-level detail, hand off to `linkincrease-requirement-design`.
9. When the request is actually onboarding, configuration, or customer support, hand off to `linkincrease-product-success`.
10. When the user explicitly asks for a demo, HTML prototype, page prototype, interaction sample, or UI mockup, hand off to `linkincrease-demo-prototype` after the product problem and impact scope are understood. Do not include detailed demo visual design in ordinary product analysis.

## Workflow Decision Tree

```text
User gives a vague customer request
-> Use Requirement Clarification Workflow.

User asks whether to do a feature or how big it is
-> Use Impact and Scope Workflow.

User asks to write a PRD
-> Use PRD Framing Workflow, then hand off to requirement-design for full details.

User asks why a product direction was chosen
-> Use Decision Record Workflow.

User asks how to improve PM work with the knowledge base
-> Use Product Knowledge Loop Workflow.

User shares many customer issues or weekly notes
-> Use Feedback Synthesis Workflow.
```

Read `references/product-manager-workflows.md` when producing a concrete PM deliverable, decision record, weekly review, or product knowledge update.

## Requirement Clarification Workflow

Output:

```md
## 我先按这个需求理解
## 业务目标
## 目标用户与场景
## 已知证据
## 需要确认的问题
## 可能影响的对象/流程/权限/数据
## 暂不进入范围
## 下一步建议
```

Prioritize questions that change scope, data model, permissions, workflow, or acceptance criteria.

## Impact and Scope Workflow

Use this checklist before judging effort or feasibility:

| Impact area | Check |
| --- | --- |
| Product end | 运营端、贸易端、采集端、公共能力是否受影响 |
| Object model | FlowSpace、订单、里程碑、工单、资源库、模板、字段、附件、报告是否受影响 |
| Process | 创建、编辑、提交、批复、采集、同步、归档、导入导出是否变化 |
| Permission | 角色、协作团队、数据围栏、按钮权限、字段可见性是否变化 |
| Data | 写入来源、引用关系、历史数据、同步规则、口径是否变化 |
| Notification | 消息、邮件、自动化、定时任务、执行日志是否变化 |
| Analytics | 仪表盘、报表、统计口径、筛选维度是否变化 |
| Audit | 操作日志、动态、历史记录、系统执行记录是否变化 |
| Compatibility | 旧模板、旧数据、客户配置、移动端版本是否兼容 |
| Test | 权限测试、异常边界、回归范围、验收标准是否明确 |

## PRD Framing Workflow

For early PRD framing, produce only the structure and open questions unless the user asks for the full PRD.

```md
## 背景与问题
## 目标与非目标
## 用户角色
## 场景流程
## 功能清单
## 产品端设计范围
## 对象与数据规则
## 权限与审计
## 通知与自动化
## 报表与指标
## 验收标准
## 风险与待确认
## 需要同步的知识库页面
```

If full implementation detail is needed, switch to `linkincrease-requirement-design`.

## Decision Record Workflow

Use this when a decision changes product behavior, product scope, implementation priority, object model, permission boundary, analytics口径, or customer-facing explanation.

Write or propose entries using:

```md
## 决策：{标题}

| 字段 | 内容 |
| --- | --- |
| 日期 | YYYY-MM-DD |
| 状态 | proposed / approved / deprecated |
| 背景 |  |
| 选项 |  |
| 最终结论 |  |
| 决策原因 |  |
| 影响范围 |  |
| 关联文档 |  |
| 后续复盘条件 |  |
```

## Product Knowledge Loop Workflow

Every product work item should end with one of these outcomes:

| Work residue | Knowledge destination |
| --- | --- |
| Confirmed product rule | `docs/10`, `docs/20`, `docs/30`, or `docs/40` |
| Reusable PM method | `docs/70-产品维护知识/产品经理知识库工作台.md` or a skill |
| Customer support playbook | `docs/50-运营支持知识/08-工作技能` |
| Metric or dashboard口径 | `docs/60-数据分析支持` |
| Product tradeoff | `docs/70-产品维护知识/决策记录.md` |
| Source conflict or uncertainty | `docs/90-版本历史与来源治理/待确认问题.md` |
| Repository/Agent usage rule | `AGENTS.md` or `docs/90-版本历史与来源治理/知识资产地图.md` |

## Output Style

Keep product-manager outputs short, decisive, and traceable. Prefer tables for impact scope and decisions. Put the recommended next action near the top when the user is asking what to do.