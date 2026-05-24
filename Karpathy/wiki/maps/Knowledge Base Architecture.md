---
type: map
status: active
created: 2026-05-25
updated: 2026-05-25
tags:
  - llm-wiki
  - architecture
sources:
  - "[[wiki/concepts/LLM Wiki]]"
---

# Knowledge Base Architecture

## Three Layers

```mermaid
flowchart LR
  human["Human\nsources, questions, judgment"]
  raw["raw/\nimmutable sources"]
  schema["AGENTS.md\nmaintenance schema"]
  wiki["wiki/\nLLM-maintained knowledge"]
  obsidian["Obsidian\nreading, graph, review"]

  human --> raw
  human --> schema
  schema --> wiki
  raw --> wiki
  wiki --> obsidian
  obsidian --> human
```

## Operations

```mermaid
flowchart TB
  ingest["Ingest\nnew source"]
  source["wiki/sources/\nsource page"]
  pages["entities, concepts,\nclaims, questions"]
  index["wiki/index.md"]
  log["wiki/log.md"]
  query["Query\nanswer from wiki"]
  filed["Filed answer\nquestion/map/output"]
  lint["Lint\nhealth check"]

  ingest --> source
  source --> pages
  pages --> index
  ingest --> log
  query --> index
  query --> pages
  query --> filed
  filed --> index
  filed --> log
  lint --> pages
  lint --> index
  lint --> log
```

## Design Notes

- `raw/` protects provenance.
- `wiki/` accumulates synthesis.
- `AGENTS.md` keeps future LLM sessions disciplined.
- `wiki/index.md` is the first navigation surface.
- `wiki/log.md` preserves the history of how the wiki evolved.

