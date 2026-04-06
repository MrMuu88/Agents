---
name: ui-design
description: "Use when: writing structural design rules and corresponding functional UI prototypes under Documentations/UI."
---

# UI Design Creation Skill

Guidance for writing structural design rules and corresponding functional UI prototypes under `Documentations/UI`.

## Step 1: File and Folder Setup
- Review `Documentations/UI/ProjectDesignDirectives.md` for project-wide UI tokens.
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
- Must include an embedded `<style>` block simulating the chosen design system (Anthracite Modern or Green/White Clean).
- Must use distinct CSS pseudo-classes (`:hover`, `:active`, `:focus-visible`) for all interactive elements.
- Ensure semantic layout matching the hierarchy (`<nav>`, `<main>`, `<aside>`).

## Step 4: Iterative UI Verification
- Ensure interactions are understandable without JS, though minimal JS is allowed for basic tab toggling or modal toggles.