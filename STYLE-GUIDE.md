# Style Guide

This guide keeps the knowledge base readable for both humans and AI assistants.

## File Naming

- Use kebab-case for Markdown files.
- Use `.md` for notes.
- Use `YYYY-MM-DD.md` for dated notes.
- Keep names stable after links exist.

Examples:

- `2026-07-04.md`
- `book-note-linux.md`
- `project-roadmap.md`

## Folder Naming

- Use numbered top-level folders for stable structure.
- Use clear names for subfolders.
- Avoid renaming top-level folders unless the repository structure changes intentionally.

## Frontmatter

Use frontmatter for notes that need metadata.

```yaml
---
title: Example Note
created: 2026-07-04
updated: 2026-07-04
status: draft
tags:
  - example
aliases: []
---
```

Recommended statuses:

- `inbox`
- `draft`
- `evergreen`
- `review`
- `archived`

## Markdown Structure

- Start every note with one `# Title`.
- Use `##` and `###` for sections.
- Keep paragraphs short.
- Use tables for comparisons.
- Use fenced code blocks for commands or examples.
- Prefer relative links.

## Writing Style

- Write clearly.
- Prefer practical examples.
- Preserve source meaning.
- Separate facts from opinions.
- Add assumptions when context is incomplete.

## AI Editing Rules

- Do not invent facts.
- Mark uncertain claims.
- Keep the user's framing.
- Link related notes when useful.
- Avoid duplicate notes.
