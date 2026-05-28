# Knowledge Base Map

Knowledge base root resolution:

```text
1. LINKINCREASE_KB_PATH
2. Current workspace if it contains metadata/source-roots.csv and docs/README.md
3. Nearby workspace/repository roots containing those marker files
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
| Requirement design workflow | `docs/00-产品总览与规划/迭代需求设计工作流.md` |
| Product strategy and positioning | `docs/00-产品总览与规划/产品战略与定位.md` |
| User roles and scenarios | `docs/00-产品总览与规划/用户角色与场景.md` |
| Product metrics and roadmap | `docs/00-产品总览与规划/产品指标与路线图.md` |

## Product Ends

| End | Files |
|---|---|
| 运营端 | `docs/10-功能模块详情/运营端.md` |
| 贸易端 | `docs/10-功能模块详情/贸易端.md` |
| 采集端 | `docs/10-功能模块详情/采集端.md` |
| Cross-end data relationship | `docs/10-功能模块详情/三端数据关系.md` |
| Account and personal center | `docs/10-功能模块详情/账号与个人中心.md` |

## Objects

| Object | Files |
|---|---|
| FlowSpace | `docs/20-业务对象与数据模型/FlowSpace.md` |
| Team and collaboration team | `docs/20-业务对象与数据模型/团队与协作团队.md` |
| Order | `docs/20-业务对象与数据模型/订单.md` |
| Milestone | `docs/20-业务对象与数据模型/里程碑.md` |
| Work order and approval | `docs/20-业务对象与数据模型/工单与批复.md` |
| Resource library | `docs/20-业务对象与数据模型/资源库.md` |
| Business template | `docs/20-业务对象与数据模型/业务模板.md` |
| Resource library template | `docs/20-业务对象与数据模型/资源库模板.md` |

## Flows

| Flow | Files |
|---|---|
| Template to FlowSpace | `docs/30-业务流程与产品流程图/从模板到FlowSpace.md` |
| Order lifecycle | `docs/30-业务流程与产品流程图/订单生命周期.md` |
| Work order collection and approval | `docs/30-业务流程与产品流程图/工单采集与批复.md` |
| Cross-team collaboration | `docs/30-业务流程与产品流程图/跨团队协作.md` |
| Resource reference and sync | `docs/30-业务流程与产品流程图/资源库引用与同步.md` |
| Automation execution | `docs/30-业务流程与产品流程图/自动化执行.md` |
| Mobile collection | `docs/30-业务流程与产品流程图/移动端采集.md` |
| Order reuse relationship | `docs/30-业务流程与产品流程图/订单复用关系.md` |

## Permissions

| Need | Files |
|---|---|
| Permission overview | `docs/40-权限、安全与审计/权限体系总表.md` |
| Team permissions | `docs/40-权限、安全与审计/团队权限.md` |
| FlowSpace role permissions | `docs/40-权限、安全与审计/FlowSpace业务角色权限.md` |
| Collaborative FlowSpace permissions | `docs/40-权限、安全与审计/协作FlowSpace权限.md` |
| Data fence | `docs/40-权限、安全与审计/数据围栏.md` |
| Resource permissions | `docs/40-权限、安全与审计/资源库权限.md` |
| Dashboard and report permissions | `docs/40-权限、安全与审计/仪表盘与报告权限.md` |

## Configuration, Notification, Display, Audit

| Area | Folder |
|---|---|
| Form, template, formulas, import/export | `docs/50-运营支持知识/` |
| Messages, mail collaboration, automation | `docs/60-数据分析支持/` |
| Workbench, views, dashboard, reports | `docs/70-产品维护知识/` |
| Logs, tracking, history, snapshots | `docs/80-架构与技术方案/` |
| Source, questions, version records | `docs/90-版本历史与来源治理/` |
| Historical product document evaluation | `docs/90-版本历史与来源治理/历史产品文档评估.md` |

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
