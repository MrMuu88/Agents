---
name: data-models
description: "Use when: extracting entities and generating or updating the DataModels.md and DataModels.puml documentation files."
---

# Data Models Creation Skill

This skill provides step-by-step guidance for an agent generating or updating the DataModels.md and DataModels.puml documentation files.

## Prerequisites
- Review existing `Documentations/Architecture/architecture.md` to understand high-level concepts.
- Review `Documentations/Features/**` and `Documentations/UI/**` to gather all required domain entities.
- Ensure you have a clear understanding of the project's data domains before you start.

## Step 1: Extract Entities
- Read through the feature specifications and UI design documents.
- Identify core business entities (e.g., users, roles, products, orders).
- Determine what fields are required to support the features and UI.
- Establish relationships (one-to-one, one-to-many, many-to-many) between entities based on the described functionality.

## Step 2: Write DataModels.md
In `Documentations/Architecture/DataModels.md`, create sections in this EXACT order:

### 1. Overview
- 3–6 sentences about the main data domains (e.g., backups, databases, users, access, audit).

### 2. Entity Catalogue
- For each persisted entity, provide its Name, short description, and table/collection name.
- Use this EXACT markdown table format for attributes:
  | Field | Type (logical) | Null? | Default | Description |
  |-------|----------------|-------|---------|-------------|

### 3. Relationships
- List important relationships with cardinality (1–1, 1–N, N–M).
- Mention ownership and delete behavior if known.

### 4. Domain & Integrity Rules
- Bullet list of rules that affect persistence (e.g., soft delete, history tables, access-control link tables).

### 5. Open Questions / Assumptions
- Bullet list of assumptions or unknowns to clarify later.

## Step 3: Write DataModels.puml
- In `Documentations/Architecture/DataModels.puml`, define a PlantUML class diagram for all persisted entities and their relationships.
- Use class names that match the entity names in the markdown file exactly.
- Keep the diagram architectural; include only major attributes and primary relationships with proper cardinalities.