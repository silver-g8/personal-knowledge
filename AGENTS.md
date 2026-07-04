# AGENTS.md

This repository is designed to be maintained collaboratively by humans and AI assistants.

Every AI agent must follow these rules.

## Primary Objective

Help maintain a clean, organized, reusable knowledge system.

The AI should improve knowledge, not create chaos.

## Repository Principles

1. Never destroy knowledge.
2. Prefer updating existing notes.
3. Avoid duplicate information.
4. Keep Markdown readable.
5. Keep filenames stable.
6. Keep links working.

## AI Responsibilities

The AI may:

- Create notes
- Improve notes
- Refactor notes
- Summarize
- Generate diagrams
- Create templates
- Organize folders
- Link related notes
- Suggest improvements

## AI Should Never

- Delete files automatically.
- Rename folders without permission.
- Break existing links.
- Overwrite user writing.
- Invent facts.
- Create duplicated notes.

## Preferred Workflow

Before creating a new file:

1. Search similar notes.
2. If a similar note exists, update it.
3. Otherwise, create a new note.
4. Link the new note from a relevant index when useful.

## Repo Commands

When the user invokes a short command such as `process-inbox`, `inbox`, `learn-from-source`, `/process-inbox`, `/inbox`, or `/learn-from-source`, read the matching command file in `08-AI/commands/` and follow that workflow.

If the interface does not support slash commands, treat the plain text command name as equivalent.

## Markdown Rules

Always use:

- `# Title`
- `## Heading`
- `### Heading`
- Lists
- Tables
- Code blocks
- Relative links

Never use HTML unless necessary.

## Writing Style

- Clear
- Simple
- Educational
- Beginner friendly
- Accurate
- Avoid unnecessary jargon

## Knowledge Structure

Prefer:

- One idea per note
- Small reusable sections
- Cross-linked notes

Avoid giant documents when a topic can be split cleanly.

## Cross Linking

Whenever possible, create links between related notes.

Knowledge should form a network.

## Folder Rules

- `00-Inbox/`: temporary only.
- `01-Daily Notes/`: do not store permanent knowledge here.
- `02-Learning/`: learning material only.
- `03-Projects/`: active projects only.
- `04-Reference/`: stable reference information.
- `05-Areas/`: long-term responsibilities.
- `06-Resources/`: binary files and downloaded material.
- `07-Templates/`: reusable templates.
- `08-AI/`: prompt engineering, AI workflows, and agent documentation.
- `09-Archive/`: historical content.

## Git Rules

- Use small commits.
- Write meaningful messages.
- Do not rewrite Git history.

## AI Notes

If unsure, ask before changing.

Preserve user intent.

Never optimize by deleting knowledge.

## Long-Term Goal

Build a knowledge system that remains understandable ten years from now.
