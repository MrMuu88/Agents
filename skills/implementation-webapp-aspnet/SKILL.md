---
name: implementation-webapp-aspnet
description: "Use when: implementing web applications where ASP.NET backend exposes HTTP APIs consumed by web frontend clients."
---

# Implementation Adapter: Web App (ASP.NET)

This adapter specializes the implementation-core skill for ASP.NET web application stacks.

Shared rules that apply across stacks are defined in `.github/instructions/SharedDeveloperGuidelines.instruction.md`.
This skill focuses only on ASP.NET-specific implementation behavior.

## When to use

- Backend is ASP.NET (controllers/minimal APIs/application services).
- Frontend consumes HTTP APIs.
- Integration boundary is HTTP API.

## Contract model

- OpenAPI is the default source-of-truth contract.
- Define paths, methods, auth rules, request/response schemas, error models, pagination/filtering/sorting, and versioning approach.
- Stabilize contract before backend/frontend implementation.

## ASP.NET implementation checklist

- Keep `Program.cs` focused on DI, middleware, and controller mapping.
- Prefer controller-based endpoints for HTTP APIs.
- Keep controllers thin and delegate reusable business logic to services.
- Keep services operating on domain entities, not request/response DTOs.

## Data and persistence checklist

- Inject `AppDbContext` directly; do not add repository wrappers over EF Core by default.
- Keep data access cohesive in services; avoid scattered controller-level persistence code.
- Handle transaction and concurrency boundaries explicitly for multi-step write paths.

## Migration discipline checklist

- On DAL model or `DbContext` change:
	1. Generate migration: `dotnet ef migrations add <DescriptiveMigrationName>`.
	2. Review generated migration for intended diff only.
	3. Apply update: `dotnet ef database update`.
- Never modify/delete applied migrations; create corrective migrations.

## API behavior checklist

- Validate route/query/body inputs before service invocation.
- Keep response and error payload schemas consistent with contract.
- Use clear status code semantics across success and failure paths.
- Ensure authentication/authorization behavior matches contract definition.

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
