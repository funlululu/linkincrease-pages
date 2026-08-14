# Product Manager Workflows

## 1. Product Question Classifier

Use this classifier before searching deeply.

| User input pattern | Primary workflow | First documents to check |
| --- | --- | --- |
| 客户说“想提效、想管理、想看进度” | Requirement clarification | `docs/00-产品总览与规划/用户角色与场景.md`, `docs/50-运营支持知识/08-工作技能/客户场景诊断.md` |
| 想新增字段、状态、按钮、页面、筛选 | Impact and scope | `docs/20-业务对象与数据模型`, `docs/40-权限、安全与审计` |
| 要写 PRD 或评审需求 | PRD framing | `docs/00-产品总览与规划/迭代需求设计工作流.md`, then `linkincrease-requirement-design` |
| 问为什么这样做、是否要做 | Decision record | `docs/70-产品维护知识/决策记录.md`, `docs/70-产品维护知识/产品原则.md` |
| 一堆客户反馈、周报、会议纪要 | Feedback synthesis | `docs/70-产品维护知识/客户反馈.md`, `docs/70-产品维护知识/需求池.md` |
| 想让知识库更好用 | Product knowledge loop | `docs/90-版本历史与来源治理/知识资产地图.md`, `AGENTS.md` |

## 2. Demand Discovery Questions

Ask only the questions that change the answer.

| Question | Why it matters |
| --- | --- |
| 谁在什么场景下遇到这个问题？ | Determines user role and product end. |
| 现在怎么做，卡在哪里？ | Separates product gap from SOP/configuration gap. |
| 期望系统帮他减少什么？ | Defines value and success metric. |
| 涉及哪些对象和数据来源？ | Determines model and migration impact. |
| 谁能看、谁能改、谁要确认？ | Determines permission and approval design. |
| 是否已有客户配置或历史需求类似？ | Avoids duplicate capability and captures precedent. |
| 这个需求不做会怎样？ | Helps priority and risk judgment. |

## 3. Impact Analysis Output

Use this structure for fast scope review:

```md
## 结论
一句话说明建议推进、暂缓、拆分还是转配置/SOP。

## 影响范围
| 维度 | 是否影响 | 说明 | 待确认 |
| --- | --- | --- | --- |
| 产品端 |  |  |  |
| 业务对象 |  |  |  |
| 流程状态 |  |  |  |
| 权限/数据围栏 |  |  |  |
| 通知/自动化 |  |  |  |
| 报表/指标 |  |  |  |
| 日志/审计 |  |  |  |
| 导入导出/兼容 |  |  |  |
| 测试回归 |  |  |  |

## 建议拆分
## 需要查证的知识库页面
## 需要更新的知识库页面
```

## 4. Feedback Synthesis

When processing multiple feedback items, classify them as:

| Type | Meaning | Destination |
| --- | --- | --- |
| Product rule gap | Existing behavior unclear or wrong | Product rule page + requirement pool |
| Configuration/SOP gap | Can be solved by setup or training | `docs/50` SOP/FAQ/playbook |
| Data/permission issue | Visibility or operation boundary unclear | `docs/40` + troubleshooting |
| Analytics need | Customer wants visibility or metrics | `docs/60` |
| Strategic signal | Repeated pain across customers | Product roadmap / decision record |
| One-off project practice | Useful only for one customer | Customer note, not authority page |

## 5. Weekly PM Review

Use this once a week:

```md
## 本周产品信号
## 已确认应入库内容
## 应转需求池的问题
## 应沉淀成 FAQ/SOP/Skill 的内容
## 需要做决策记录的取舍
## 旧文档需更新或废弃
## 下周产品动作
```

## 6. Capability Boundary Reminders

Avoid keyword overfitting:

| Keyword | Do not assume | Need evidence |
| --- | --- | --- |
| CAP | Any issue equals CAP | Corrective action, defect closure, root cause, preventive action |
| 供应商治理 | Any supplier data equals governance project | Lifecycle, admission, evaluation, risk, accountability |
| 仪表盘 | Any management concern requires dashboard | Repeated decision, stable metric, clear data source |
| 自动化 | Any manual step should be automated | Repeated trigger, stable rule, owner, failure handling |
| 权限 | Any “看不到” is permission defect | User role, data scope, collaboration team, target record |
| 资源库 | Any list is resource library | Stable master data reused across flows |
