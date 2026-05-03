# Green / White Clean Design Style — Ruleset

> A friendly, accessible, and clinical aesthetic inspired by healthcare systems and modern admin dashboards. Emphasizes clarity, trust, and ease of navigation through warm greens, crisp whites, and thoughtful spacing.

---

## 1. Core Philosophy

- **Light, airy canvas.** The interface lives on white or near-white backgrounds, creating openness and approachability.
- **Green as trust.** Soft, natural greens convey healthcare, wellness, and human-centered design.
- **Depth through elevation.** Clean shadows and subtle borders define information hierarchy rather than heavy contrast.
- **Clarity first.** Every element has a clear purpose. Visual noise is eliminated.
- **Accessible by nature.** High contrast, large hit targets, readable typography ensures inclusion from the ground up.

---

## 2. Color System

### 2.1 Background & Canvas

| Token                  | Value        | Usage                                            |
|------------------------|--------------|--------------------------------------------------|
| `--bg-base`            | `rgba(247,250,248,1)`    | Main app background (very light warm gray)       |
| `--bg-secondary`       | `rgba(241,247,242,1)`    | Page section backgrounds, subtle shift           |
| `--bg-surface`         | `rgba(255,255,255,1)`    | Card surfaces, elevated panels                   |
| `--bg-surface-alt`     | `rgba(238,244,239,1)`    | Alternative surface for secondary content        |
| `--bg-overlay`         | `rgba(16,20,24,0.56)` | Modal backdrop, overlays            |

### 2.2 Green Accent Palette

Green is the semantic accent — used for success, primary actions, and positive states.

| Token              | Value     | Hue Name         |
|--------------------|-----------|------------------|
| `--green-primary`  | `rgba(22,163,74,1)` | Core brand green |
| `--green-light`    | `rgba(220,252,231,1)` | Light green background |
| `--green-dark`     | `rgba(21,128,61,1)` | Dark green for hover/active |
| `--green-muted`    | `rgba(134,239,172,1)` | Softer green accent |

### 2.3 Semantic / Functional Colors

| Token               | Value       | Usage                         |
|---------------------|-------------|-------------------------------|
| `--text-primary`    | `rgba(16,20,24,1)`   | Headings, key labels, body text |
| `--text-secondary`  | `rgba(75,85,99,1)`   | Meta, descriptions            |
| `--text-muted`      | `rgba(156,163,175,1)`   | Placeholders, disabled text   |
| `--text-inverse`    | `rgba(255,255,255,1)`   | Text on colored backgrounds   |
| `--border-subtle`   | `rgba(215,227,218,1)`   | Default borders, dividers     |
| `--border-active`   | `rgba(22,163,74,1)`   | Focused / active borders      |
| `--accent-primary`  | `rgba(22,163,74,1)`   | Primary CTA, links, active nav|
| `--accent-soft`     | `rgba(220,252,231,1)`   | Light backgrounds for accents |
| `--danger`          | `rgba(220,38,38,1)`   | Errors, destructive actions   |
| `--warning`         | `rgba(245,158,11,1)`   | Warnings, caution             |
| `--success`         | `rgba(16,185,129,1)`   | Success, confirmations        |
| `--info`            | `rgba(59,130,246,1)`   | Informational, secondary CTA  |

### 2.4 Color Usage Rules

- Green is used consistently for all positive, primary, and affirmative states.
- Red is reserved for errors, deletions, and destructive actions only.
- Backgrounds should remain light — never use dark overlays on main canvas.
- All color combinations must meet WCAG AAA (7:1) contrast for accessibility.
- A single screen should use **1 primary** and **at most 1 secondary** semantic color.

---

## 3. Typography

### 3.1 Font Stack

```
Primary:   "Inter", system-ui, sans-serif
Heading:   "Inter", system-ui, sans-serif  (can use 600+ weight for distinction)
Monospace: "JetBrains Mono", "Fira Code", monospace (code, IDs, counters)
```

Inter provides excellent readability at all sizes and weights. Prioritize clarity over stylistic variation.

### 3.2 Type Scale

| Role            | Size   | Weight | Line Height | Letter Spacing | Token              |
|-----------------|--------|--------|-------------|----------------|--------------------|
| Display XL      | 40 px  | 700    | 1.20        | −0.01em        | `--type-display-xl`|
| Display L       | 32 px  | 700    | 1.25        | 0              | `--type-display-l` |
| Heading 1       | 28 px  | 600    | 1.35        | 0              | `--type-h1`        |
| Heading 2       | 24 px  | 600    | 1.40        | 0              | `--type-h2`        |
| Heading 3       | 20 px  | 600    | 1.45        | 0              | `--type-h3`        |
| Heading 4       | 16 px  | 600    | 1.50        | 0              | `--type-h4`        |
| Body L          | 16 px  | 400    | 1.65        | 0              | `--type-body-l`    |
| Body M (base)   | 14 px  | 400    | 1.65        | 0              | `--type-body-m`    |
| Body S          | 13 px  | 400    | 1.60        | 0.01em         | `--type-body-s`    |
| Label / UI      | 12 px  | 500    | 1.50        | 0.03em         | `--type-label`     |
| Caption         | 11 px  | 400    | 1.50        | 0.02em         | `--type-caption`   |
| Mono / Code     | 13 px  | 400    | 1.60        | 0              | `--type-mono`      |

### 3.3 Typography Rules

- All headings are `--text-primary`. Never apply decorative colors.
- Body text is always `--text-primary` or `--text-secondary` depending on hierarchy.
- Links are `--accent-primary` with underline on hover.
- Do not use font weights below 400.
- All-caps is only permitted for `--type-label` tokens (badges, section headers, column headers).
- Line length should not exceed 75 characters for optimal readability.

---

## 4. Spacing System

Based on a **4 px grid**. All layout spacing, padding, margin, and gap values must be multiples of 4.

| Token      | Value | Common Use                               |
|------------|-------|------------------------------------------|
| `--sp-1`   | 4 px  | Inline micro-gaps (icon ↔ label)         |
| `--sp-2`   | 8 px  | Inner component padding (chips, badges)  |
| `--sp-3`   | 12 px | Input field internal padding             |
| `--sp-4`   | 16 px | Card internal padding, form rows         |
| `--sp-5`   | 20 px | Section sub-spacing                      |
| `--sp-6`   | 24 px | Card padding (standard), list row height |
| `--sp-8`   | 32 px | Section header to content gap            |
| `--sp-10`  | 40 px | Page section vertical rhythm             |
| `--sp-12`  | 48 px | Major section separators                 |
| `--sp-16`  | 64 px | Hero / page top padding                  |
| `--sp-24`  | 96 px | Full-page vertical centering offset      |

### 4.1 Layout Grid

| Context       | Columns | Gutter | Margin     |
|---------------|---------|--------|------------|
| Desktop ≥1280 | 12      | 24 px  | 48 px      |
| Tablet 768–   | 8       | 20 px  | 32 px      |
| Mobile < 768  | 4       | 16 px  | 16 px      |

### 4.2 Border Radius

| Token          | Value  | Use                                    |
|----------------|--------|----------------------------------------|
| `--radius-sm`  | 6 px   | Chips, badges, small inputs            |
| `--radius-md`  | 8 px   | Buttons, standard inputs               |
| `--radius-lg`  | 12 px  | Cards, panels                          |
| `--radius-xl`  | 16 px  | Modal dialogs, large cards             |
| `--radius-full`| 9999px | Pill buttons, avatars, progress bars   |

---

## 5. Elevation & Shadows

Green/White Clean uses **light, consistent shadows** to define depth and hierarchy.

### 5.1 Shadow Levels

| Level      | Box Shadow                                       | When to use              |
|------------|--------------------------------------------------|--------------------------|
| None       | none                                             | Flat panels, table rows  |
| Subtle     | `0 1px 2px rgba(16,20,24,0.05)`                  | Slightly raised elements |
| Raised     | `0 4px 6px rgba(16,20,24,0.08), 0 1px 3px rgba(16,20,24,0.04)` | Cards, list items  |
| Elevated   | `0 10px 15px rgba(16,20,24,0.10), 0 4px 6px rgba(16,20,24,0.05)` | Dropdowns, popovers |
| Float      | `0 20px 25px rgba(16,20,24,0.15), 0 8px 10px rgba(16,20,24,0.06)` | Floating modals    |

```css
/* Example: Raised card */
.card {
  background: rgba(255,255,255,1);
  border: 1px solid rgba(215,227,218,1);
  box-shadow: 0 4px 6px rgba(16, 20, 24, 0.08), 0 1px 3px rgba(16, 20, 24, 0.04);
  border-radius: var(--radius-lg);
}
```

### 5.2 Border Usage

Light borders define surface boundaries without heaviness.

```css
/* Standard border */
border: 1px solid var(--border-subtle);

/* Active/focused border */
border: 2px solid var(--border-active);
```

---

## 6. Iconography

### 6.1 Icon Library

**Recommended:** [Lucide Icons](https://lucide.dev/) or [Phosphor Icons](https://phosphoricons.com/) (outline/regular weight).

Rationale: Clean, friendly stroke-based icons that pair well with healthcare and admin contexts.

### 6.2 Size Tokens

| Token          | Size  | Use                                        |
|----------------|-------|--------------------------------------------|
| `--icon-xs`    | 12 px | Inline meta, badges                        |
| `--icon-sm`    | 16 px | Standard UI icons (buttons, nav items)     |
| `--icon-md`    | 20 px | List row leading icons, action icons       |
| `--icon-lg`    | 24 px | Section titles, feature icons              |
| `--icon-xl`    | 32 px | Empty states, modal headers                |
| `--icon-hero`  | 48 px | Onboarding, large feature markers          |

### 6.3 Icon Style Rules

- Use **outline** icons exclusively — no filled icons on standard UI.
- Icon color follows text context: `--text-primary` for default, `--accent-primary` for active, `--text-muted` for disabled.
- Icon + label gap: always `--sp-1` (4 px) for compact, `--sp-2` (8 px) for spacious layouts.
- All icons must scale proportionally.
- Decorative icons may use `--green-light` as a background tint.

```css
/* Active icon with green */
.icon-active {
  color: var(--accent-primary);
}

/* Icon with background tint */
.icon-decorative {
  color: var(--accent-primary);
  background: var(--green-light);
  border-radius: var(--radius-md);
  padding: var(--sp-1);
}
```

### 6.4 Icon in Context

| Context           | Size Token   | Color                  | Style    |
|-------------------|--------------|------------------------|----------|
| Navigation item   | `--icon-sm`  | `--text-secondary`     | Outline  |
| Navigation active | `--icon-sm`  | `--accent-primary`     | Outline  |
| Button (with text)| `--icon-sm`  | Inherits button color  | Outline  |
| Button (icon-only)| `--icon-md`  | `--text-primary`       | Outline  |
| Table row action  | `--icon-sm`  | `--text-secondary`     | Outline  |
| Success state     | `--icon-md`  | `--success`            | Outline  |

---

## 7. Component Patterns

### 7.1 Buttons

| Variant    | Background       | Text             | Border                    | Shadow        |
|------------|------------------|------------------|---------------------------|---------------|
| Primary    | `--accent-primary` | `rgba(255,255,255,1)`        | none                      | Subtle (7.1) |
| Secondary  | `rgba(238,244,239,1)`        | `--accent-primary` | `1px solid --border-subtle` | None         |
| Ghost      | transparent      | `--accent-primary` | `1px solid --accent-primary` | None        |
| Danger     | `rgba(254,226,226,1)`        | `rgba(220,38,38,1)`        | `1px solid rgba(254,202,202,1)`       | None         |

- Height: 36 px (compact) / 40 px (standard) / 48 px (large).
- Padding: `--sp-4` horizontal (16 px), `--sp-2` vertical (8 px) for standard.
- Border radius: `--radius-md` (8 px) standard, `--radius-full` for pill style.
- Focus: `outline: 2px solid var(--accent-primary); outline-offset: 2px`.

### 7.2 Inputs & Forms

- Background: `rgba(255,255,255,1)`, border `--border-subtle`.
- Focus: border becomes `--border-active` (2px), box-shadow adds subtle green glow.
- Error: border `rgba(220,38,38,1)`, background tint `rgba(254,226,226,1)`.
- Height: 40 px standard, 36 px compact.
- Label: `--type-label` above input, `--text-secondary` color.
- Helper/error text: `--type-caption` below input in corresponding color.
- Placeholder: `--text-muted` color.

```css
input:focus {
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 3px rgba(22, 163, 74, 0.10);
  outline: none;
}

input:invalid {
  border-color: rgba(220,38,38,1);
  box-shadow: 0 0 0 3px rgba(220, 38, 38, 0.10);
}
```

### 7.3 Cards

- Background: `rgba(255,255,255,1)` with `--border-subtle` border.
- Shadow: Raised level (see §5.1).
- Padding: `--sp-6` (24 px) all sides.
- Content hierarchy: Section label → Title → Body → Actions.
- Hover: subtle shadow lift to Elevated level.

### 7.4 Navigation (Sidebar / Top Bar)

- Background: `rgba(255,255,255,1)` with subtle border-bottom `--border-subtle`.
- Active item: `--accent-primary` text + icon, no underline, left border accent 3px `--accent-primary`.
- Inactive item: `--text-secondary`, no border.
- Hover: background becomes `--bg-secondary`, transition 150ms.
- Spacing: `--sp-4` (16 px) padding per item, `--sp-1` (4 px) gap.

### 7.5 Badges & Status Tags

| Semantic | Background       | Text         |
|----------|------------------|--------------|
| Success  | `rgba(220,252,231,1)`        | `rgba(21,128,61,1)`    |
| Warning  | `rgba(254,243,199,1)`        | `rgba(180,83,9,1)`    |
| Danger   | `rgba(254,226,226,1)`        | `rgba(220,38,38,1)`    |
| Info     | `rgba(219,234,254,1)`        | `rgba(30,64,175,1)`    |
| Neutral  | `rgba(243,244,246,1)`        | `--text-secondary` |

- Border radius: `--radius-full` (pill).
- Padding: `6px 12px`.
- Font: `--type-label`, 500 weight.
- Icon + label gap: `--sp-1` (4 px).

---

## 8. Motion & Interaction

- **Easing:** `ease-in-out` for all transitions; reserve `cubic-bezier(0.22, 1, 0.36, 1)` only for important reveals.
- **Duration:** 100 ms micro (hover, focus), 150 ms standard (page transitions), 250 ms complex (modals).
- **No glow effects.** Avoid decorative motion on data-heavy screens.
- Respect `prefers-reduced-motion` — all animations must degrade to instant toggle.

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## 9. Accessibility Requirements

- **Text contrast:** minimum 7:1 for all text on colored backgrounds (AAA standard).
- **Focus indicators:** visible, 2px solid `--accent-primary` outline with 2px offset on all interactive elements.
- **Touch targets:** minimum 44x44 px for mobile, 40x40 px for desktop.
- **Color alone should not convey meaning** — pair status colors with text or icon labels.
- **Keyboard navigation:** full keyboard support, tab order follows visual flow, no keyboard traps.
- **Forms:** associated labels, clear error messages, hint text accessible to screen readers.

---

## 10. What to Avoid

| Anti-pattern                            | Reason                                          |
|-----------------------------------------|-------------------------------------------------|
| Dark backgrounds on main canvas         | Breaks the light, open aesthetic                |
| Multiple accent colors per screen       | Creates visual confusion                        |
| Colored text (anything but links)       | Reduces contrast and accessibility              |
| Shadows stronger than Elevated level    | Creates artificial depth and clutter            |
| Animations longer than 250 ms           | Feels sluggish in a clinical context            |
| Italic text for emphasis                | Harder to read, use weight or color instead     |
| Tiny text sizes (< 13px)                | Excludes users with vision challenges           |
| Mixed rounded/sharp corner radii        | Breaks visual consistency                       |
