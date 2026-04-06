---
name: DataModels
description: "Use when: evaluating or locating documentation for the persisted data model (tables, entities, relationships, constraints) of the system."
applyTo: "Documentations/Architecture/DataModels.md"
---

## Purpose
Defines the persisted data model, including entities, relationships, and business rules.

## File Locations
- **Markdown:** `Documentations/Architecture/DataModels.md`
- **Diagram:** `Documentations/Architecture/DataModels.puml`

## Content Structure
1. **Overview:** A brief summary of the main data domains.
2. **Entity Catalogue:** Tables listing data entities, their fields, types, and constraints.
3. **Relationships:** Cardinality (1-N, N-M) and entity ownership.
4. **Domain & Integrity Rules:** Data behavior rules (e.g., soft deletes, audit tracks).
5. **Open Questions:** Unresolved constraints or missing types.

**Note:** To generate or update this documentation, use the `data-models` skill.

