# 工作台与FlowSpace入口

## 定位

工作台是贸易端用户进入 Linkincrease 后的主入口，用于承载 FlowSpace 访问、创建 FlowSpace、FlowSpace 分组、常用视图、任务入口和订单日程等日常工作能力。

本页聚焦工作台作为“业务入口”的部分；订单日程、任务中心、常用视图的详细规则见同目录其他页面。

## 核心能力

| 能力 | 说明 |
|---|---|
| FlowSpace列表 | 展示当前用户在当前团队可见的内部 FlowSpace 和协作 FlowSpace |
| FlowSpace搜索 | 支持按 FlowSpace 名称模糊搜索 |
| FlowSpace星标 | 用户可将常用 FlowSpace 标星，星标 FlowSpace 置顶展示 |
| FlowSpace分组 | 团队级维护 FlowSpace 分组，影响工作台中的分组展示 |
| 创建FlowSpace入口 | 有团队设置-创建 FlowSpace 权限的用户可从工作台进入模板中心并创建 FlowSpace |
| 预留事务模块 | 工作台承载常用视图、任务中心、订单日程等事务入口 |

## FlowSpace列表展示规则

每个 FlowSpace 至少展示 FlowSpace 名称。列表先区分用户可见范围，再按星标与创建时间排序。

| 类型 | 可见条件 |
|---|---|
| 内部FlowSpace | 用户拥有团队角色-内部 FlowSpace 管理权限，或已加入该内部 FlowSpace |
| 协作FlowSpace | 用户拥有团队角色-协作 FlowSpace 管理权限，或已加入该协作 FlowSpace |

排序规则：

1. 星标 FlowSpace 排在非星标 FlowSpace 前。
2. 星标 FlowSpace 按标星时间倒序。
3. 非星标 FlowSpace 按 FlowSpace 创建时间倒序。
4. 星标状态按“当前用户 + 当前团队”存储。

## 创建FlowSpace

创建 FlowSpace 从工作台入口进入，整体链路为：

```mermaid
flowchart LR
  A["工作台"] --> B["模板中心"]
  B --> C["模板预览"]
  B --> D["创建FlowSpace"]
  C --> D
  D --> E["创建成功并进入FlowSpace"]
```

创建入口仅对有“团队设置-创建 FlowSpace”权限的用户展示。模板中心展示运营端已启用的业务模板，并按行业分类和发布时间倒序排序。

创建 FlowSpace 时的关键字段：

| 字段 | 规则 |
|---|---|
| FlowSpace名称 | 必填，限制 100 字符 |
| FlowSpace编号 | 必填，限制 1-8 位大写英文，输入小写时自动转大写 |
| 编号唯一性 | 同团队内 FlowSpace 编号不可重复 |
| FlowSpace分组 | 可选择当前团队的 FlowSpace 分组，默认未分组 |

创建成功后：

1. 创建者默认成为该 FlowSpace 成员。
2. 创建者自动配置固定角色“业务管理员”。
3. FlowSpace 设置-业务角色列表自动生成固定角色“业务管理员”，拥有 FlowSpace 业务角色内全部权限。
4. FlowSpace 设置-更多设置默认生成部分预设订单作废原因。

## FlowSpace分组

FlowSpace 分组用于在工作台组织用户可见的 FlowSpace。分组设置是团队级配置，对团队内所有成员生效，但每个成员只能看到自己有权限查看的 FlowSpace。

| 操作 | 规则 |
|---|---|
| 默认分组 | 未分组，不可编辑、不可删除 |
| 新增分组 | 分组名称必填，限制 20 字符，新分组默认排在最上方 |
| 编辑分组 | 可修改分组名称 |
| 删除分组 | 删除后，该分组下 FlowSpace 移入未分组 |
| 移入分组 | FlowSpace 可移动到除当前分组外的其他分组 |
| 排序 | 分组可拖拽排序，FlowSpace 可拖拽移动 |

分组查看规则：

1. 固定展示“所有FlowSpace”tab，包含当前用户可见权限内所有 FlowSpace。
2. 可切换到某个细分分组。
3. 在“所有FlowSpace”tab 中可按分组显示，默认勾选。
4. 分组排序按分组设置中的顺序。
5. 每个分组内按星标、非星标和 FlowSpace 创建时间排序。
6. 当前用户无可见 FlowSpace 的分组隐藏。
7. 前端记住当前用户最后一次“按分组显示”勾选状态。

## 关联页面

- [从模板到FlowSpace](../30-业务流程/从模板到FlowSpace.md)
- [业务模板](../20-业务对象/业务模板.md)
- [团队权限](../40-权限与安全/团队权限.md)
- [订单日程与任务中心](./订单日程与任务中心.md)
- [常用视图与视图设置](./常用视图与视图设置.md)

## 来源

- `source:thoughts-v2-current/v2.0.x/贸易端/【贸易端】【工作台】工作台、创建SCCS、SCCS分组.md`

