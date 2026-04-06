## Goal

This instruction describes how to document **UI screens and flows** in the project so that the UI Designer Agent can easily interpret them and automatically generate:

- the functional **Markdown specification (.md)** and
- the corresponding styled **HTML prototype (.html)**.

## Folder Structure

1. UI design files are stored **separately** from feature documentation, in the `Documentations/UI` folder.
2. In the `Documentations/UI` folder you must create a central summary document named `ProjectDesignDirectives.md`.
3. Every UI screen / flow has its own **subfolder** under `Documentations/UI`.

Base structure:

- `Documentations/UI/ProjectDesignDirectives.md`
- `Documentations/UI/<ScreenId-ScreenShortName>/`

Example screen subfolders:

- `Documentations/UI/UI-001-login-kepernyo/`
- `Documentations/UI/UI-010-adatbazismentesek-lista/`

Each individual screen / flow consists of two files inside its own subfolder:

- a **`.md`** specification file, and
- an identically named **`.html`** prototype file in the **same** subfolder.

## File Name Convention

1. Base format: `UI-<id>-<short-name>.md` and `UI-<id>-<short-name>.html`
2. Use only **lowercase letters** and **hyphens (`-`)**; do not use spaces.
3. The identifier can be a sequence number or a short code, e.g. `UI-001-backup-lista.md`.

Examples:

- `UI-001-login-kepernyo.md` / `UI-001-login-kepernyo.html`
- `UI-010-adatbazismentesek-lista.md` / `UI-010-adatbazismentesek-lista.html`

## Required Content of the Markdown Specification (.md)

The `.md` file describes the **behaviour, information hierarchy and UX logic**. Recommended template:

```md
# [UI-XXX] [Screen Title]

## Screen Overview
- Goal: ...
- Main user type(s): ...
- Primary action: ...

## User Flow & States
- Step 1: ...
- Step 2: ...
- States: empty state / loading / success / error

## Information Hierarchy
- Main regions (header / sidebar / content / footer)
- What appears as primary, what as secondary

## Components & Fields
- Buttons: ... (primary/secondary, label, icon, disabled state)
- Input fields: ... (type, placeholder, validation)
- Lists / tables: ... (columns, sorting, filtering)

## Interaction Notes
- Hover: ...
- Active: ...
- Focus: ...
- Loading: skeleton / spinner / progress bar

## Accessibility Notes
- Contrast requirements
- Focus order and focus indication
- Keyboard navigation (Tab, Enter, Esc, arrow keys)

## Navigation and Relationships
- Where the user comes from when arriving at this screen
- Where they can go next (links, buttons)
```

## Requirements for the HTML Prototype (.html)

The `.html` file is a **standalone, styled UI prototype** that:

1. Is a complete HTML document:
	- `<!DOCTYPE html>`
	- with `<html>`, `<head>`, `<body>` blocks.
2. Contains an **embedded `<style>` block** that follows the chosen design system:
	- **Anthracite Modern**, or
	- **Green / White Clean**.
3. Uses clearly separated **design tokens** in CSS (colours, typography, spacing, radius).
4. Has an HTML structure that reflects the **information hierarchy** described in the MD (header, nav, main, aside, footer, etc.).

### Navigation

If the screen includes multiple views / tabs:

- provide a clear **top or side navigation**, and
- highlight the current view with an **active** state (e.g. different background, border or colour).

### State Indications

- Define hover / active / focus states using **CSS pseudo-classes** (`:hover`, `:active`, `:focus-visible`).
- For loading states you may use a simple skeleton or a progress bar.

### Use of JavaScript

- Only minimal JS is allowed, and only when needed to demonstrate behaviour (e.g. tab switching, opening/closing a modal).
- Interactions must remain **understandable without JS** (progressive enhancement approach).

## Relationship to the UI Designer Agent

`UIDesigner.agent.md` describes the visual direction and the agent’s workflow. This instruction:

- defines **where** and in **what format** UI specifications must be stored,
- defines the expected structure of **`.md` and `.html` pairs**, and
- ensures that generated UI documents follow a **consistent, machine-readable** structure.

For every new UI screen / flow created by the agent, create such an **MD + HTML pair** in the appropriate feature/UI folder.

