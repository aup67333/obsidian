---
type: synthesis
status: seed
created: 2026-05-25
updated: 2026-05-25
tags:
  - synthesis
  - llm-wiki
sources:
  - "[[wiki/concepts/LLM Wiki]]"
---

# Synthesis

## Current Thesis

LLM Wiki 的核心價值是把 LLM 從「每次查詢時重新從文件碎片組裝答案」轉成「持續維護一個會累積的中間知識層」。這個中間層是 markdown wiki：可讀、可改、可連結、可版本控管，也能被 Obsidian 視覺化。

## Why It Matters

傳統 RAG 把知識留在原始文件中，查詢時才臨時檢索與組合。LLM Wiki 則把整理、交叉引用、矛盾標記、綜合分析提前完成並保存下來。隨著來源增加，wiki 本身會變得更有價值，而不是每次對話都從零開始。

## Open Questions

- 這個 vault 的主要用途會偏向研究、個人管理、閱讀筆記、還是某個特定主題？
- 來源頁需要多細？短摘要、詳細摘要，還是依來源類型調整？
- 要不要在成熟後加入 Dataview frontmatter 查詢？
- 當 wiki 變大時，要使用 `qmd` 或自建搜尋工具嗎？

## Watchpoints

- 如果只建立來源摘要但不更新概念/實體頁，wiki 會退化成普通筆記庫。
- 如果沒有穩定引用來源，綜合頁會逐漸失去可查證性。
- 如果 `index.md` 不維護，LLM 之後會更難快速定位已有知識。
