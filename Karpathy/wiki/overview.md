---
type: overview
status: active
created: 2026-05-25
updated: 2026-05-25
tags:
  - llm-wiki
---

# Overview

這個知識庫採用 [[wiki/concepts/LLM Wiki|LLM Wiki]] 架構：原始來源保存在 `raw/`，LLM 維護後的結構化知識保存在 `wiki/`。

## Current Scope

目前這是一個空白但已建好骨架的知識庫。第一階段目標是讓每次新增來源時，Codex 都能穩定完成：

- 建立來源摘要。
- 抽取概念、實體、重要主張與問題。
- 更新既有頁面的交叉連結。
- 記錄變更歷史。
- 維持 `index.md` 可導航。

## Navigation

- 從 [[wiki/index|Wiki Index]] 找頁面。
- 從 [[wiki/synthesis|Synthesis]] 看跨來源的整體理解。
- 從 [[wiki/log|Log]] 看最近做過什麼。
- 從 Obsidian graph view 檢查哪些頁面是 hub、哪些是 orphan。

## Operating Rhythm

建議一次 ingest 一個來源。處理後先閱讀 `wiki/sources/` 裡的新來源頁，再看被更新的概念或實體頁，必要時要求 Codex 調整重點。
