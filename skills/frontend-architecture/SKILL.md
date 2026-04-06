---
name: frontend-architecture
description: "Use when: documenting the primary layout, navigation mapping, component hierarchy, client-side data state, and overall frontend structure."
---

# Frontend Architecture Implementation Skill

Write clear and cohesive documentation covering exactly these sections mapped from requirements in `Documentations/Architecture/FrontendArchitecture.md`.

## Step-by-Step Frontend Architecture Definition
Format the markdown document exactly as follows:

# 1. Purpose
- Brief intro to the frontend stack (frameworks, routing, build tools).

# 2. Application Map & Layouts
- High-level directory/module mapping.
- Core UI layout shells (dashboard view, public view).

# 3. Component Hierarchy
- Feature areas mapped to distinct route boundaries.
- The separation paradigm used for UI display versus data fetching (smart vs. dumb components).

# 4. State Management
- Global store structure vs local state context.
- Caching strategies, synchronous user data, background synchronization rules.

# 5. API Integrations
- Fetching strategies (fetch API vs Axios vs Apollo/GraphQL).
- Interceptors, global error notifications, retry logic.

# 6. Styling and UI Components 
- Component library rules (Tailwind, Material-UI, Custom SCSS/CSS Modules).

# 7. Frontend Architecture Diagrams (PlantUML)
- Add diagrams to demonstrate complex UI state transitions or client-to-API communication in `Documentations/Architecture/FrontendArchitecture.puml`.