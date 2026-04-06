---
description: "Core workflow and operational rules shared across all Developer Agents (NetDeveloper, ReactDeveloper). Apply this when performing any implementation task."
---

# Developer Implementation Workflow & Core Rules

This document outlines the shared expectations, boundaries, and workflow for all developer-based agents (e.g., `NetDeveloper`, `ReactDeveloper`) executing implementation tasks in the workspace.

## Reference Materials

Before starting any implementation, always locate and review the following sources of truth:
- **PRD:** `PRD_Database_manager.md`
- **Architecture:** `Documentations/Architecture/architecture.md`, `Documentations/Architecture/HighLevelArchitecture.md`
- **Features & User Stories:** `Documentations/Features/**`
- **UI Design:** `Documentations/UI/ProjectDesignDirectives.md`, `Documentations/UI/**`

## General Developer Rules

1. **Information Primacy**: Always start from the PRD, relevant feature/user story docs, and UI/architecture specifications. Do not invent new flows, endpoint fields, or UI screens that are not strictly documented.
2. **Component & Module Sizing**: Keep code (React components, API controllers, services) small, focused, and reusable. Avoid "god classes" or massive components with mixed responsibilities.
3. **Convention adherence**: Follow existing folder hierarchies, naming conventions, and patterns found in the workspace. Do not introduce new architectural patterns or major third-party libraries without explicit prior agreement documented by the Architect.
4. **Resiliency**: Implement clear loading states, error handling, and robust input validation. Never leave failure modes unhandled.
5. **No Hardcoding**: Avoid hardcoding environment-specific values, integration URLs, or secrets. Rely on the established runtime configuration mechanisms.
6. **Cross-Boundary Respect**: If your implementation requires changes in a different tier (e.g., a frontend change requiring a backend API tweak), treat it as a cross-cutting concern. Call it out and coordinate with the respective agent (e.g., NetDeveloper) instead of mocking or guessing the change.

## Standard Implementation Workflow

1. **Understand the Requirement**
   - Identify the affected features, user stories, and specifications.
   - Clarify the primary user goals, roles, and success criteria for the task.

2. **Discover Existing Implementation**
   - Review relevant baseline code (endpoints, components, contexts, models, routing).
   - Check corresponding API contracts and data schemas used by the feature.

3. **Design Contracts and Structure**
   - Decide on component hierarchy, object boundaries, and state/logic separation.
   - Plan data loading, mutations, validation semantics, and error/feedback patterns.

4. **Implement the Changes**
   - Ensure you are working in the correct framework scope (e.g., `.NET 10` for backend, `React` for frontend).
   - Add or modify the minimum necessary code to fulfill the requirement.
   - Commit to small, coherent iterations.

5. **Validate and Tidy Up**
   - Ensure the implementation behaves correctly across happy paths, loading, error, and empty states.
   - Update or add automated tests if an existing test structure supports it.
   - Keep the code readable, uniformly spaced, and properly typed.
