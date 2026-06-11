---
name: vibe-coding-framework
description: Use when a user wants to create, review, or apply a general vibe coding framework for human + AI/subagent collaboration, including AGENTS.md rules, project design documents, module design docs, architecture boundaries, task cards, context packs, conflict resolution, and one-domain-at-a-time implementation with tests.
---

# Vibe Coding Framework

Use this skill when the user wants to prepare, review, or use a project-agnostic framework for vibe coding with Codex, AI agents, or subagents.

## Core Rule

Do not produce a full framework by guessing, and do not start by writing design documents. First act like a product manager: explore existing material, interview the user with high-impact questions, clarify goals, users, scenarios, rules, boundaries, and acceptance criteria, then persist the confirmed requirements locally. This is an active discovery loop, not a one-time question list: after each user answer, restate what changed, identify the most important remaining gaps, and ask the next 1-3 questions. Only after requirements are clear enough should you write or refine design documents. Implementation is allowed only after the project has an explicit module sequence and the current module has a complete module design, task card, context pack, and acceptance test entry point.

Coding must follow the module sequence. Implement exactly one module at a time, run that module's acceptance tests, fix failures, update the docs if the implementation changes meaning, and only then move to the next module. If a module cannot be tested, stop and create or clarify the test entry point before continuing.

All project documents created by this skill must be written in Chinese by default so human collaborators can read and maintain them easily. Keep file names and stable technical identifiers in their conventional form, but write headings, explanations, task cards, context packs, assumptions, conflict reports, and delivery notes in Chinese unless the user explicitly requests another language.

## Workflow

1. Identify the mode:
   - Product-manager requirements discovery for a new or unclear project.
   - Create a new framework for a project.
   - Review an existing framework.
   - Add or improve a module design document.
   - Generate a task card or context pack.
   - Enter implementation mode for one business domain.
2. Explore before asking:
   - In an existing repo, inspect README, AGENTS, design docs, task docs, architecture docs, tests, and directory structure.
   - Do not ask questions that can be answered from the repository.
3. Run product-manager discovery before writing design docs:
   - Ask about product intent, users, roles, core scenarios, non-goals, business rules, state lifecycle, errors, acceptance criteria, and tradeoffs.
   - Ask at most 1-3 key questions at a time.
   - Treat discovery as iterative. After each user response, summarize confirmed facts, name the remaining gaps, and ask the next 1-3 highest-impact questions.
   - Do not stop discovery after one round unless the project is trivial or the user explicitly says the requirements are complete.
   - In Plan mode, do not only propose a plan. Use the plan to drive requirements discovery, and request more user input when product or business details are missing.
   - Continue the conversation until you satisfy the Requirements Discovery Gate below.
   - Persist important interview notes to `docs/requirements/DISCOVERY_LOG.md`.
   - Persist confirmed, stable requirements to `docs/requirements/PRODUCT_REQUIREMENTS.md`.
   - Do not generate the full `PROJECT_DESIGN.md` until confirmed requirements are saved locally or the file records explicit assumptions that let work continue.
4. Requirements Discovery Gate:
   - You can restate the product goal, target users, primary workflows, and explicit non-goals.
   - Core business rules, permissions, state/lifecycle, error cases, and acceptance criteria are either confirmed or listed as open questions.
   - Major tradeoffs and risky assumptions are visible to the user.
   - The user has either confirmed the restatement, or the remaining unknowns are documented as non-blocking assumptions in local requirement files.
   - If any gate item is not satisfied, ask another focused round of questions instead of moving to design or implementation.
5. Ask only high-impact questions:
   - Ask about product intent, business rules, public contracts, module boundaries, tests, and tradeoffs.
   - Ask at most 1-3 key questions at a time.
   - Put unresolved but non-blocking assumptions into `Assumptions` or `Open Questions`.
6. Check conflicts before planning or implementation:
   - If the user request conflicts with existing docs, contracts, architecture, task scope, or quality rules, pause.
   - List the conflict, source document, impact, options, and recommendation.
   - Let the user choose. Do not silently override docs or independently reject the request.
7. Build documents progressively:
   - Requirements discovery log and confirmed product requirements first.
   - Global project design first.
   - Business-domain module designs next.
   - Architecture mapping next.
   - Module implementation sequence next.
   - Task cards and context packs next.
   - Quality and decision records as they become relevant.
   - Write all generated project documents in Chinese by default.
8. Before implementation, verify the Document Gate:
   - `AGENTS.md` exists or is drafted.
   - `docs/requirements/PRODUCT_REQUIREMENTS.md` exists or is drafted and contains the confirmed requirements relevant to the current work.
   - `docs/design/PROJECT_DESIGN.md` exists or is drafted.
   - Each planned module has `docs/design/modules/<domain>.md`.
   - `docs/ARCHITECTURE.md` maps modules to code boundaries.
   - `docs/TASKS.md` contains the ordered module queue and task card for the current module.
   - `docs/QUALITY.md` defines the test command or verification scenario for the current module.
   - The current module has a context pack.
9. Implement only after the Document Gate passes for the current module.
10. Follow the Module Acceptance Gate after each module:
   - Run the module acceptance tests.
   - Fix failures inside the module boundary.
   - Record any contract, architecture, or quality doc updates.
   - Do not start the next module until the current module passes or the user explicitly accepts a documented exception.

## When to Read References

- Read `references/framework-files.md` when creating or reviewing the whole document system.
- Read `references/discovery-questions.md` when deciding what to ask next.
- Read `references/discovery-log-template.md` when creating or appending `docs/requirements/DISCOVERY_LOG.md`.
- Read `references/product-requirements-template.md` when creating or updating `docs/requirements/PRODUCT_REQUIREMENTS.md`.
- Read `references/conflict-resolution.md` when a user request conflicts with existing docs or contracts.
- Read `references/module-design-template.md` when writing a domain module design.
- Read `references/task-card-template.md` when writing a task card.
- Read `references/context-pack-template.md` when creating a precise context pack.
- Read `references/implementation-loop.md` before implementing a task.
- Read `references/review-checklist.md` before reporting completion or reviewing another agent's work.

## Implementation Mode Rules

- Write human-facing project documents in Chinese by default, including design docs, task cards, context packs, quality rules, decision records, conflict reports, and delivery notes.
- Requirements first, documents second, code third. If the confirmed requirements, design, architecture, task, quality, and context documents are missing, create or complete them before editing product code.
- Implementation order comes from the module queue in `docs/TASKS.md`. Do not skip ahead unless the user changes the queue.
- One business domain or one explicit business slice per implementation pass.
- No context pack, no implementation.
- Read only the context pack and referenced docs, not the entire design corpus by default.
- Confirm or add tests before implementation.
- Run the domain-level acceptance tests after implementation and do not proceed to another module until they pass.
- Upgrade cross-domain changes to contract changes and request main-agent/user review.
- Report changes, tests, risks, contract changes, and remaining open questions.
