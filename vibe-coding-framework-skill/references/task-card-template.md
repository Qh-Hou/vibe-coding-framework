# Task Card Template

Use task cards to hand work to an agent or subagent without giving it the whole project context.

```markdown
# Task: <Title>

## Goal

<One concrete outcome.>

## Business Domain

<Domain name from module design docs.>

## Context Pack

<docs/context-packs/<name>.md>

## Must Read

- <specific module design section>
- <architecture section>
- <contract file or doc>
- <test file>

## Allowed Modifications

- <file or directory>
- <file or directory>

## Forbidden Modifications

- <file, directory, contract, or module>
- <behavior not in scope>

## Input Contract

<What this task receives or depends on.>

## Output Contract

<What this task must produce or preserve.>

## Acceptance Tests

- <test command or scenario>
- <test command or scenario>

## Out of Scope

- <explicitly excluded behavior>

## Conflict Checks

- Does this change public contracts?
- Does this cross module boundaries?
- Does this require design or architecture doc updates?

## Main-Agent Review Required

- <yes/no, and why>
```

A task is not ready if it lacks allowed modifications, forbidden modifications, acceptance tests, or a context pack.
