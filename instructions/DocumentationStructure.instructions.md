---
name: DocumentationStructure
description: "Use when: organizing, reading, or locating structural requirements for documentation layout and content organization across all documentation types."
applyTo: "Documentations/**"
---
# Documentation Structure Guidelines

This document serves as the master guide for how all documentation should be structured, organized, and formatted.

## Folder Structure Example
```text
Documentations/
├── Architecture/
│   ├── BackendArchitecture.md
│   ├── BackendArchitecture.puml
│   ├── DataModels.md
│   ├── DataModels.puml
│   ├── FrontendArchitecture.md
│   ├── FrontendArchitecture.puml
│   ├── HighLevelArchitecture.md
│   └── HighLevelArchitecture.puml
├── Features/
│   └── FE-001-InventoryManagement/
│       ├── FE-001-InventoryManagement.md
│       └── US-001-AddStock.md
└── UI/
    └── UI-001-Dashboard/
        ├── DashboardSpec.md
        └── DashboardPrototype.html
```

## 1. Features and User Stories
Stores the functional requirements, broken down into Features and individual User Stories.
* **Location:** `Documentations/Features/FE-XXX-[feature-name]/`
* **Feature File (`FE-XXX-[FeatureName].md`):** High-level description, business goals, and feature-level acceptance criteria. Links to PRD and User Stories.
* **User Story Files (`US-XXX-[story-name].md`):** Formatted as "As a [role], I want to [goal] so that [reason]." Includes a numbered bullet list (`[AC-001]`) of technical and functional conditions.
* **Skill to use to create or update:** `features-and-userstories`

## 2. High-Level Architecture
The primary single source of truth for the end-to-end technical design and logical infrastructure.
* **Location:** `Documentations/Architecture/HighLevelArchitecture.md` and `HighLevelArchitecture.puml`
* **Content:** Scope & overview, runtime context (actors, C4 Context diagram), references to sub-architectures, security & ops (deployment topology, roles).
* **Skill to use to create or update:** `high-level-architecture`

## 3. Data Models
Defines the persisted data model, including entities, relationships, and business rules.
* **Location:** `Documentations/Architecture/DataModels.md` and `DataModels.puml`
* **Content:** Overview of domains, entity catalogue (fields, types, constraints), relationships (cardinality), domain rules (soft deletes), and open questions.
* **Skill to use to create or update:** `data-models`

## 4. Backend Architecture
Acts as the detailed guide for backend systems, layers, routing logic, and systemic integrations.
* **Location:** `Documentations/Architecture/BackendArchitecture.md` and `BackendArchitecture.puml`
* **Content:** API layer (HTTP handlers, routing, DTOs), application/domain services, infrastructure (data access, ORM, third-party clients), and background processes.
* **Skill to use to create or update:** `backend-architecture`

## 5. Frontend Architecture
Acts as the central reference for the frontend layout, component hierarchy, and client-side data management.
* **Location:** `Documentations/Architecture/FrontendArchitecture.md` and `FrontendArchitecture.puml`
* **Content:** Application structure (SPA/MPA, modules), component hierarchy (routing, layout shells), state management (caching, Redux/Context), and API communication (interceptors, WebSockets).
* **Skill to use to create or update:** `frontend-architecture`

## 6. UI Design
Defines exactly how specific screens and user flows should look and behave.
* **Location:** `Documentations/UI/UI-XXX-[screen-name]/`
* **Functional Spec (`.md`):** Information hierarchy, user goals, state descriptions (loading/error/empty), inputs, and accessibility rules.
* **Prototype (`.html`):** A standalone, styled UI representation implementing semantic tags and standard design tokens to visualize the spec.
* **Skill to use to create or update:** `ui-design`