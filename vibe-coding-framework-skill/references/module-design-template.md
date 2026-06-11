# Module Design Template

Use one file per business domain: `docs/design/modules/<domain>.md`.

```markdown
# <Domain Name> Module Design

## Purpose

What business capability this module provides.

## Responsibilities

- <responsibility>
- <responsibility>

## Non-Responsibilities

- <decision or behavior owned elsewhere>
- <integration detail owned elsewhere>

## Core Concepts

| Concept | Meaning | Owner |
|---|---|---|
| <name> | <definition> | <module> |

## Inputs

- <command/query/event/API/Protocol input>

## Outputs

- <result/event/error/API response>

## Public Contracts

List stable fields, methods, events, or schemas other modules may depend on.

## Business Rules

- <deterministic rule>
- <edge condition>

## Error Semantics

| Error | Meaning | Recoverable | Visible To |
|---|---|---|---|
| <error> | <meaning> | <yes/no> | <user/operator/caller> |

## State and Migration

- Persistent state:
- Temporary state:
- Versioning or migration needs:

## Dependencies

- External ports:
- Other module contracts:

## Tests

- Unit tests:
- Contract tests:
- Integration tests:
- Golden scenarios:
- Required fixtures/mocks:

## Open Questions

- <question>

## Assumptions

- <assumption and when to revisit>
```
