---
name: high-level-architecture
description: "Use when: analyzing requirements and generating appropriate architectural models and descriptions for HighLevelArchitecture.md."
---

# High Level Architecture Implementation Skill

Write clear and cohesive documentation covering exactly these 7 key sections mapped from requirements in `Documentations/Architecture/HighLevelArchitecture.md`.

## Step 1: Architectural Definition (7 Sections)
Format the markdown document exactly as follows:

# 1. Purpose and Scope
- Explain what the system is and what the HLA covers. Refer to PRDs.

# 2. Architectural Overview
- Monolith vs. microservices, SPA vs. server rendered. Main technologies used.

# 3. Runtime Context
- List human actors, external technical dependencies (DBs, Email, IdP).
- ALWAYS embed a simple Context Diagram link here.

# 4. System Architectures & Models
- Reference [BackendArchitecture.md](BackendArchitecture.md) for backend specifics.
- Reference [FrontendArchitecture.md](FrontendArchitecture.md) for frontend specifics.
- Reference [DataModels.md](DataModels.md) for database tables, entities, and storage layouts.

# 5. Security and Compliance
- Auth approach (e.g. JWT) and Authorization (RBAC). Audit principles.

# 6. Operational Concerns
- Deployment topology, observability (logs/metrics/traces), limits, retries.

# 7. Open Architectural Questions
- List unresolved tech questions/strategies.

## Step 2: C4 / Conceptual Context Diagramming (.puml)
- Define a high-level PlantUML Context Diagram under `Documentations/Architecture/HighLevelArchitecture.puml`.
- Demonstrate the interactions between key components (frontend, backend APIs, data stores, external platforms).