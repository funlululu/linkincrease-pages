# Ingestion Workflow

Use this workflow only when the user says the requirement is confirmed or explicitly asks to sync it into the Linkincrease knowledge base.

## Sources

Knowledge base root resolution:

```text
1. LINKINCREASE_KB_PATH
2. D:\work\daren\Linkincrease-knowledge-base
3. 知识库私有 Git 仓库本地工作区 (legacy fallback)
4. User-provided local path, shared drive path, or repository clone
```

Latest raw requirement source:

```text
source:thoughts-v2-current
Local path: LINKINCREASE_SOURCE_PATH, usually 最新需求源（source:thoughts-v2-current）
```

Historical product document source:

```text
source:product-docs-legacy
Local path: LINKINCREASE_PRODUCT_DOCS_PATH
Use as secondary reference unless a product owner confirms promotion to current requirements.
```

## Steps

1. Confirm the source file path of the approved requirement.
2. If the file should be part of the latest source set, ensure a copy exists under the local path represented by `LINKINCREASE_SOURCE_PATH`.
3. If the file comes from `source:product-docs-legacy`, decide whether it remains historical reference, is promoted into latest source, or becomes a待确认问题.
4. From the knowledge base root, run:

```powershell
$env:LINKINCREASE_SOURCE_PATH="最新需求源（source:thoughts-v2-current）"
$env:LINKINCREASE_PRODUCT_DOCS_PATH="D:\work\daren\项目文档\产品文档"
python scripts\scan_source_manifest.py
```

5. Check `metadata/source-diff.csv` for new, changed, or removed source files.
6. Update `05-需求文档来源台账.md` with the source and target knowledge module when the source is a current requirement.
7. Update relevant knowledge pages under `docs/`.
8. Update metadata:

| File | Update |
|---|---|
| `metadata/documents.csv` | Add or update knowledge document records |
| `metadata/sources.csv` | Add or update source records |
| `metadata/tags.csv` | Add tags when new modules or terms appear |
| `metadata/search-index.json` | Add or update searchable entries |

9. Add unresolved decisions to `99-待办与问题池.md` and `docs/90-来源与待办/待确认问题.md`.
10. For meaningful KB changes, update `docs/90-来源与待办/版本变更记录.md`.
11. Validate:

```powershell
python scripts\scan_source_manifest.py
Get-Content metadata\search-index.json -Raw | ConvertFrom-Json
Import-Csv metadata\documents.csv
Import-Csv metadata\sources.csv
```

## Traceability Rules

- Keep `source:` references exactly aligned with source filenames.
- Preserve historical `SCCS` in source filenames, even when knowledge text uses `FlowSpace`.
- Do not move or delete raw source files unless the user explicitly asks.
- If a confirmed rule conflicts with existing knowledge, update the knowledge page and record the reason or source.
- Do not expose local absolute paths in knowledge pages, site output, or metadata intended for sharing; use `source:` identifiers instead.
