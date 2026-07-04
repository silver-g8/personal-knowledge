# AI Commands

This folder documents short repo-native commands for PKS v2 workflows.

These are not shell commands. They are instruction contracts for AI assistants working in this repository.

## Available Commands

- [`process-inbox`](process-inbox.md): process `00-Inbox/` as a queue, classify files, create notes, update indexes, archive raw files, and commit when safe.
- [`learn-from-source`](learn-from-source.md): ask NotebookLM a structured question set, save the raw synthesis to `00-Inbox/`, then help turn it into Learning Notes.

## How To Use

Write the command in chat with any required inputs.

Use the plain command name when the interface does not support slash commands.

Example:

```text
process-inbox mode="plan" limit=5
```

```text
learn-from-source topic="NotebookLM Agent Workflow"
```

Slash form is also acceptable in tools that support it:

```text
/process-inbox mode="plan"
```

```text
/learn-from-source topic="NotebookLM Agent Workflow"
```

If inputs are omitted, the assistant should use the defaults documented in the command file when they are still valid.
