# Context Pack Template

A context pack is the minimum reading list for one task or one business domain. It indexes documents and tests. It should not copy large sections of design text.

```markdown
# Context Pack: <Task or Domain>

## Purpose

<Why this context pack exists.>

## Business Domain

<Domain name.>

## Required Reading

- `AGENTS.md`: <specific rules or sections>
- `docs/design/PROJECT_DESIGN.md`: <specific sections>
- `docs/design/modules/<domain>.md`: <specific sections>
- `docs/ARCHITECTURE.md`: <specific sections>
- `docs/TASKS.md`: <task card>
- `docs/QUALITY.md`: <specific testing rules>

## Related Contracts

- <schema, API, Protocol, event, error code, state model>

## Related Tests

- <test file or scenario>
- <fixture or mock>

## Do Not Read By Default

- <large unrelated module design>
- <unrelated historical docs>

## Red Lines

- <must not violate>
- <must not modify>

## Known Risks

- <risk>

## Acceptance Entry Point

- <test command or verification scenario>
```

If a task spans multiple domains, reference multiple context packs explicitly. Do not load all module docs by default.
