---
type: concept
status: seed
created: 2026-05-25
updated: 2026-05-25
tags:
  - llm-wiki
  - knowledge-management
sources: []
---

# LLM Wiki

## Definition

LLM Wiki 是一種用 LLM 建立和維護個人知識庫的模式。它不只是在查詢時從原始文件中檢索片段，而是讓 LLM 逐步建立一個持久、結構化、互相連結的 markdown wiki。

## Core Pattern

知識庫分成三層：

- `raw/`：不可變的原始來源。
- `wiki/`：LLM 生成並持續維護的知識層。
- `AGENTS.md`：告訴 LLM 如何維護這個 wiki 的 schema。

## Key Difference From RAG

RAG 通常在每次問題發生時才檢索與組合答案。LLM Wiki 會把整理後的結論、交叉引用、矛盾、開放問題保存成 wiki 頁面，使知識能在多次 ingest 和 query 中累積。

## Important Operations

- Ingest：讀取新來源，建立來源頁，更新相關概念、實體、主張與索引。
- Query：先讀索引與相關頁，再產出有引用的回答；有價值的回答可以歸檔回 wiki。
- Lint：定期檢查孤兒頁、過期主張、缺失連結、矛盾與資料缺口。

## Related Pages

- [[wiki/overview|Overview]]
- [[wiki/synthesis|Synthesis]]
