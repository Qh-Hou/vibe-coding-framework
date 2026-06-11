# Discovery Questions

Use these questions selectively. Do not ask them mechanically. Ask only questions that materially affect design, contracts, module boundaries, testing, or implementation.

Start discovery as a product manager, not as a document generator. Ask 1-3 questions at a time, restate what you learned, name the most important remaining gaps, then ask the next focused round. Persist stable answers to `docs/requirements/PRODUCT_REQUIREMENTS.md`. Use `docs/requirements/DISCOVERY_LOG.md` for interview notes, unresolved ambiguity, and why a question mattered.

## Discovery Loop

Use this loop for every new or unclear project, including Plan mode:

1. Explore existing files before asking.
2. Ask 1-3 high-impact product questions.
3. After the user answers, restate confirmed facts in your own words.
4. Identify which requirement areas are still unclear.
5. Ask the next 1-3 questions, ordered by risk and design impact.
6. Repeat until the Requirements Discovery Gate is satisfied.
7. Save confirmed requirements locally before writing full design docs.

Do not treat a single answer from the user as enough unless it already covers goals, users, workflows, non-goals, business rules, acceptance criteria, and risky tradeoffs.

## Requirements Discovery Gate

Discovery is ready to move into design only when these are clear or explicitly documented as non-blocking assumptions:

- Product goal and success criteria.
- Target users, roles, callers, and permissions.
- Primary workflows and important alternate/error flows.
- Non-goals and out-of-scope behaviors.
- Core business rules and data/state lifecycle.
- External integrations or public contracts.
- Acceptance criteria and minimum test/verification expectations.
- Important risks, tradeoffs, and open questions.

## Project Goal

- What user or business problem must this system solve?
- What is explicitly out of scope?
- What would make the first version successful?
- Who consumes the output: end users, operators, another service, or all of them?

## Users and Callers

- Who initiates the workflow?
- Who receives the final result?
- Are there different roles with different permissions?
- Which actions are human decisions and which are system decisions?

## Business Domains

- What are the natural business areas in this system?
- Which concepts change together?
- Which concepts should be owned by different modules?
- Which domain owns each public decision?

## Module Responsibility

- What does this module own?
- What must this module never decide?
- What inputs does it accept?
- What outputs does it guarantee?
- What errors can it produce?

## Cross-Domain Contracts

- Which modules need to communicate?
- Is the communication a command, query, event, API, or Protocol?
- Which fields are stable public contract fields?
- Who is allowed to change the contract?

## State and Lifecycle

- What state is persistent?
- What state is temporary?
- What state needs migration?
- What is the lifecycle from start to terminal state?

## Errors and Conflicts

- What failures are business outcomes?
- What failures are technical errors?
- What must be visible to users?
- What must be logged only for operators?

## Testing and Acceptance

- What pure business rules can be unit tested?
- Which contracts need contract tests?
- What is the minimum integration path?
- What golden scenarios prevent semantic drift?
- Which external dependencies need mocks and fixtures?

## Subagent Division

- Which business domain can a subagent own independently?
- What files or directories may it modify?
- What files or contracts are forbidden without review?
- What tests must it run before handoff?
