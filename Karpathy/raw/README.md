# Raw Sources

這一層保存原始資料，是知識庫的 source of truth。

規則：

- LLM 可以讀取這裡的檔案。
- LLM 不應該改寫、重排或刪除這裡的檔案，除非你明確要求。
- 新資料先放到 `raw/incoming/`。
- 已處理且想長期保存的來源可放到 `raw/sources/`。
- 圖片、截圖、PDF 或網頁附件可放到 `raw/assets/`。

建議：

- 使用 Obsidian Web Clipper 把網頁轉成 markdown。
- 如果文章有圖片，盡量下載到 `raw/assets/`，避免外部連結失效。

