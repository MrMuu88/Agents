---
name: implementation-electron-desktop
description: "Use when: implementing Electron desktop features where Node/Electron backend and renderer frontend communicate through IPC contracts."
---

# Implementation Adapter: Electron Desktop

This adapter specializes the implementation-core skill for Electron desktop projects.

## When to use

- Backend is Electron main/preload + Node.js services.
- Frontend is Electron renderer (for example React/Vite).
- Integration boundary is IPC, not HTTP REST.

## Contract model

- Contract-first artifact is an IPC contract (channel names, request payloads, response payloads, error shapes, auth/permission constraints, and validation rules).
- OpenAPI is optional and only used when an actual HTTP interface is part of scope.
- IPC contract is the source of truth for backend/frontend integration in this stack.

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
