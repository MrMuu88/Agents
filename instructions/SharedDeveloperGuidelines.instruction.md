---
name: SharedDeveloperGuidelines
description: "Use when: implementing application code in any stack to enforce cross-cutting engineering, quality, and collaboration rules."
---

# Shared Developer Guidelines

This file contains cross-stack rules shared by Electron, React, and ASP.NET developer guidance.

## 1. Source of Truth and Collaboration

- Treat Features, User Stories, UI specifications, and Architecture docs as the implementation source of truth; do not infer behavior directly from the PRD.
- Coordinate contract changes (IPC channels, HTTP routes, request/response shapes, status codes) before applying breaking changes.
- Prefer existing project patterns over introducing new frameworks or architectural styles without explicit alignment.

## 2. Layering and Responsibilities

- Keep transport/protocol concerns at boundaries (IPC handlers, controllers, API entrypoints, preload bridges).
- Keep business logic in focused services/domain modules rather than UI components or boundary handlers.
- Keep data access cohesive; avoid ad-hoc persistence logic scattered across unrelated modules.
- Follow existing folder and naming conventions unless a documented architecture change is approved.

## 3. Input Validation and Error Handling

- Validate all external inputs at boundaries (UI input, IPC payloads, HTTP route/query/body, filesystem paths).
- Fail fast with safe, consistent error responses and meaningful logs.
- Never swallow exceptions silently; either handle with context or escalate through centralized handling.
- Do not leak sensitive implementation details in user-facing errors.

## 4. Language and Code Quality

- Use strongly typed models and avoid `any`/`dynamic` unless there is an explicit and justified boundary case.
- Keep units of code small, focused, and testable.
- Prefer async I/O patterns end-to-end; avoid blocking waits on async operations.
- Keep changes incremental and scoped to one concern when possible.

## 5. Security and Configuration

- Do not hardcode secrets, credentials, tokens, or environment-specific endpoints.
- Never log secrets or sensitive credentials.
- Expose only required system capabilities and validate access to privileged operations.
- Follow platform security defaults and least-privilege behavior at integration boundaries.

## 6. Verification Expectations

- Add or update tests for non-trivial behavior where test projects/framework support already exists.
- Ensure lint/format/type rules pass for touched files.
- Verify behavior against relevant acceptance criteria before considering implementation complete.

## 7. Stack-Specific Deep Guidance

- Electron backend and IPC specifics: use `implementation-electron-desktop` skill.
- ASP.NET web/API specifics: use `implementation-webapp-aspnet` skill.
- React renderer implementation specifics: use `implementation-react-renderer` skill.
