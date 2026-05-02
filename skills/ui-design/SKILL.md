---
name: ui-design
description: "Use when: writing structural design rules and corresponding functional UI prototypes under Documentations/UI."
---

# UI Design Creation Skill

Guidance for writing structural design rules and corresponding functional UI prototypes under `Documentations/UI`.

## Available Design Style Definitions

The following named design styles are defined and available for use in prototypes. When a task specifies a style or the context implies one, load the corresponding file before writing HTML/CSS tokens.

| Style Name           | File                                                      | Character & Use Case                             |
|----------------------|-----------------------------------------------------------|--------------------------------------------------|
| Aurora               | `.github/skills/ui-design/Aurora Design.md`               | Dark cosmic, glassmorphism, premium ethereal feel|
| Anthracite Modern    | `.github/skills/ui-design/Anthracite Modern Design.md`    | Enterprise/fintech, dark precise, cool green    |
| Green / White Clean  | `.github/skills/ui-design/Green White Clean Design.md`    | Healthcare/admin, light airy, friendly green    |

> Always check this table before applying design tokens. Load the corresponding style file to retrieve exact color, typography, spacing, and component specifications.

## Step 1: File and Folder Setup
- Review `Documentations/UI/ProjectDesignDirectives.md` for project-wide UI tokens.
- If a named design style is specified, read the corresponding file from the table above to retrieve exact color tokens, typography, spacing, and component rules before proceeding.
- Set up a subfolder `Documentations/UI/UI-XXX-[short-name]/`. (e.g., `UI-001-login-kepernyo`). Note that no spaces are allowed. Use only lowercase and hyphens.
- Inside, create an exact `.md` specification and a styling-matching `.html` prototype file pair.

## Step 2: Write Functional MD Spec
Provide the following defined structure in the `.md`:
```md
# [UI-XXX] [Screen Title]

## Screen Overview
- Goal: ... | Main user type: ... | Primary action: ...

## User Flow & States
- Steps 1, 2... and empty/loading/error states.

## Information Hierarchy
- Main regions (header / sidebar / content / footer)

## Components & Fields
- Buttons, Input fields, validation, tables.

## Interaction Notes
- Hover / Active / Focus / Loading

## Accessibility Notes
- Contrast, focus, keyboard navigation

## Navigation and Relationships
- Where user comes from and goes next
```

## Step 3: Write HTML Prototype (.html)
- Ensure the result is a fully standalone HTML5 document.
- Must include an embedded `<style>` block using the design tokens from the chosen style definition (see **Available Design Style Definitions** above, or fall back to Anthracite Modern / Green/White Clean from `UIDesignSystems.instructions.md`).
- Must use distinct CSS pseudo-classes (`:hover`, `:active`, `:focus-visible`) for all interactive elements.
- Ensure semantic layout matching the hierarchy (`<nav>`, `<main>`, `<aside>`).

## Step 4: Iterative UI Verification
- Ensure interactions are understandable without JS, though minimal JS is allowed for basic tab toggling or modal toggles.