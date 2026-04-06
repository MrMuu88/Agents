---
name: UI_Design
description: "Use when: organizing, reading, or locating structural requirements for user interface layouts and prototypes."
applyTo: "Documentations/UI/**"
---

## Purpose
Defines exactly how specific screens and user flows should look and behave.

## Structure & Content
**Folder Location:** `Documentations/UI/UI-XXX-[screen-name]/`

1. **Functional Specification (`.md`):**
   - **Content:** Information hierarchy, user goals, and state descriptions (loading/error/empty).
   - **Components:** Lists of needed inputs, buttons, validations, and accessibility rules.

2. **Prototype (`.html`):**
   - **Content:** A standalone, styled UI representation using HTML/CSS.
   - **Design:** Implements semantic tags and standard design tokens (colors, spacing) to visualize the `.md` specification.

**Note:** To generate functional specs and HTML prototypes, use the `ui-design` skill.

