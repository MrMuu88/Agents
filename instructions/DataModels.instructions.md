---
name: data-model-docs
description:>
Use when: generating or updating documentation for the persisted data model
	(tables, entities, relationships, constraints) of the Database Manager system.
applyTo:
  - "Documentations/Architecture/DataModels.md"
  - "Documentations/Architecture/DataModels.puml"
---

## Task

- Create or update Documentations/Architecture/DataModels.md with the **persisted data model** description.
- Create or update Documentations/Architecture/DataModels.puml with a **class diagram** of the same data model (PlantUML).

## Use These Inputs

- Documentations/Architecture/architecture.md
- Documentations/Features/**
- Documentations/UI/**
- Any schema/ERD/DDL files if they exist.

## Output Structure

In Documentations/Architecture/DataModels.md, create sections in this order:

1. Overview
2. Entity Catalogue
3. Relationships
4. Domain & Integrity Rules
5. Open Questions / Assumptions

### 1. Overview

- 3–6 sentences about the main data domains (e.g., backups, databases, users, access, audit).

### 2. Entity Catalogue

- For each persisted entity:
  - Name, short description, table/collection name (if known).
  - Attribute table:

    | Field | Type (logical) | Null? | Default | Description |
    |-------|----------------|-------|---------|-------------|

### 3. Relationships

- List important relationships with cardinality (1–1, 1–N, N–M).
- Mention ownership and delete behavior if known.

### 4. Domain & Integrity Rules

- Bullet list of rules that affect persistence (e.g., soft delete, history tables, access-control link tables).

### 5. Open Questions / Assumptions

- Bullet list of assumptions or unknowns to clarify later.

## Class Diagram File

- In Documentations/Architecture/DataModels.puml:
  - Define a PlantUML class diagram for all persisted entities and their relationships.
  - Use class names that match the entity names in the markdown file.
  - Show associations with proper cardinalities where possible.

