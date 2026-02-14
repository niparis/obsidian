---
id: obsidian-agent-grade-vault
type: concept
status: draft
tags: [process, design-brief, obsidian-note-maker]
created: 2026-02-12
updated: 2026-02-12
---

# Obsidian Agent-Grade Knowledge Vault

## Summary
This captures the agent-grade Obsidian system we just implemented: deterministic retrieval, folder routing, metadata-driven filtering, and audited write-back, all tied to the Dream Escape research workflow.

## Core Content
The blueprint:
1. Intent → folder mapping (people, projects, domains, etc.)
2. Metadata filtering to avoid drafts/archived content.
3. Keyword search across file names, ids, tags, headers (max 3 notes).
4. Write flow: slug generation, complete frontmatter, default draft status, git commit/push via hook.
5. Tag tracking via `references/tag-list.md` keeps the vocabulary.

Intent commands (search/read/write/update/archive/list_by_type) respect the schema and vault layout.

## Key Points
- Retrieval returns at most three deterministic results.
- Writing never overwrites evergreen/archived notes and always updates `updated`.
- Governance requires manual promotions (draft → active → evergreen) and monthly audits.
- Future embedding path already mapped by metadata fields for smooth migration.

## Links
[[Stylistic Brief Framework]]
[[Dream Escape Workflow]]
