# Linkincrease Knowledge Base Agent Guide

本文件是给 Codex、Claude Code、OpenClaw 等 AI Agent 使用的知识库入口。使用本仓库前，先按任务类型选择入口，避免把全部文档一次性塞入上下文。

## 必读入口

- [docs/README.md](./docs/README.md)
- [产品能力地图](./docs/00-产品总览与规划/产品能力地图.md)
- [FlowSpace 数据层级](./docs/20-业务对象与数据模型/FlowSpace数据层级.md)
- [权限体系总表](./docs/40-权限、安全与审计/权限体系总表.md)
- [运营支持知识索引](./docs/50-运营支持知识/index.md)
- [产品经理知识库工作台](./docs/70-产品维护知识/产品经理知识库工作台.md)
- [知识资产地图](./docs/90-版本历史与来源治理/知识资产地图.md)

## 使用规则

1. 涉及产品规则，优先查 `docs/10-功能模块详情`、`docs/20-业务对象与数据模型`、`docs/30-业务流程与产品流程图`、`docs/40-权限、安全与审计`。
2. 涉及客户配置、SOP、问题排查、上线方案，优先查 `docs/50-运营支持知识`。
3. 涉及外贸供应链业务背景、行业对象、行业流程、运营专业方案，优先查 `docs/55-外贸供应链行业知识`，先读 [运营专业知识建设路线图](./docs/55-外贸供应链行业知识/运营专业知识建设路线图.md)。
4. 涉及数字供应链成熟度、系统边界、主数据治理、可视化预警、Linkincrease 在供应链系统版图中的定位，优先查 `docs/56-数字供应链专项知识`。
5. 涉及指标、报表、仪表盘、统计口径，优先查 `docs/60-数据分析支持`。
6. 涉及需求澄清、影响范围、产品取舍、客户反馈、产品复盘，优先查 `docs/70-产品维护知识`，并使用 `skills/linkincrease-product-manager`。
7. 涉及需求 Demo、HTML 原型、页面原型、交互样例、UI mockup，使用 `skills/linkincrease-demo-prototype`，并读取 `docs/70-产品维护知识/需求Demo输出规范.md`、`docs/70-产品维护知识/Demo视觉与页面规范.md`、`metadata/ui-patterns.csv`、`metadata/ui-style-tokens.csv`。
8. 涉及需求来源、冲突、历史规则、待确认事项、知识资产治理，查 `docs/90-版本历史与来源治理`。
9. 不确定项必须进入 [待确认问题](./docs/90-版本历史与来源治理/待确认问题.md)，不要把客户实践直接写成产品规则。
10. 知识库不得依赖维护者本地 prototype 目录或个人绝对路径；本地原型稳定后，只沉淀页面模式、视觉 token、规则和验收清单。

## Skill 使用建议

| Skill | 适用任务 |
| --- | --- |
| `skills/linkincrease-product-manager` | 需求澄清、影响范围分析、产品取舍、决策记录、产品周复盘 |
| `skills/linkincrease-requirement-design` | PRD 写作、需求评审、权限/状态/日志/验收标准设计 |
| `skills/linkincrease-product-success` | 客户场景诊断、上线方案、配置方案、运营支持和问题排查 |
| `skills/linkincrease-demo-prototype` | 仅在明确输出 Demo、HTML 原型、页面原型或交互样例时使用 |

## 输出要求

面向产品、实施、客户成功或运营的输出，默认包含：

- 业务目标
- 角色与权限边界
- 资源库设计
- FlowSpace / 模板设计
- 数据流转
- 自动化与通知
- 仪表盘与运营指标
- 上线步骤
- 验收清单
- 风险与待确认

## 知识沉淀规则

1. 已验证流程沉淀到 `docs/50-运营支持知识/08-工作技能` 或 `docs/50-运营支持知识/06-运营规范与SOP`。
2. 客户案例沉淀到 `docs/50-运营支持知识/03-业务场景案例库`。
3. 问题排查沉淀到 `docs/50-运营支持知识/05-问题排查手册`。
4. 产品规则变更同步到对应权威规则页，并更新 `metadata/documents.csv`、版本记录和待确认问题。
5. 新文档必须登记 `metadata/documents.csv`，至少包含 `id`、`title`、`type`、`domain`、`module`、`status`、`path`、`permission`、`tags`、`updated_at`。
6. 重要产品取舍必须进入 [决策记录](./docs/70-产品维护知识/决策记录.md)，并写明背景、选项、结论、影响范围和复盘条件。
7. 页面母版和视觉样式沉淀到 `docs/70-产品维护知识`、`metadata/ui-patterns.csv`、`metadata/ui-style-tokens.csv`；不要把完整 HTML/CSS/JS 或本地 prototype 路径写入共享知识库。
