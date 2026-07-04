# process-inbox

Use this command to process new files in `00-Inbox/` as an inbox queue.

The command analyzes inbox files, classifies them, checks for duplicates, creates or updates knowledge notes, links related topics, updates repository indexes, updates `CHANGELOG.md`, and commits the result when the workflow reaches a safe commit point.

Alias: `inbox`

Slash aliases, if supported by the interface: `/process-inbox`, `/inbox`

## Invocation

```text
process-inbox
```

Process only selected files:

```text
process-inbox files="00-Inbox/example.md, 00-Inbox/another.md"
```

Dry-run mode:

```text
process-inbox mode="plan"
```

Apply mode:

```text
process-inbox mode="apply"
```

Batch mode:

```text
process-inbox mode="apply" limit=10
```

## Default Mode

Use `mode="plan"` by default unless the user explicitly asks to process, create notes, commit, or run the full workflow.

Use `mode="apply"` when the user clearly asks Codex to execute the command end to end.

## Inputs

| Input | Default | Meaning |
| --- | --- | --- |
| `files` | all Markdown files in `00-Inbox/` except `README.md` | Inbox files to process |
| `limit` | `10` | Maximum number of inbox files to process in one run |
| `mode` | `plan` | `plan` produces a report only; `apply` edits files |
| `commit` | `true` in apply mode | Commit after verification |
| `push` | `false` | Push only when the user explicitly asks |
| `archive_raw` | `true` | Move processed raw inbox files to `09-Archive/Inbox/` instead of deleting |

## Required Behavior

1. Read `AGENTS.md`.
2. Read this command file.
3. Run `git status --short --branch`.
4. List target inbox files, sorted by filename.
5. Read each target inbox file.
6. Analyze the document type.
7. Propose a destination category under `02-Learning/`, `04-Reference/`, `05-Areas/`, `03-Projects/`, or `09-Archive/`.
8. Search for duplicate or related notes before creating files.
9. Decide one action per inbox file: `Merge`, `Append`, `Create New`, `Reference`, `Project`, `Archive`, or `Defer`.
10. In `plan` mode, stop after reporting the proposed actions.
11. In `apply` mode, create or update notes according to the action plan.
12. Add frontmatter to new notes.
13. Add related topics and relative links.
14. Update relevant README/index files.
15. Update `CHANGELOG.md`.
16. Move processed raw inbox files to `09-Archive/Inbox/YYYY-MM-DD/` when `archive_raw=true`.
17. Run `git diff --check`.
18. Commit with a Conventional Commit message when verification passes and `commit=true`.
19. Push only if the user explicitly requested push.
20. End with a concise report.

## Batch Rules

- Process at most `limit` files per run.
- Default `limit=10` protects the repo from oversized automated changes.
- If `files` is provided, process only those files, but still stop at `limit`.
- If more files remain after the limit, report them under `Files remaining`.
- Use smaller limits for high-risk inboxes:

```text
process-inbox mode="plan" limit=3
process-inbox mode="apply" limit=3
```

- Use a larger limit only when the inbox files are simple and similar:

```text
process-inbox mode="apply" limit=25
```

## Safety Rules

- Never delete inbox files automatically.
- Do not overwrite user writing.
- Do not rename top-level folders.
- Do not merge into an existing note unless similarity is strong and the merge target is obvious.
- If unsure, choose `Defer` and explain what decision is needed.
- Preserve source caveats and uncertainty.
- Keep raw source material archived after processing.
- Do not invent facts beyond the inbox source.
- For financial, medical, legal, or other high-stakes topics, mark source limits clearly and avoid actionable advice unless the source supports it.

## Classification Guide

| Document Type | Destination | Notes |
| --- | --- | --- |
| Learning source synthesis | `02-Learning/<category>/` | Create one or more Learning Notes |
| Stable facts, glossary, lists | `04-Reference/<category>/` | Create Reference Notes |
| Active work | `03-Projects/<project>/` | Create or update project files |
| Long-term responsibility | `05-Areas/<area>/` | Create or update area notes |
| Daily journal or meeting note | `01-Daily Notes/` | Move only when clearly dated |
| Raw resource or binary description | `06-Resources/` | Link to related Markdown note |
| Obsolete or completed material | `09-Archive/` | Archive with context |
| Unclear material | `00-Inbox/` | Defer |

## Duplicate Check

Search with focused keywords from the inbox file:

```bash
rg -n "<keyword-1>|<keyword-2>|<keyword-3>" 02-Learning 03-Projects 04-Reference 05-Areas 08-AI
```

Use these decisions:

- `Merge`: same topic, same purpose, and existing note should absorb the inbox content.
- `Append`: same topic, but inbox content is a new section or update.
- `Create New`: related but meaningfully distinct topic.
- `Reference`: stable factual material better suited to `04-Reference/`.
- `Project`: active outcome-oriented work.
- `Archive`: no longer active but worth preserving.
- `Defer`: insufficient confidence.

## Learning Note Creation

Use `07-Templates/learning-note.md` for new Learning Notes.

Minimum required sections:

```markdown
# <Title>

---
title: <Title>
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: draft
tags:
  - learning
aliases: []
source:
  inbox: ../../00-Inbox/<source-file>.md
---

## Overview

## Learning Objective

## Source

## Concepts

## Example

## Notes

## Tips

## Questions

## Related

## Next Actions
```

## Reference Note Creation

Use Reference Notes for stable facts, lists, glossary entries, personas, checklists, and reusable frameworks.

Minimum required sections:

```markdown
# <Title>

---
title: <Title>
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: draft
tags:
  - reference
aliases: []
source:
  inbox: ../../00-Inbox/<source-file>.md
---

## Purpose

## Reference

## Caveats

## Related
```

## Raw Inbox Archive

After successful processing in `apply` mode, move each processed raw inbox file to:

```text
09-Archive/Inbox/YYYY-MM-DD/<original-file-name>
```

Do not archive files with `Defer` status.

Update any source links in created notes to point to the archived path.

## Changelog Entry

Add a concise entry under `[Unreleased]`.

Examples:

```markdown
- Processed inbox source into AI learning notes.
- Added reference notes from inbox source.
- Archived processed inbox source.
```

## Commit Message

Use Conventional Commit format.

Examples:

```text
docs(pks): process inbox learning notes
docs(ai): process NotebookLM source notes
docs(reference): add investment reference notes
```

## Example Workflow

User:

```text
process-inbox mode="plan" limit=5
```

Codex:

```text
Inbox files found:
- 00-Inbox/2026-07-04-stock-analysis-using-ai-and-notebooklm-notebooklm.md

Plan:
- Type: Learning source synthesis
- Category: 02-Learning/AI/stock-analysis-using-ai-and-notebooklm/
- Duplicate check: no direct Learning Note duplicates found
- Actions:
  - Create Learning Note: google-gemini-gems-setup.md
  - Create Learning Note: ctfc-prompting-framework.md
  - Create Learning Note: notebooklm-knowledge-integration.md
  - Create Reference Note: 04-Reference/Investment/dr-niwet-vi-persona.md
  - Create Reference Note: 04-Reference/Investment/investment-reading-list.md
  - Update README/index files
  - Update CHANGELOG.md
  - Archive raw inbox file after apply
```

User:

```text
process-inbox mode="apply" limit=5
```

Codex:

```text
Applied:
- Created 3 Learning Notes
- Created 2 Reference Notes
- Updated 4 index files
- Archived 1 inbox source
- Updated CHANGELOG.md
- Commit: docs(pks): process inbox learning notes
```

## Final Report

End with:

```text
Inbox processed:
- Files scanned:
- Files processed:
- Files deferred:
- Files remaining:
- Learning notes created:
- Reference notes created:
- Existing notes updated:
- Raw files archived:
- Duplicate handling:
- Related topics added:
- Changelog:
- Verification:
- Commit:
- Push:
- Open questions:
```
