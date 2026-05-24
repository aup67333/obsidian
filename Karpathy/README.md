# LLM Wiki Vault

這是一個依照 **LLM Wiki** 模式建立的 Obsidian 知識庫。

核心分工：

- `raw/` 保存原始來源，是不可變的 source of truth。
- `wiki/` 保存 LLM 維護後的結構化知識、交叉連結、綜合分析與問題追蹤。
- `AGENTS.md` 告訴 Codex 之後每次進來時要怎麼維護這個 wiki。

建議工作方式：

1. 把文章、筆記、PDF、截圖或逐字稿放進 `raw/incoming/`。
2. 告訴 Codex：「請 ingest `raw/incoming/檔名`」。
3. Codex 會建立來源頁、更新概念/實體頁、補上索引，並在 `wiki/log.md` 留紀錄。
4. 平常閱讀時從 `wiki/index.md`、`wiki/overview.md` 和 Obsidian graph view 開始。

重要入口：

- [[wiki/index|Wiki Index]]
- [[wiki/overview|Overview]]
- [[wiki/synthesis|Synthesis]]
- [[wiki/log|Log]]

