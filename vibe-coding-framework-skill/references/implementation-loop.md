# Implementation Loop

Use this before and during implementation. The loop is intentionally strict because most semantic drift happens while coding.

## Steps

1. Select one business domain or one explicit business slice.
2. Read the task's context pack.
3. Confirm the task card is complete.
4. Check whether the user request conflicts with existing docs, contracts, architecture, or tests.
5. Check whether public contracts are stable.
6. Add or confirm the relevant tests before implementation.
7. Implement the smallest complete business slice.
8. Run the domain acceptance tests.
9. Check cross-domain impact.
10. Update module design, architecture mapping, task card, quality docs, or decisions if the implementation changed their meaning.
11. Report changes, tests, risks, contract changes, and open questions.

## Hard Rules

- One business domain per implementation pass unless the task explicitly says otherwise.
- No context pack, no implementation.
- No acceptance test or verification entry point, no completion claim.
- Cross-domain behavior changes are contract changes.
- User-request/document conflicts must be resolved by user choice before coding.

## Delivery Report

```markdown
## Done

- <change>

## Tests

- <command or scenario>: <result>

## Contract Changes

- <none or list>

## Risks / Open Questions

- <none or list>

## Needs Main-Agent Review

- <yes/no and why>
```
