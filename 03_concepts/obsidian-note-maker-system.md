---
id: obsidian-note-maker-system
type: concept
status: draft
tags: [process, design-brief, obsidian-note-maker]
created: 2026-02-12
updated: 2026-02-12
---

# Obsidian Note Maker Skill System

## Summary
This skill enforces an agent-grade Obsidian vault with deterministic retrieval, folder-based routing, and metadata-first write-back. It now maps intents to folders, validates strict frontmatter, and commits every note so we keep a transparent history before we ever add embeddings.

## Core Content
The workflow:
1. Intent → folder mapping (people, projects, domains, etc.)
2. Metadata filtering to avoid drafts/archived content.
3. Keyword search across file names, ids, tags, headers.
4. Write flow ensures slug generation, required frontmatter, draft status, plus git commits/push.
5. Tag tracking via `references/tag-list.md` keeps the vocabulary.

Commands include search/read/write/update/archive/list_by_type, all of which respect the schema and the vault layout.

## Key Points
- Retrieval returns at most three notes and respects deterministic filters.
- Writing never overwrites evergreen or archived notes and always updates `updated`.
- Governance requires human promotions (draft → active → evergreen) and monthly audits.
- Future path is embeddings after parsing headers; schema already supports vector metadata.

## Links
[[Stylistic Brief Framework]]
[[Dream Escape Workflow]]
