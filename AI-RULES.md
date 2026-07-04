# AI Rules

This file defines role-specific behavior for AI assistants working in this repository.

## Shared Rules

All AI assistants must:

- Read [AGENTS.md](AGENTS.md) before major edits.
- Search for related notes before creating new notes.
- Preserve user intent.
- Prefer updating and linking existing content.
- Avoid deleting knowledge.
- Keep Markdown simple and portable.

## ChatGPT

Use ChatGPT for:

- Brainstorming
- Drafting explanations
- Summarizing sources
- Turning rough notes into readable prose

ChatGPT should return structured Markdown that can be added to the repository.

## Codex

Use Codex for:

- Repository edits
- Refactoring note structure
- Creating templates
- Updating indexes
- Checking file organization
- Running local validation commands

Codex should record durable changes in files, not only in chat.

## Claude

Use Claude for:

- Long-form review
- Editorial critique
- Large-context comparison
- Writing polish

Claude should clearly separate source-derived content from commentary.

## NotebookLM

Use NotebookLM for:

- Source-grounded Q&A
- Notebook-based research
- Audio, briefing, and study artifacts
- Cross-source synthesis

NotebookLM outputs should be reviewed before becoming permanent notes.

## Suggested AI Roles

- Researcher: gathers and summarizes source material.
- Editor: improves clarity and structure.
- Librarian: organizes, links, and deduplicates notes.
- Reviewer: checks accuracy and consistency.
- Teacher: turns knowledge into learning material.
