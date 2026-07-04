# learn-from-source

Use this command to turn one NotebookLM source into PKS learning material.

The command asks NotebookLM a standard set of focused questions, stores the raw synthesis in `00-Inbox/`, then prepares the material for Learning Notes under `02-Learning/`.

Alias: `/learn-from-source`

## Default Inputs

Use these defaults unless the user provides different values.

| Input | Value |
| --- | --- |
| Notebook ID | `8924ac68-2ca6-46f1-b454-42ea2924fce6` |
| Source ID | `099f074a-7d58-4070-b2bc-aa1800719ab5` |
| Language | Thai |
| Output folder | `00-Inbox/` |
| Learning template | `07-Templates/learning-note.md` |

## Invocation

```text
learn-from-source topic="<topic>"
```

Slash form, if supported by the interface:

```text
/learn-from-source topic="<topic>"
```

Optional fields:

```text
learn-from-source notebook="<notebook-id>" source="<source-id>" topic="<topic>" category="<category>"
```

Slash form:

```text
/learn-from-source notebook="<notebook-id>" source="<source-id>" topic="<topic>" category="<category>"
```

## Required Behavior

1. Read `AGENTS.md`.
2. Verify NotebookLM auth before asking questions.
3. Use the explicit NotebookLM ID and source ID.
4. Ask NotebookLM using the prompt files in `08-AI/prompts/learn-from-source/`.
5. Keep each NotebookLM question focused. Do not combine all questions into one large prompt.
6. Save the raw synthesis into `00-Inbox/YYYY-MM-DD-<topic>-notebooklm.md`.
7. Analyze whether the material should become one Learning Note or several Learning Notes.
8. Search `02-Learning/` for similar notes before creating new files.
9. Use `07-Templates/learning-note.md` for new Learning Notes.
10. Add related topics.
11. Update `CHANGELOG.md`.
12. Commit with a Conventional Commit message only when the user has asked for commit/push or the workflow explicitly includes it.

## NotebookLM Commands

Check auth:

```bash
notebooklm auth check --test --json
```

Ask a prompt file:

```bash
notebooklm ask \
  --notebook 8924ac68-2ca6-46f1-b454-42ea2924fce6 \
  -s 099f074a-7d58-4070-b2bc-aa1800719ab5 \
  --prompt-file 08-AI/prompts/learn-from-source/01-summary.md \
  --json
```

Repeat the `ask` command for each prompt file.

## Prompt Order

1. `01-summary.md`
2. `02-main-concepts.md`
3. `03-key-terms.md`
4. `04-differences.md`
5. `05-practical-actions.md`
6. `06-learning-note-plan.md`
7. `07-related-topics.md`

## Raw Inbox Output

Create a Markdown file in `00-Inbox/` with this structure:

```markdown
# <Topic> - NotebookLM Source Synthesis

---
title: <Topic> - NotebookLM Source Synthesis
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: inbox
tags:
  - notebooklm
  - learning
source:
  notebook_id: 8924ac68-2ca6-46f1-b454-42ea2924fce6
  source_id: 099f074a-7d58-4070-b2bc-aa1800719ab5
---

## Summary

## Main Concepts

## Key Terms

## Differences From Previous Methods

## Practical Actions

## Learning Note Plan

## Related Topics

## Source Caveats
```

## Learning Note Output

When the source is ready to become permanent knowledge, create notes under:

```text
02-Learning/<category>/<topic>/
```

If the category is unclear, use:

```text
02-Learning/AI/
```

Prefer multiple focused notes over one large note when the source contains separate reusable ideas.

## Duplicate Check

Before creating new Learning Notes:

```bash
rg -n "<topic>|<related keyword>" 02-Learning 04-Reference 08-AI
```

Decide one of:

- `Merge`: combine with an existing note.
- `Append`: add a section to an existing note.
- `Create New`: create a new focused Learning Note.
- `Defer`: keep in `00-Inbox/` until the user decides.

## Guardrails

- Do not invent facts beyond NotebookLM output.
- Preserve caveats when NotebookLM source coverage is weak.
- Keep source-derived content separate from AI commentary.
- Do not delete raw inbox files unless the user explicitly approves.
- Use relative links.
- Keep filenames in kebab-case.

## Final Report

End the workflow with a short report:

```text
NotebookLM source processed:
- Notebook:
- Source:
- Raw inbox file:
- Learning notes created:
- Existing notes updated:
- Duplicate handling:
- Related topics:
- Open questions:
- Commit:
```
