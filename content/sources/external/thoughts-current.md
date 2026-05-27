# 所思最新需求源接入说明

## 定位

`最新需求源（source:thoughts-v2-current）` 是从所思在线导出的最新需求文档目录，作为 Linkincrease 知识库的最新来源层。

维护人本地目录由环境变量 `LINKINCREASE_SOURCE_PATH` 指定，知识库仓库和只读站点只展示来源标识，不展示本机绝对路径。

当前知识库根目录下的旧 `需求文档/` 不再保留，也不作为来源维护对象。

## 来源层分工

| 来源 | 角色 | 使用方式 |
| --- | --- | --- |
| `最新需求源（source:thoughts-v2-current）` | 最新权威来源层 | 通过扫描脚本生成 manifest 和 diff，作为后续更新知识页的依据 |
| `docs/` | 标准知识库正文 | 只沉淀归纳、去重、校验后的稳定口径 |
| `metadata/` | 元数据与治理层 | 管理来源根、来源清单、差异、知识页、检索索引 |

## 同步流程

1. 在 `LINKINCREASE_SOURCE_PATH` 指向的最新需求源本地目录中运行或更新 `thoughts_sync.py`，从所思在线同步最新文档。
2. 回到知识库目录运行：

   ```powershell
   python scripts\scan_source_manifest.py
   ```

3. 查看 `metadata/source-diff.csv`，判断新增、修改、删除的来源文件。
4. 将影响业务口径的变更抽取到 `docs/` 对应知识页。
5. 更新 `metadata/documents.csv`、`metadata/sources.csv` 和 `metadata/search-index.json`。

## 文件说明

| 文件 | 说明 |
| --- | --- |
| `metadata/source-roots.csv` | 外部来源根目录配置 |
| `metadata/source-manifest.csv` | 最新来源文件全量清单，包含版本、端、模块、hash、更新时间 |
| `metadata/source-diff.csv` | 本次扫描相对上次扫描的差异 |
| `scripts/scan_source_manifest.py` | 扫描外部来源并生成 manifest/diff 的脚本 |

## 注意事项

1. 不把 `.thoughts_sync/` 纳入知识库正文或来源 manifest。
2. 不把浏览器缓存、同步状态数据库、临时文件作为需求材料入库。
3. `*_assets/` 图片目录先暂不纳入 manifest；需要本地化截图资产时，再单独建立图片资产清单。
4. 所有标准知识页仍以 `docs/` 为准，来源文件只作为证据和变更输入。
5. 不再维护知识库内的旧 `需求文档/` 目录，避免双来源。
