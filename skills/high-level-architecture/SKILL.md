---
name: high-level-architecture
description: "Use when: analyzing requirements and generating appropriate architectural models and descriptions for HighLevelArchitecture.md."
---

# High Level Architecture Implementation Skill

Write clear and cohesive documentation covering exactly these 10 key sections mapped from requirements in `Documentations/Architecture/HighLevelArchitecture.md`.

## Step 1: Architectural Definition (10 Sections)
Format the markdown document exactly as follows:

# 1. Purpose and Scope
- Explain what the system is and what the HLA covers. Refer to PRDs.

# 2. Architectural Overview
- Monolith vs. microservices, SPA vs. server rendered. Main technologies used.

# 3. Runtime Context
- List human actors, external technical dependencies (DBs, Email, IdP).
- ALWAYS embed a simple Context Diagram link here.

# 4. Backend Logical Architecture
## 4.1 API Layer
- HTTP routing, controllers, input validation. Auth behavior.
## 4.2 Application/Domain Services
- Core business logic, workflows, cross-cutting concerns.
## 4.3 Infrastructure and Integrations
- Data access (ORM/SQL) and integrations with external systems (files, SMS).

# 5. Frontend Architecture
- Target layout, feature areas (pages), components. How it talks to backend.

# 6. Data Model and Storage
- Summarize entities. Distinguish app databases vs external stores vs blob storage.

# 7. Security and Compliance
- Auth approach (e.g. JWT) and Authorization (RBAC). Audit principles.

# 8. Operational Concerns
- Deployment topology, observability (logs/metrics/traces), limits, retries.

# 9. Open Architectural Questions
- List unresolved tech questions/strategies.

# 10. Diagrams (PlantUML)
- Each architecture must be supported by C4 PlantUML diagrams.

## Step 2: C4 / Conceptual Context Diagramming (.puml)
- Define a high-level PlantUML Context Diagram under `Documentations/Architecture/HighLevelArchitecture.puml`.
- Demonstrate the interactions between key components (frontend, backend APIs, data stores, external platforms).