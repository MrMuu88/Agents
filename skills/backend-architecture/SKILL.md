---
name: backend-architecture
description: "Use when: documenting backend-specific structure, such as API definition, domain logic, and data access layers."
---

# Backend Architecture Implementation Skill

Write clear and cohesive documentation covering exactly these sections mapped from requirements in `Documentations/Architecture/BackendArchitecture.md`.

## Step-by-Step Backend Architecture Definition
Format the markdown document exactly as follows:

# 1. Purpose
- Brief intro to the backend stack (languages, frameworks).

# 2. Logical Architecture Layering
- Detail the boundaries and rules of each component tier.

## 2.1 API Layer
- HTTP routing principles, controllers vs routes.
- Input validation, response DTO patterns, HTTP status mappings.
- API authentication behavior (e.g. middleware verification).

## 2.2 Application / Domain Services
- Core business logic containerization.
- Workflows, orchestration, and business rule enforcement.

## 2.3 Infrastructure and Integrations
- Implementation details for the data access (ORM/Query builders, Repository patterns).
- Integrations with external systems (files, SMS, external APIs, Auth providers).

# 3. Background Processing & Async Workloads
- Details on queue workers, message brokers, CRON schedules.

# 4. Error Handling and Cross-Cutting Concerns
- How errors are caught, logged, and surfaced to clients. Default exception handlers.

# 5. Component Diagrams (PlantUML)
- If necessary, provide component or sequence diagrams illustrating complex backend data flows inside `Documentations/Architecture/BackendArchitecture.puml`.