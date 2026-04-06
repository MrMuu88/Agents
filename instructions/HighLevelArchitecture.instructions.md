---
name: high-level-architecture
description:>
Use when: creating or updating the High-Level Architecture document
  (Documentations/Architecture/HighLevelArchitecture.md) for this project.
applyTo:
  - "Documentations/Architecture/HighLevelArchitecture.md"
  - "Documentations/Architecture/HighLevelArchitecture.puml"
---

## High-Level Architecture (HLA) – Short Instructions

The High-Level Architecture (HLA) document explains the end-to-end technical design of a system or product.
Each project must have a main HLA file under:
- Documentations/Architecture/HighLevelArchitecture.md

Use this guide when you create or update that file.
The HLA must be supported by PlantUML diagrams (see section 10).

---

# 1. Purpose and Scope

- Explain what the system is and what the HLA covers.
- Refer to the project PRD and the key feature/UI documents.
- List which topics are in scope (components, data flows, integrations, security, operations) and which are deferred to lower‑level designs.

---

# 2. Architectural Overview

- Describe the overall system style (e.g., monolith vs. microservices, SPA vs. server‑rendered).
- Name the main technologies for frontend, backend, and data stores.
- Mention the main external systems/services the solution depends on.

---

# 3. Runtime Context

- List human actors/roles using the system.
- List external technical dependencies (such as databases, file storage, messaging, email, identity provider).
- Summarize how they interact (for example: users → UI → API → data store; background jobs → external systems).
- ALWAYS add a simple context/C4 diagram.

---

# 4. Backend Logical Architecture

Describe how the backend is structured into logical parts and what each part does.

## 4.1 API Layer
- HTTP controllers/endpoints, routing, input validation, error mapping.
- Authentication and authorization behavior.

## 4.2 Application/Domain Services
- Core business/domain logic.
- Cross-cutting application services (for example: authentication, authorization, auditing, notifications).
- Coordination of use cases and workflows.
- Reference relevant user stories or features where useful.

## 4.3 Infrastructure and Integrations
- Data access (for example: ORM, repositories, direct SQL).
- Integrations with external systems (for example: file storage, messaging, email/SMS, third‑party APIs).
- Technical concerns such as caching, configuration, and background processing.

---

# 5. Frontend Architecture

- Describe the overall shell/layout and how it follows the project’s UI design directives.
- List the main feature areas/pages (for example: authentication, core workflows, administration, reporting).
- Explain how the frontend talks to the backend (API client, auth handling, error and notification patterns).
- Mention shared services/components (for example: routing, state management, auth context, API client, notifications).

---

# 6. Data Model and Storage

- Summarize the key domain entities and main relationships (high level only).
- Distinguish between:
  - Application databases and what they store.
  - External or attached data sources.
  - File or object storage and how items are referenced.
- Call out where critical records (such as configuration, domain state, and audit events) are stored.

---

# 7. Security and Compliance

- Describe the authentication approach (e.g., username/password + JWT, IdP/AD integration).
- Describe the authorization model (roles, policies, permissions around features).
- Note data protection mechanisms (TLS, encryption in transit/at rest where relevant).
- Summarize audit logging principles (what is logged, where, and at what level of detail).

Keep this section at strategy/pattern level; leave code details to other docs.

---

# 8. Operational Concerns

- Describe deployment topology (where backend runs, how frontend is hosted, environments).
- Summarize observability (logging, metrics, tracing) at a high level.
- Mention resilience patterns (retries, timeouts, limits, background jobs/cleanup).
- Note important operational constraints (e.g., concurrency limits, scheduled maintenance jobs).

---

# 9. Open Architectural Questions

- List undecided or open topics (identity provider, scaling strategy, notification provider, etc.).
- Note current assumptions or options.
- Move resolved topics into the main sections or separate ADRs.

---

# 10. Diagrams (PlantUML)

- Each HLA must be supported by at least one high-level component diagram of the system.
- All architecture diagrams must be authored in PlantUML and stored as separate .puml files under:
  - Documentations/Architecture
- The HLA document must reference these .puml files (for example by file name or embedded include directive), but the diagram source itself lives in the .puml files.
- At minimum, show the main components (for example: UI, backend/API, data stores, key external systems) and their relationships.
- Optionally add other diagrams where useful (for example: context diagrams, sequence diagrams for key flows).
- Keep diagrams at an architectural level (components and interactions), not at class or implementation detail level.

---

# Maintenance Rules

- Treat the HLA as stable but living:
  - Update when major architectural decisions change.
  - Do not document minor implementation details.
- Keep the HLA aligned with:
  - The current PRD.
  - Feature documentation under Documentations/Features/.
  - UI design documentation under Documentations/UI/.
- When a new feature significantly changes architecture (new service, external system, etc.), update the relevant HLA sections instead of writing a separate one‑off document.
