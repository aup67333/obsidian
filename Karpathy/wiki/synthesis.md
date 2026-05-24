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
  - "[[wiki/sources/Sell the Truth]]"
---

# Synthesis

## Current Thesis

LLM Wiki 的核心價值是把 LLM 從「每次查詢時重新從文件碎片組裝答案」轉成「持續維護一個會累積的中間知識層」。這個中間層是 markdown wiki：可讀、可改、可連結、可版本控管，也能被 Obsidian 視覺化。

第一篇 ingested 來源 [[wiki/sources/Sell the Truth|Sell the Truth]] 把這個 vault 的內容方向暫時推向「可信溝通、創業、領導、交易與個人動機」。它的核心主張是：真正有效的銷售不是操控別人，而是把自己已經理解、相信且興奮的東西誠實地傳達出去。

## Why It Matters

傳統 RAG 把知識留在原始文件中，查詢時才臨時檢索與組合。LLM Wiki 則把整理、交叉引用、矛盾標記、綜合分析提前完成並保存下來。隨著來源增加，wiki 本身會變得更有價值，而不是每次對話都從零開始。

從 [[wiki/sources/Sell the Truth|Sell the Truth]] 開始，這個 wiki 也開始形成一組可累積的實用哲學：可信度比技巧重要，長期選擇權比短期成交重要，高信任小團隊比低信任大組織更適合追求困難目標，而真正的動機通常來自好奇、自由與 genuine obsession。

## Emerging Themes

- [[wiki/concepts/Credible Sales|Credible Sales]]：銷售是可信、清楚、真實地傳達，而不是讓人感覺被推銷。
- [[wiki/concepts/Rational Empathy|Rational Empathy]]：有效溝通先理解對方的有效理由，再補上自己的立場。
- [[wiki/concepts/Leadership vs Management|Leadership vs Management]]：領導不是下命令，而是讓人真的想做。
- [[wiki/concepts/Stag Hunt|Stag Hunt]]：高信任合作讓人放棄小收益，一起追求更大的 shared upside。
- [[wiki/concepts/Optionality|Optionality]] and [[wiki/concepts/Nonlinear Returns|Nonlinear Returns]]：在 power-law 世界裡，保留時間、聲譽、心安與未來路徑可能比眼前分配更重要。

## Open Questions

- 這個 vault 的主要用途會偏向研究、個人管理、閱讀筆記、還是某個特定主題？
- 來源頁需要多細？短摘要、詳細摘要，還是依來源類型調整？
- 要不要在成熟後加入 Dataview frontmatter 查詢？
- 當 wiki 變大時，要使用 `qmd` 或自建搜尋工具嗎？
- Naval 的 credible sales 模型是否適用於 quota-driven sales，還是主要適用於 founder-led selling、recruiting、fundraising 和高信任合作？
- 「不做 suboptimal deals」和「逃避困難談判」的界線在哪裡？
- 如何判斷自己的 excitement 是 grounded in fundamentals，而不是暫時的情緒或自我說服？

## Watchpoints

- 如果只建立來源摘要但不更新概念/實體頁，wiki 會退化成普通筆記庫。
- 如果沒有穩定引用來源，綜合頁會逐漸失去可查證性。
- 如果 `index.md` 不維護，LLM 之後會更難快速定位已有知識。
