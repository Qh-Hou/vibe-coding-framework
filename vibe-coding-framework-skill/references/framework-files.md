# Framework Files Reference

This reference explains the document system for a project using the vibe coding framework.

## Language Rule

All human-facing project documents created from this framework should be written in Chinese by default. Keep file paths, commands, API names, schema fields, code identifiers, and external protocol names unchanged, but write the actual headings, explanations, rules, task cards, context packs, assumptions, risks, and decision records in Chinese unless the user explicitly asks for another language.

## `AGENTS.md`

Purpose: AI execution discipline and hard rules.

Contains:
- Source-of-truth priority.
- Startup reading rules.
- Conflict handling rules.
- AI and subagent boundaries.
- Implementation hard rules.
- Test and delivery discipline.

Does not contain:
- Detailed business rules.
- Module-level design.
- Long templates.

## `docs/requirements/DISCOVERY_LOG.md`

Purpose: product-manager discovery notes and interview trail.

Contains:
- Interview date or round.
- User intent and original wording summarized in Chinese.
- Agent understanding and restatement.
- Confirmed requirements from that round.
- Open questions and unresolved assumptions.
- Conflicts, tradeoffs, and next questions.

Does not contain:
- Final architecture decisions.
- Full module design.
- Implementation details unless they materially constrain requirements.

## `docs/requirements/PRODUCT_REQUIREMENTS.md`

Purpose: confirmed product requirements source of truth before design documents are created.

Contains:
- Product goal and non-goals.
- Users, roles, callers, and external systems.
- Core scenarios and user flows.
- Functional requirements.
- Non-functional requirements.
- Business rules and constraints.
- Acceptance criteria.
- Open questions, assumptions, and requirement change log.

Does not contain:
- Long interview transcript.
- Code boundary mapping.
- Task-level implementation instructions.

## `docs/design/PROJECT_DESIGN.md`

Purpose: global project design and index.

Contains:
- Link to `docs/requirements/PRODUCT_REQUIREMENTS.md`.
- Goals and non-goals.
- Users, callers, and external systems.
- Core workflow overview.
- Global glossary.
- Global lifecycle or state overview.
- Index of module design docs.
- Global error semantics and acceptance scenario index.

Does not contain:
- All module details.
- Implementation file inventories.
- Task-level instructions.

## `docs/design/modules/<domain>.md`

Purpose: source of truth for one business domain.

Contains:
- Domain responsibility and non-responsibility.
- Core concepts, entities, rules, states, errors.
- Inputs, outputs, and public contracts.
- Persistence and migration requirements.
- Tests and fixtures.

Use one document per business domain. Do not split by technical layer unless the domain itself is technical.

## `docs/ARCHITECTURE.md`

Purpose: map design to implementation boundaries.

Contains:
- Layering and dependency direction.
- Domain-to-directory mapping.
- Domain-to-design-doc mapping.
- Location of public contracts, ports, events, errors.
- Orchestration-layer rules.
- Cross-domain change process.

It references module design docs instead of copying their business rules.

## `docs/TASKS.md`

Purpose: task cards and subagent division.

Each task card must state:
- Goal.
- Business domain.
- Product requirement references.
- Context pack.
- Allowed modifications.
- Forbidden modifications.
- Input and output contracts.
- Acceptance tests.
- Out of scope.
- Main-agent review points.

## `docs/QUALITY.md`

Purpose: quality, testing, operations, and debugging rules.

Contains:
- Test layers.
- Fixture and mock requirements.
- Golden path scripts.
- Configuration rules.
- Explicit error handling.
- State migration rules.
- Logging and redaction.
- Merge acceptance standards.

## `docs/DECISIONS.md`

Purpose: decision log for important tradeoffs.

Each record should include:
- Date.
- Decision.
- Context.
- Chosen option.
- Rejected options.
- Impact.
- Revisit condition.

## `docs/context-packs/<task-or-domain>.md`

Purpose: precise context entry point for a task or domain.

Context packs should index, not duplicate, large docs. They list the exact requirement sections, design sections, contracts, and tests an agent must read for the task.
