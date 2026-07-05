# add-vocabulary

Use this command to add learning vocabulary to PKS v2 without creating duplicates.

Alias: `/add-vocabulary`

## Invocation

```text
add-vocabulary terms="<term list>" source="<source or note>" domain="<domain>"
```

Slash form, if supported by the interface:

```text
/add-vocabulary terms="<term list>" source="<source or note>" domain="<domain>"
```

## Required Behavior

1. Read `AGENTS.md`.
2. Read `04-Reference/Vocabulary/vocabulary-index.md`.
3. Search for each candidate term by term, alias, and canonical ID.
4. Add only terms that are not already represented.
5. If a term already exists, update the existing row only when the new source adds useful context.
6. If the meaning is unclear or unsupported, put the term in `Review Queue` instead of the main table.
7. Create a detail note in `04-Reference/Vocabulary/terms/` only when the term needs longer explanation.
8. Use `07-Templates/vocabulary-term.md` for detail notes.
9. Link related Learning Notes or Reference Notes when useful.
10. Update `CHANGELOG.md` for notable vocabulary system changes.

## Canonical ID Rules

Use `Canonical ID` as the duplicate-prevention key.

- Trim whitespace.
- Use lowercase for English terms.
- Convert English spaces and punctuation to single hyphens.
- Keep Thai terms stable and readable.
- Map aliases to the existing canonical ID.

Examples:

| Input | Canonical ID |
| --- | --- |
| Margin of Safety | margin-of-safety |
| margin safety | margin-of-safety if it means the same concept |
| AI | artificial-intelligence if used as the same concept |

## Duplicate Decision

For each term, decide one of:

- `Add`: create a new row in `Vocabulary Index`.
- `Alias`: add the term as an alias to an existing row.
- `Update`: improve an existing row with better source-aware meaning.
- `Detail`: create or update a term detail note.
- `Review`: add to `Review Queue` because the meaning needs verification.
- `Skip`: ignore because it is already covered and adds no new context.

## Vocabulary Index Row Format

```markdown
| Term | Canonical ID | Aliases | Language | Domain | Short Meaning | Source | Detail Note | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <Term> | <canonical-id> | <aliases> | <language> | <domain> | <meaning> | <source> | [<term>](terms/<canonical-id>.md) | draft |
```

If there is no detail note, leave `Detail Note` blank.

## Guardrails

- Do not invent definitions.
- Prefer meanings from the source context.
- Keep one row per concept, not one row per spelling.
- Do not create detail notes for every term automatically.
- Use relative links.
- Keep filenames in kebab-case for English terms.

## Final Report

End with a short report:

```text
Vocabulary processed:
- Terms received:
- Added:
- Updated:
- Aliases:
- Detail notes:
- Review queue:
- Skipped duplicates:
```
