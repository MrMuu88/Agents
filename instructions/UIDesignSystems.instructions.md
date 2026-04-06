---
name: DesignSystem
description: "Use when: creating, designing, or implementing UI components, layouts, and prototypes. Contains design tokens, colors, typography, and component rules."
applyTo: "Documentations/UI/**"
---

# Design System & UI Tokens

This document defines the core visual language, design tokens, and interaction patterns for the application interface.

## Visual Directions (2 Approved Styles)

### A) Anthracite Modern
Use this when the product needs an enterprise / technological feel.

- **Background:** `#111315` or `#15181B`
- **Surface:** `#1B1F24`
- **Surface elevated:** `#232831`
- **Text primary:** `#F5F7FA`
- **Text secondary:** `#A9B2BF`
- **Border:** `#2C3440`
- **Accent (cool green):** `#2BD97F`
- **Danger:** `#FF5D6C`

### B) Green / White Clean
Use this when you need a friendlier, fresher, healthcare or admin-like UI.

- **Background:** `#F7FAF8`
- **Surface:** `#FFFFFF`
- **Surface alt:** `#EEF4EF`
- **Text primary:** `#101418`
- **Text secondary:** `#4B5563`
- **Border:** `#D7E3DA`
- **Accent green:** `#16A34A`
- **Accent soft:** `#DCFCE7`
- **Danger:** `#DC2626`

## Typography and Rhythm
- **Font:** Inter, Manrope, or system sans-serif.
- **Size scale:** 12 / 14 / 16 / 20 / 24 / 32.
- **Weight:** 400 (body), 500 (UI), 600–700 (heading).
- **Line height:** 1.4–1.6.
- **Spacing system:** 4px based (4, 8, 12, 16, 24, 32, 40, 48).
- **Radius:** 10–14 px.
- **Shadow:** restrained, single soft layer.

## Component Rules
- **Buttons:** max 2 highlighted CTAs per view.
- **Cards:** clear hierarchy (title → meta → action).
- **Forms:** short labels, inline validation, clearly visible focus state.
- **Tables/Lists:** high readability, fixed headers, clear status badges.
- **Navigation:** flat, minimal depth, quick access.

## Interaction Style
- Animations should be **subtle and short** (120–220ms).
- Hover: slight brightness or border change.
- Active: one step stronger contrast.
- Loading: simple skeleton or progress indicator.
- Empty state: informative, not decorative.

## What to Avoid
- Crowded screens, too many panels.
- Neon overdone, strong glow, noisy gradient.
- More than 3 actions in a critical block.
- Mixed design language within a single page.