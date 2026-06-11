---
name: vibe-coding-framework
description: Use when a user wants to create, review, or apply a general vibe coding framework for human + AI/subagent collaboration, including AGENTS.md rules, project design documents, module design docs, architecture boundaries, task cards, context packs, conflict resolution, and one-domain-at-a-time implementation with tests.
---

# Vibe Coding Framework

Use this skill when the user wants to prepare, review, or use a project-agnostic framework for vibe coding with Codex, AI agents, or subagents.

## Core Rule

Do not produce a full framework by guessing. Work interactively: explore first, ask high-impact questions, resolve conflicts, then write or refine documents incrementally. During implementation, work on one business domain or one explicit business slice at a time and run the relevant tests.

## Workflow

1. Identify the mode:
   - Create a new framework for a project.
   - Review an existing framework.
   - Add or improve a module design document.
   - Generate a task card or context pack.
   - Enter implementation mode for one business domain.
2. Explore before asking:
   - In an existing repo, inspect README, AGENTS, design docs, task docs, architecture docs, tests, and directory structure.
   - Do not ask questions that can be answered from the repository.
3. Ask only high-impact questions:
   - Ask about product intent, business rules, public contracts, module boundaries, tests, and tradeoffs.
   - Ask at most 1-3 key questions at a time.
   - Put unresolved but non-blocking assumptions into `Assumptions` or `Open Questions`.
4. Check conflicts before planning or implementation:
   - If the user request conflicts with existing docs, contracts, architecture, task scope, or quality rules, pause.
   - List the conflict, source document, impact, options, and recommendation.
   - Let the user choose. Do not silently override docs or independently reject the request.
5. Build documents progressively:
   - Global project design first.
   - Business-domain module designs next.
   - Architecture mapping next.
   - Task cards and context packs next.
   - Quality and decision records as they become relevant.
6. Implement only after the current business domain has enough design, contract, task, context, and test information.

## When to Read References

- Read `references/framework-files.md` when creating or reviewing the whole document system.
- Read `references/discovery-questions.md` when deciding what to ask next.
- Read `references/conflict-resolution.md` when a user request conflicts with existing docs or contracts.
- Read `references/module-design-template.md` when writing a domain module design.
- Read `references/task-card-template.md` when writing a task card.
- Read `references/context-pack-template.md` when creating a precise context pack.
- Read `references/implementation-loop.md` before implementing a task.
- Read `references/review-checklist.md` before reporting completion or reviewing another agent's work.

## Implementation Mode Rules

- One business domain or one explicit business slice per implementation pass.
- No context pack, no implementation.
- Read only the context pack and referenced docs, not the entire design corpus by default.
- Confirm or add tests before implementation.
- Run the domain-level acceptance tests after implementation.
- Upgrade cross-domain changes to contract changes and request main-agent/user review.
- Report changes, tests, risks, contract changes, and remaining open questions.
