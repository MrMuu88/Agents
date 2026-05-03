---
name: implementation-webapp-aspnet
description: "Use when: implementing web applications where ASP.NET backend exposes HTTP APIs consumed by web frontend clients."
---

# Implementation Adapter: Web App (ASP.NET)

This adapter specializes the implementation-core skill for ASP.NET web application stacks.

## When to use

- Backend is ASP.NET (controllers/minimal APIs/application services).
- Frontend consumes HTTP APIs.
- Integration boundary is HTTP API.

## Contract model

- OpenAPI is the default source-of-truth contract.
- Define paths, methods, auth rules, request/response schemas, error models, pagination/filtering/sorting, and versioning approach.
- Stabilize contract before backend/frontend implementation.

## Delegation mapping

- Backend specialist: NetDeveloper.
- Frontend specialist: ReactDeveloper (or project-specific web frontend specialist).

## Integration checks

- Frontend calls match OpenAPI paths/methods/headers/query/body definitions.
- Backend responses and error payloads match declared schemas/status codes.
- Authentication and authorization behavior is consistent with the contract.

## Blockers

- If NetDeveloper is unavailable in current project, stop and report a hard blocker and required agent mapping.
- If repository is not a web app stack, do not use this adapter.
