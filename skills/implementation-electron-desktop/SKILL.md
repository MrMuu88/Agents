---
name: implementation-electron-desktop
description: "Use when: implementing Electron desktop features where Node/Electron backend and renderer frontend communicate through IPC contracts."
---

# Implementation Adapter: Electron Desktop

This adapter specializes the implementation-core skill for Electron desktop projects.

Shared rules that apply across stacks are defined in `.github/instructions/SharedDeveloperGuidelines.instruction.md`.
This skill focuses only on Electron/IPC-specific implementation behavior.

## When to use

- Backend is Electron main/preload + Node.js services.
- Frontend is Electron renderer (for example React/Vite).
- Integration boundary is IPC, not HTTP REST.

## Contract model

- Contract-first artifact is an IPC contract (channel names, request payloads, response payloads, error shapes, auth/permission constraints, and validation rules).
- OpenAPI is optional and only used when an actual HTTP interface is part of scope.
- IPC contract is the source of truth for backend/frontend integration in this stack.

## Electron implementation checklist

- Main process stays orchestration-oriented; long/blocking work is moved out of hot event-loop paths.
- IPC handlers are thin boundary handlers that delegate to services/data-access modules.
- Channel naming is explicit and predictable (for example `models:get`, `models:create`).
- Prefer `ipcMain.handle` for request/response workflows.

## Preload and security checklist

- Expose only minimal preload APIs via `contextBridge`.
- Keep renderer `nodeIntegration` disabled and `contextIsolation` enabled.
- Never expose unrestricted filesystem or shell operations to renderer.
- Validate paths and privileged operation parameters before execution.

## Persistence checklist (SQLite)

- Use parameterized queries/prepared statements.
- Keep data access cohesive and testable; no ad-hoc SQL in IPC handlers.
- Run schema migration/version checks on startup.
- Ensure DB connections are closed cleanly on app shutdown.

## Type and error contracts

- Define explicit TypeScript types for IPC request/response/error payloads.
- Normalize error envelopes returned to renderer.
- Ensure uncaught exceptions and unhandled rejections are logged with safe shutdown behavior.

## Delegation mapping

- Backend specialist: NodeJsDeveloper.
- Frontend specialist: ReactDeveloper (or renderer specialist available in project).

## Integration checks

- Renderer calls the expected preload or bridge functions/channels.
- Main/preload handlers match contract payload/response/error schemas.
- Error handling semantics are consistent across backend and renderer.
- Security boundaries are respected (context isolation, limited bridge surface, validation at boundary).

## Blockers

- If NodeJsDeveloper or renderer specialist is unavailable, stop and report a hard blocker with required handoff mapping.
- If implementation requires HTTP APIs in addition to IPC, either extend this adapter scope explicitly or use a separate web adapter slice.
