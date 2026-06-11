# Conflict Resolution

Use this when the user request conflicts with existing documents, public contracts, architecture boundaries, task scope, or quality rules.

## Conflict Levels

- P0: public contract, core business rule, data safety, security, or state migration conflict. Must stop and ask the user.
- P1: module boundary, task scope, dependency direction, or test strategy conflict. Usually stop and ask with a recommendation.
- P2: naming, directory layout, wording, or minor documentation conflict. The agent may recommend a fix and explain it.

## Conflict Report Template

```markdown
## Conflict Detected

User request:
- <summarize request>

Conflicting source:
- <file and section>

Conflict type:
- <requirement | architecture boundary | public contract | test quality | task scope>

Why it conflicts:
- <short explanation>

Impact:
- <affected modules, contracts, tests, users, or migration>

Options:
1. Use the new request as source of truth, then update docs, contracts, and tests.
2. Keep the existing documents as source of truth, then adjust this request.
3. Treat this as a temporary exception, record risk and effective scope in decisions.

Recommendation:
- <recommended option and why>

Please choose option 1, 2, or 3 before implementation continues.
```

## After User Chooses

- Option 1: update relevant design docs, architecture mapping, task cards, context packs, and tests before or alongside implementation.
- Option 2: adjust the task and do not implement the conflicting portion.
- Option 3: record the exception in `DECISIONS.md`, limit its scope, and add a follow-up to revisit it.

Never silently override documents. Never reject a conflicting user request without explaining the conflict and asking for a choice.
