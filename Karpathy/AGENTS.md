# LLM Wiki Maintenance Guide

This vault is an LLM-maintained personal wiki. The human curates sources,
asks questions, and decides what matters. The agent maintains the wiki:
summarizing, linking, reconciling contradictions, updating indexes, and logging
changes.

## Layers

- `raw/` is the source-of-truth layer. Treat it as immutable. Read from it, but
  do not rewrite, reorganize, or "clean up" source files unless the human asks.
- `wiki/` is the maintained knowledge layer. The agent owns this layer and may
  create or update pages as part of ingest, query, and lint work.
- `AGENTS.md` is the operating schema. Update it when the human and agent agree
  that the workflow or conventions should change.

## Directory Map

- `raw/incoming/` - newly clipped or dropped files waiting to be processed.
- `raw/sources/` - processed source documents, kept as stable references.
- `raw/assets/` - local images, PDFs, screenshots, and other attachments.
- `wiki/index.md` - content-oriented catalog of the maintained wiki.
- `wiki/log.md` - append-only chronological activity log.
- `wiki/overview.md` - high-level map of the current knowledge base.
- `wiki/synthesis.md` - evolving cross-source thesis and open questions.
- `wiki/sources/` - one page per processed source.
- `wiki/entities/` - people, organizations, projects, places, models, systems.
- `wiki/concepts/` - ideas, terms, techniques, patterns, theories.
- `wiki/claims/` - important claims, evidence, tensions, and contradictions.
- `wiki/questions/` - durable questions, answered analyses, and research trails.
- `wiki/maps/` - topic maps, timelines, comparison tables, and relationship views.
- `wiki/outputs/` - filed artifacts such as briefings, slide drafts, or reports.
- `wiki/_templates/` - page templates used by the agent.
- `inbox/` - human notes, prompts, and rough ideas not yet integrated.
- `tools/` - optional scripts or notes for search, linting, export, or automation.

## Core Principles

1. Build persistent synthesis. Do not merely summarize a source in isolation.
   Integrate it into existing pages and links.
2. Preserve provenance. Important claims should cite source pages or raw files.
3. Prefer small, linked pages over large undifferentiated notes.
4. Keep uncertainty visible. Mark conflicts, weak evidence, stale claims, and
   open questions explicitly.
5. Maintain navigation. Update `wiki/index.md` and `wiki/log.md` whenever the
   wiki changes.
6. Do not invent source facts. If something is inferred, label it as inference.

## Markdown Conventions

Use Obsidian wiki links for internal pages:

```md
[[wiki/concepts/Transformer|Transformer]]
[[wiki/entities/Andrej Karpathy|Andrej Karpathy]]
```

Use standard Markdown links for external URLs and local raw files:

```md
[raw source](../raw/sources/example.md)
```

Recommended frontmatter:

```yaml
---
type: concept
status: seed
created: 2026-05-25
updated: 2026-05-25
tags: []
sources: []
---
```

Page `type` values:

- `source`
- `entity`
- `concept`
- `claim`
- `question`
- `map`
- `output`
- `overview`
- `synthesis`

Page `status` values:

- `seed` - early page, likely incomplete.
- `active` - useful and maintained.
- `needs-review` - may contain stale, conflicting, or weakly sourced material.
- `stable` - mature enough to rely on, though still revisable.

## Source Ingest Workflow

When the human asks to ingest a source:

1. Identify the raw file or URL and assign a stable source title.
2. If the source is in `raw/incoming/`, move or copy only if the human asks.
   Otherwise leave it in place and cite its current path.
3. Read the source carefully. For long files, inspect structure first, then read
   the relevant sections.
4. Create or update a page in `wiki/sources/` using the source template.
5. Extract durable entities, concepts, claims, data points, and questions.
6. Update existing entity and concept pages touched by the source.
7. Create new pages only when the topic is likely to recur or clarifies the
   graph.
8. Add contradictions or tensions to `wiki/claims/` or relevant pages.
9. Update `wiki/index.md`.
10. Append an entry to `wiki/log.md`.

Source pages should answer:

- What is this source?
- Why does it matter to the wiki?
- What are the key claims or facts?
- Which existing pages did it update?
- What should be investigated next?

## Query Workflow

When answering a question against the wiki:

1. Read `wiki/index.md` first.
2. Search the wiki with `rg` for key terms, aliases, and related concepts.
3. Read the most relevant pages before answering.
4. Cite internal pages and source pages in the answer.
5. If the answer creates durable value, offer or create a filed page under
   `wiki/questions/`, `wiki/maps/`, or `wiki/outputs/`.
6. If a filed page is created or updated, update `wiki/index.md` and append to
   `wiki/log.md`.

## Lint Workflow

When asked to lint or health-check the wiki, inspect for:

- orphan pages with no inbound or outbound links.
- pages mentioned in text but not linked.
- concepts that deserve their own page.
- stale claims superseded by newer sources.
- contradictions across pages.
- source pages that were not integrated into entities/concepts.
- index entries that are missing, stale, or too vague.
- log entries that do not follow the standard prefix.

Write lint findings as actionable notes, and update pages directly when the fix
is mechanical and low-risk.

## Log Format

Append-only entries in `wiki/log.md` must start with:

```md
## [YYYY-MM-DD] action | Title
```

Actions:

- `ingest`
- `query`
- `lint`
- `maintenance`
- `schema`

Each entry should include:

- What changed.
- Which pages were created or updated.
- Any unresolved questions or follow-ups.

## Index Format

`wiki/index.md` is organized by category. Each item should include a link, a
one-line description, and optional metadata.

Example:

```md
- [[wiki/concepts/LLM Wiki|LLM Wiki]] - Persistent, LLM-maintained markdown wiki
  pattern. Status: active. Sources: 1.
```

## File Naming

- Use clear human-readable filenames.
- Prefer singular nouns for concept/entity pages.
- Avoid dates in filenames unless the page is inherently chronological.
- Keep raw source filenames unchanged unless the human asks.

## Human Review

The human is responsible for judgment calls:

- which sources are worth ingesting.
- what emphasis matters.
- whether a synthesis feels right.
- which open questions deserve follow-up.

The agent should make reasonable maintenance decisions but flag uncertainty
instead of hiding it.
