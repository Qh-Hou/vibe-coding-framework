# Review Checklist

Use after implementation or when reviewing another agent's work.

## Architecture and Boundaries

- Did the change modify public contracts?
- Did it cross a business-domain boundary?
- Did it read or modify another module's internal state?
- Did it put business logic into orchestration, glue, routing, or adapter code?
- Did it introduce circular dependencies?

## Documentation

- Did business semantics change? If yes, was the module design updated?
- Did code boundaries change? If yes, was architecture mapping updated?
- Did acceptance criteria change? If yes, was quality or task documentation updated?
- Was a major tradeoff recorded in decisions?

## Testing

- Were relevant tests added or confirmed before implementation?
- Were assertions weakened?
- Were mocks or fixtures updated consistently?
- Were domain-level acceptance tests run?
- Is any slow or external dependency test intentionally skipped and documented?

## Runtime and Operations

- Were hardcoded environment values introduced?
- Are errors explicit rather than silently swallowed?
- Is sensitive data protected in logs?
- Does state shape change require migration?
- Are request, correlation, or trace identifiers preserved where relevant?

## Handoff

- Is the changed scope clear?
- Are risks and open questions listed?
- Is main-agent review needed for contract or cross-domain changes?
