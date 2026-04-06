---
name: BackendArchitecture
description: "Use when: documenting, navigating, or designing backend-specific technical structures, such as API layers, domain services, or data access."
applyTo: "Documentations/Architecture/BackendArchitecture.md"
---

## Purpose
Acts as the detailed guide for backend systems, delineating layers (e.g., controllers vs. services), routing logic, and systemic integrations.

## Content Stored
- **API Layer:** HTTP handlers, routing, input DTO structure, payload validation, and core controller design.
- **Application & Domain Services:** Core business workflows, abstractions, and cross-cutting components (e.g. logging decorators).
- **Infrastructure & Integrations:** Data-access layer implementation, ORM patterns, and third-party API clients.
- **Background Processes:** Queue workers, scheduled CRON jobs, event consumption.

**Note:** For modifying backend architectural docs, pair this with the `backend-architecture` skill.
