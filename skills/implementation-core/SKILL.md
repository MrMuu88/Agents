---
name: implementation-core
description: "Use when: coordinating end-to-end implementation of a feature or user story across backend/frontend with contract-first orchestration, regardless of stack."
---

# Implementation Core Skill (LeadDeveloper)

This skill defines the stack-agnostic orchestration model for LeadDeveloper. It does not prescribe a specific backend technology or contract format.

## Purpose

- Orchestrate implementation end to end without pausing at planning.
- Enforce contract-first execution.
- Delegate stack-specific implementation to specialist developer agents.
- Run verification and correction loops until acceptance criteria are met or a hard blocker is reached.

## Execution model

1. Load implementation context:
- Target feature and user story files.
- Relevant UI specs/prototypes.
- Relevant architecture and data model docs.

2. Detect repository stack from project documentation first:
- Read repository-level `Readme.md` and project-level README files (for example app/server subproject READMEs) to identify runtime model, backend/frontend technologies, and integration boundaries.
- Treat README-declared stack as primary input for adapter selection.
- If README content is missing, outdated, or ambiguous, run Explore to verify actual code structure and available specialist agents.
- If ambiguity remains after README plus code check, ask one targeted clarification question.

3. Select one stack adapter skill:
- Use exactly one active adapter for the implementation context.
- Adapter choice must be consistent with README-derived stack and available specialist agents.

4. Define/refresh the interface contract using the selected adapter:
- Contract artifact and validation rules come from the adapter skill.
- Freeze the contract before implementation delegation.

5. Plan and delegate implementation tasks:
- Backend tasks to the backend specialist agent required by the adapter.
- Frontend tasks to the frontend specialist agent required by the adapter.
- Include references to feature, user story, UI, architecture, and contract sections in each delegation.

6. Integrate and verify:
- Verify backend/frontend alignment against the frozen contract.
- Verify acceptance criteria and error behavior.
- Trigger targeted re-delegation if outputs are incomplete or misaligned.

7. Closeout:
- Return a concise implementation summary (scope, contract changes, backend changes, frontend changes, open follow-ups).

## Authority and boundaries

- Boundaries and guardrails are defined in the active agent file and workspace instructions and must not be duplicated here.
- This skill defines orchestration flow only; enforce the owning agent boundaries as the source of truth.

## Quality checks

- Contract is explicitly identified and versioned/traceable in repository artifacts.
- Backend behavior and frontend consumption match the same contract version.
- Acceptance criteria from the target user story are demonstrably covered.
- Any unresolved risks are listed as explicit follow-up tasks.
