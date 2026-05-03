---
description: "Workspace-wide rules applied to all Copilot interactions and Custom Agents. Provides cross-cutting architectural constraints and required rule exceptions for specific roles/agents."
---

# Global Project Rules

These rules apply universally to all tools, agents, and implementations within this workspace.

## Strict Boundaries & Role Exceptions

1. **Requirements & Documentation Stability**
   - **Rule**: NEVER modify the PRD, Data Models, UI Specifications, or High-Level Architecture documentation without explicit instruction.
   - **Exception**: This rule is bypassed ONLY if your actively invoked persona is explicitly the `Architect` or `ProductOwner` agent. All developer agents (NetDeveloper, NodeJsDeveloper, ReactDeveloper, LeadDeveloper) must treat the documentation as an immutable source of truth. If a gap is identified, they must raise it as an issue rather than guessing or changing it.

2. **Backend API Contracts**
   - **Rule**: NEVER modify Backend API contracts (routes, request/response shapes, status codes) dynamically while working on frontend or unrelated tasks.
   - **Exception**: This rule is bypassed ONLY if your actively invoked persona is the `NetDeveloper` or `NodeJsDeveloper`, or if explicit coordination with the `LeadDeveloper` is requested. If a frontend change requires a backend change, you must raise it as a cross-cutting concern.

3. **Frontend UI Contracts**
   - **Rule**: NEVER edit Frontend UI code while working on backend tasks to "make it fit". 
   - **Exception**: Bypassed ONLY if the actively invoked persona is `ReactDeveloper` or explicitly orchestrated by `LeadDeveloper`.

4. **Instruction File Adherence**
   - **Rule**: All implementation must adhere strictly to the instruction files that exist in `.github/instructions/*.instructions.md` for this project.
   - **Exception**: There are no exceptions to this rule. All agents must follow the domain-specific guidelines defined in those files.

## Universal Working Style
- Keep changes minimal, coherent, and focused on fulfilling a single documented task or issue at a time.
- Avoid introducing major new frameworks, architectural patterns, or libraries without explicit documented agreement in the architecture notes.
- Prefer small, incremental changes.
- Avoid hardcoding configuration (connection strings, URLs, secrets); rely on existing configuration mechanisms.
