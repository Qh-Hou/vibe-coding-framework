# Implementation Loop

Use this before and during implementation. The loop is intentionally strict because most semantic drift happens while coding. The agent must not begin product-code edits until the document gate passes for the current module.

## Document Gate

Before coding any module, verify that these documents exist and are consistent enough to guide implementation:

1. `AGENTS.md`: execution discipline, conflict rules, and delivery report format.
2. `docs/design/PROJECT_DESIGN.md`: project goal, non-goals, glossary, global flow, and module index.
3. `docs/design/modules/<domain>.md`: current module responsibility, non-responsibility, rules, contracts, states, errors, fixtures, and tests.
4. `docs/ARCHITECTURE.md`: current module's code boundary, dependency direction, and contract locations.
5. `docs/TASKS.md`: ordered module queue and current module task card.
6. `docs/QUALITY.md`: acceptance test command or verification scenario for the current module.
7. `docs/context-packs/<task-or-domain>.md`: precise reading list for the current module.

If any item is missing, stop implementation and create or clarify the missing document first.

## Module Queue

Implementation must follow the ordered module queue in `docs/TASKS.md`.

- Work on exactly one module at a time.
- Do not start module N+1 until module N passes its acceptance gate.
- If a later module appears easier or more urgent, update the queue with the user before changing order.
- Cross-module work is a contract change unless the task card explicitly authorizes it.

## Steps

1. Select the next module from the ordered module queue.
2. Verify the Document Gate for that module.
3. Read the module's context pack and only the referenced docs by default.
4. Confirm the task card is complete.
5. Check whether the user request conflicts with existing docs, contracts, architecture, or tests.
6. Check whether public contracts are stable.
7. Add or confirm the relevant tests before implementation.
8. Implement the smallest complete business slice inside the module boundary.
9. Run the module acceptance tests.
10. Fix failures before moving on.
11. Check cross-domain impact.
12. Update module design, architecture mapping, task card, quality docs, or decisions if the implementation changed their meaning.
13. Mark the module complete only after acceptance passes.
14. Report changes, tests, risks, contract changes, and open questions.

## Hard Rules

- Documents first, code second.
- The ordered module queue controls implementation order.
- One business domain per implementation pass unless the task explicitly says otherwise.
- No context pack, no implementation.
- No acceptance test or verification entry point, no completion claim.
- A module that has not passed acceptance blocks the next module.
- Cross-domain behavior changes are contract changes.
- User-request/document conflicts must be resolved by user choice before coding.

## Delivery Report

```markdown
## Done

- <change>

## Tests

- <command or scenario>: <result>

## Module Status

- Current module: <name>
- Acceptance gate: <passed/failed/blocked>
- Next module allowed: <yes/no and why>

## Contract Changes

- <none or list>

## Risks / Open Questions

- <none or list>

## Needs Main-Agent Review

- <yes/no and why>
```
