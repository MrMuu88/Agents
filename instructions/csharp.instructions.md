---
applyTo: "DatabaseManager-Api/**"
---

# Rules and Best Practices for C# / .NET

## General C# and .NET Standards

- Use modern C# features supported by the target framework (`net10.0`) where they improve clarity and safety.
- Keep `Nullable` reference types enabled and treat nullable warnings as design feedback, not noise.
- Prefer explicit types over `var` when it improves readability; use `var` when the type is obvious from the right-hand side.
- Avoid using `dynamic`; use strongly typed models and generics instead.
- Keep methods short and focused on a single responsibility.
- Avoid static mutable state and singletons unless explicitly justified.

## Project and Layering Guidelines

- Treat `DatabaseManager-Api` as the HTTP/API boundary for the system.
- Keep request/response shaping, routing, and protocol concerns at the API layer.
- Place business logic in dedicated services or domain classes, not directly in controllers or minimal-API lambdas.
- Keep infrastructure concerns (data access, external integrations) behind clear abstractions where complexity grows.
- Follow existing folder and namespace patterns; do not invent new high-level layers without architectural alignment.

## API Design and Controllers

- Prefer clear, resource- and use-case-oriented endpoints with consistent naming and routing.
- Use dedicated request/response DTOs instead of exposing internal domain entities directly.
- Validate all external inputs (route, query, body); fail fast with meaningful, consistent error responses.
- Use appropriate HTTP verbs and status codes (e.g., 200/201/204 for success, 400 for validation errors, 404 for missing resources, 500 for unexpected failures).
- Keep controllers/endpoints thin: delegate logic to services and keep orchestration readable.

## Error Handling and Logging

- Do not swallow exceptions; either handle them explicitly or let centralized middleware/filters handle them.
- When catching exceptions, log enough context (operation, identifiers) without leaking sensitive data.
- Use structured logging (e.g., named properties) for important events instead of concatenated strings.
- Ensure error responses do not expose stack traces or internal implementation details.

## Data and Persistence

- Follow the documented data model and integrity rules from the architecture and data model docs.
- Keep database access code cohesive and testable; avoid sprinkling ad-hoc SQL or data access calls across controllers.
- Do not embed connection strings or credentials in code; rely on configuration and secrets management.
- Handle concurrency and transaction boundaries explicitly when needed; do not rely on implicit behavior.
- **After every change to a DAL model class or `AppDbContext` configuration** (adding/removing entities, properties, indexes, relationships, or seed data), always:
  1. Generate a new migration: `dotnet ef migrations add <DescriptiveMigrationName>` (run from `DatabaseManager-Api/`).
  2. Review the generated migration file in `DAL/Migrations/` to confirm it reflects only the intended changes.
  3. Apply it to the local database: `dotnet ef database update`.
- Use descriptive migration names that reflect the change (e.g., `AddAuditEvents`, `AddUserEmailIndex`, `SeedDefaultRoles`).
- Never modify or delete an already-applied migration; create a new corrective migration instead.
- Verify there are no pending model changes (EF will throw `PendingModelChangesWarning` on startup if the model drifts from the snapshot) before committing.

## Asynchrony and Performance

- Prefer async APIs end-to-end for I/O-bound work; avoid blocking calls (`.Result`, `.Wait()`) on async operations.
- Use cancellation tokens where appropriate for long-running or client-bound operations.
- Avoid premature optimization; focus first on clear, correct code with obvious performance characteristics.
- When using caching or other performance techniques, make invalidation rules explicit.

## Testing and Maintainability

- Write code that is easy to unit test: inject dependencies, avoid tight coupling to static/global state.
- When test projects exist, add or update tests alongside non-trivial changes.
- Prefer small, incremental changes over large rewrites; keep diffs focused on a single concern or feature.
- Name classes, methods, and variables to reflect intent rather than implementation details.

## Security and Configuration

- Never log secrets, passwords, connection strings, or tokens.
- Use configuration providers and options patterns instead of hardcoding environment-specific values.
- Apply authentication and authorization consistently at the API boundary according to architecture/security docs.
- Validate and sanitize all inputs coming from external systems, not just from the UI.

## Collaboration with Other Parts of the System

- Treat the PRD, feature/user story docs, and UI specs as the source of truth for behavior and contracts.
- Coordinate contract changes (request/response shapes, routes) with frontend and architecture before applying breaking changes.
- Prefer evolving existing patterns already present in the codebase over introducing new frameworks or styles.

