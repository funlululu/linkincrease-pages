# Knowledge Base Map

Knowledge base root resolution:

```text
1. LINKINCREASE_KB_PATH
2. D:\work\daren\Linkincrease-knowledge-base
3. 知识库私有 Git 仓库本地工作区 (legacy fallback)
4. User-provided local path, shared drive path, or repository clone
```

Use these pages as entry points.

## Global

| Need | File |
|---|---|
| Overall product understanding | `01-产品总览.md` |
| Standard terminology | `02-核心概念词典.md` |
| Feature ownership and module map | `03-功能地图.md` |
| Full knowledge architecture | `04-Linkincrease完整知识库架构与内容.md` |
| Source ledger | `05-需求文档来源台账.md` |
| KB engineering architecture | `06-知识库工程架构.md` |
| Open questions | `99-待办与问题池.md` |
| Requirement design workflow | `docs/00-入门/迭代需求设计工作流.md` |
| Product strategy and positioning | `docs/00-入门/产品战略与定位.md` |
| User roles and scenarios | `docs/00-入门/用户角色与场景.md` |
| Product metrics and roadmap | `docs/00-入门/产品指标与路线图.md` |

## Product Ends

| End | Files |
|---|---|
| 运营端 | `docs/10-产品端/运营端.md` |
| 贸易端 | `docs/10-产品端/贸易端.md` |
| 采集端 | `docs/10-产品端/采集端.md` |
| Cross-end data relationship | `docs/10-产品端/三端数据关系.md` |
| Account and personal center | `docs/10-产品端/账号与个人中心.md` |

## Objects

| Object | Files |
|---|---|
| FlowSpace | `docs/20-业务对象/FlowSpace.md` |
| Team and collaboration team | `docs/20-业务对象/团队与协作团队.md` |
| Order | `docs/20-业务对象/订单.md` |
| Milestone | `docs/20-业务对象/里程碑.md` |
| Work order and approval | `docs/20-业务对象/工单与批复.md` |
| Resource library | `docs/20-业务对象/资源库.md` |
| Business template | `docs/20-业务对象/业务模板.md` |
| Resource library template | `docs/20-业务对象/资源库模板.md` |

## Flows

| Flow | Files |
|---|---|
| Template to FlowSpace | `docs/30-业务流程/从模板到FlowSpace.md` |
| Order lifecycle | `docs/30-业务流程/订单生命周期.md` |
| Work order collection and approval | `docs/30-业务流程/工单采集与批复.md` |
| Cross-team collaboration | `docs/30-业务流程/跨团队协作.md` |
| Resource reference and sync | `docs/30-业务流程/资源库引用与同步.md` |
| Automation execution | `docs/30-业务流程/自动化执行.md` |
| Mobile collection | `docs/30-业务流程/移动端采集.md` |
| Order reuse relationship | `docs/30-业务流程/订单复用关系.md` |

## Permissions

| Need | Files |
|---|---|
| Permission overview | `docs/40-权限与安全/权限体系总表.md` |
| Team permissions | `docs/40-权限与安全/团队权限.md` |
| FlowSpace role permissions | `docs/40-权限与安全/FlowSpace业务角色权限.md` |
| Collaborative FlowSpace permissions | `docs/40-权限与安全/协作FlowSpace权限.md` |
| Data fence | `docs/40-权限与安全/数据围栏.md` |
| Resource permissions | `docs/40-权限与安全/资源库权限.md` |
| Dashboard and report permissions | `docs/40-权限与安全/仪表盘与报告权限.md` |

## Configuration, Notification, Display, Audit

| Area | Folder |
|---|---|
| Form, template, formulas, import/export | `docs/50-模板表单与数据/` |
| Messages, mail collaboration, automation | `docs/60-协作通知与自动化/` |
| Workbench, views, dashboard, reports | `docs/70-展示分析/` |
| Logs, tracking, history, snapshots | `docs/80-日志审计/` |
| Source, questions, version records | `docs/90-来源与待办/` |
| Historical product document evaluation | `docs/90-来源与待办/历史产品文档评估.md` |

## Metadata

| Need | File |
|---|---|
| Knowledge documents | `metadata/documents.csv` |
| Source list | `metadata/sources.csv` |
| Tags | `metadata/tags.csv` |
| Search index | `metadata/search-index.json` |
| Source roots | `metadata/source-roots.csv` |
| Latest source manifest | `metadata/source-manifest.csv` |
| Latest source diff | `metadata/source-diff.csv` |

## Source Authority

| Source | Authority | Use |
|---|---|---|
| `source:thoughts-v2-current` | Primary latest requirement source | Current feature rules, confirmed PRD details, source traceability |
| `source:product-docs-legacy` | Secondary historical reference | Product strategy, user roles, metrics, roadmap, historical PRD comparison |

Do not let `source:product-docs-legacy` override current feature rules unless the user confirms the rule is still valid.
