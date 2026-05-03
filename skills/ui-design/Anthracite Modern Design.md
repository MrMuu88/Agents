# Anthracite Modern Design Style — Ruleset

> A sophisticated, enterprise-grade aesthetic inspired by cutting-edge fintech and SaaS products. Emphasizes precision, technology, and professional confidence through dark sophisticated grays, cool accents, and refined geometry.

---

## 1. Core Philosophy

- **Dark, premium canvas.** The interface uses sophisticated dark grays that convey technology and refinement.
- **Cool purple as precision.** A bright, crisp purple accent signals confidence, clarity, and technological prowess.
- **Depth through subtle contrast.** Layered surface values create hierarchy without visual noise.
- **Geometric precision.** Clean angles, consistent spacing, and mathematical rigor define the aesthetic.
- **Performance-first interaction.** Micro-interactions feel snappy and responsive, never sluggish.

---

## 2. Color System

### 2.1 Background & Canvas

| Token                  | Value        | Usage                                            |
|------------------------|--------------|--------------------------------------------------|
| `--bg-base`            | `rgba(17,19,21,1)`    | Deepest layer — main app background              |
| `--bg-secondary`       | `rgba(21,24,27,1)`    | Page section backgrounds, alternate              |
| `--bg-surface`         | `rgba(27,31,36,1)`    | Card surfaces, elevated panels                   |
| `--bg-surface-alt`     | `rgba(35,40,49,1)`    | Alternative surface for secondary content        |
| `--bg-overlay`         | `rgba(17,19,21,0.80)` | Modal backdrop, overlays            |

### 2.2 Purple Accent Palette

A cool, bright purple signals focus, primary actions, and active states. Precise and technological.

| Token               | Value     | Hue Name             |
|---------------------|-----------|----------------------|
| `--purple-primary`  | `rgba(139,92,246,1)` | Core brand purple |
| `--purple-light`    | `rgba(167,139,250,1)` | Light purple highlight |
| `--purple-dark`     | `rgba(109,40,217,1)` | Dark purple for inactive |
| `--purple-muted`    | `rgba(139,92,246,0.20)` | Soft purple background |

### 2.3 Semantic / Functional Colors

| Token               | Value       | Usage                         |
|---------------------|-------------|-------------------------------|
| `--text-primary`    | `rgba(245,247,250,1)`   | Headings, key labels, body text |
| `--text-secondary`  | `rgba(169,178,191,1)`   | Meta, descriptions            |
| `--text-muted`      | `rgba(107,118,132,1)`   | Placeholders, disabled text   |
| `--text-inverse`    | `rgba(17,19,21,1)`   | Text on colored backgrounds   |
| `--border-subtle`   | `rgba(44,52,64,1)`   | Default borders, dividers     |
| `--border-active`   | `rgba(139,92,246,1)`   | Focused / active borders      |
| `--accent-primary`  | `rgba(139,92,246,1)`   | Primary CTA, links, active nav|
| `--accent-muted`    | `rgba(139,92,246,0.20)` | Soft accent backgrounds |
| `--danger`          | `rgba(255,93,108,1)`   | Errors, destructive actions   |
| `--warning`         | `rgba(255,184,77,1)`   | Warnings, caution             |
| `--success`         | `rgba(139,92,246,1)`   | Success, confirmations        |
| `--info`            | `rgba(75,159,255,1)`   | Informational, secondary CTA  |

### 2.4 Color Usage Rules

- Purple is used consistently for all primary and active states.
- Red is reserved for errors, deletions, and destructive actions only.
- Backgrounds should remain in the dark gray range — never introduce warm or pastel tones.
- All color combinations must meet WCAG AA (4.5:1) contrast minimum.
- A single screen should use **1 primary** and **at most 1 secondary** semantic color.

---

## 3. Typography

### 3.1 Font Stack

```
Primary:   "Inter", system-ui, sans-serif
Heading:   "Manrope", "Inter", system-ui, sans-serif  (geometric, modern feel)
Monospace: "JetBrains Mono", "Fira Code", monospace (code, IDs, counters)
```

Inter is the default. Manrope may be used on display headings for a more geometric, premium feel. Both provide excellent legibility in dark mode.

### 3.2 Type Scale

| Role            | Size   | Weight | Line Height | Letter Spacing | Token              |
|-----------------|--------|--------|-------------|----------------|--------------------|
| Display XL      | 40 px  | 700    | 1.15        | −0.02em        | `--type-display-xl`|
| Display L       | 32 px  | 700    | 1.20        | −0.01em        | `--type-display-l` |
| Heading 1       | 24 px  | 600    | 1.30        | −0.005em       | `--type-h1`        |
| Heading 2       | 20 px  | 600    | 1.35        | 0              | `--type-h2`        |
| Heading 3       | 16 px  | 600    | 1.40        | 0              | `--type-h3`        |
| Heading 4       | 14 px  | 600    | 1.45        | 0              | `--type-h4`        |
| Body L          | 16 px  | 400    | 1.60        | 0              | `--type-body-l`    |
| Body M (base)   | 14 px  | 400    | 1.60        | 0              | `--type-body-m`    |
| Body S          | 13 px  | 400    | 1.55        | 0.01em         | `--type-body-s`    |
| Label / UI      | 12 px  | 500    | 1.40        | 0.04em         | `--type-label`     |
| Caption         | 11 px  | 400    | 1.40        | 0.02em         | `--type-caption`   |
| Mono / Code     | 13 px  | 400    | 1.50        | 0              | `--type-mono`      |

### 3.3 Typography Rules

- All headings are `--text-primary`. Never apply decorative colors.
- Body text is always `--text-primary` or `--text-secondary` depending on hierarchy.
- Links are `--accent-primary` without underline by default; underline on hover.
- Do not use font weights below 400.
- All-caps is only permitted for `--type-label` tokens (badges, section headers, column headers).
- Limit line length to 75–90 characters for optimal readability in dark mode.

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
| `--sp-16`  | 64 px | Hero / dashboard top padding             |
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
| `--radius-md`  | 10 px  | Buttons, standard inputs               |
| `--radius-lg`  | 14 px  | Cards, panels                          |
| `--radius-xl`  | 20 px  | Modal dialogs, floating surfaces       |
| `--radius-full`| 9999px | Pill buttons, avatars, progress bars   |

---

## 5. Elevation & Shadows

Anthracite Modern uses **restrained, single-layer shadows** to define depth without visual noise.

### 5.1 Shadow Levels

| Level      | Box Shadow                                       | When to use              |
|------------|--------------------------------------------------|--------------------------|
| None       | none                                             | Flat panels, table rows  |
| Subtle     | `0 2px 8px rgba(0,0,0,0.30)`                     | Slightly raised elements |
| Raised     | `0 4px 16px rgba(0,0,0,0.40)`                    | Cards, list items        |
| Elevated   | `0 8px 24px rgba(0,0,0,0.50)`                    | Dropdowns, tooltips      |
| Float      | `0 12px 32px rgba(0,0,0,0.60)`                   | Floating modals, drawers |

```css
/* Example: Raised card */
.card {
  background: rgba(27,31,36,1);
  border: 1px solid rgba(44,52,64,1);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.40);
  border-radius: var(--radius-lg);
}
```

### 5.2 Border Usage

Dark borders define surface boundaries subtly.

```css
/* Standard border */
border: 1px solid var(--border-subtle);

/* Active/focused border */
border: 1px solid var(--border-active);
```

---

## 6. Iconography

### 6.1 Icon Library

**Recommended:** [Lucide Icons](https://lucide.dev/) or [Phosphor Icons](https://phosphoricons.com/) (outline/regular weight).

Rationale: Geometric, precise icons that match the technical aesthetic of Anthracite Modern.

### 6.2 Size Tokens

| Token          | Size  | Use                                        |
|----------------|-------|--------------------------------------------|
| `--icon-xs`    | 12 px | Inline meta, badges                        |
| `--icon-sm`    | 16 px | Standard UI icons (buttons, nav items)     |
| `--icon-md`    | 20 px | List row leading icons, action icons       |
| `--icon-lg`    | 24 px | Section titles, feature icons              |
| `--icon-xl`    | 32 px | Empty states, modal headers                |
| `--icon-hero`  | 48 px | Dashboard hero, large feature markers      |

### 6.3 Icon Style Rules

- Use **outline** icons exclusively — no filled icons on standard UI.
- Icon color follows text context: `--text-primary` for default, `--accent-primary` for active, `--text-muted` for disabled.
- Icon + label gap: `--sp-1` (4 px) for compact, `--sp-2` (8 px) for spacious layouts.
- All icons must scale proportionally.
- Decorative icons may use `--accent-muted` as background tint.

```css
/* Active icon with purple */
.icon-active {
  color: var(--accent-primary);
}

/* Icon with muted purple background */
.icon-decorative {
  color: var(--accent-primary);
  background: var(--accent-muted);
  border-radius: var(--radius-md);
  padding: var(--sp-2);
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
| Success indicator | `--icon-md`  | `--accent-primary`     | Outline  |

---

## 7. Component Patterns

### 7.1 Buttons

| Variant    | Background       | Text             | Border                    | Shadow        |
|------------|------------------|------------------|---------------------------|---------------|
| Primary    | `--accent-primary` | `rgba(17,19,21,1)`        | none                      | Subtle (5.1) |
| Secondary  | `rgba(35,40,49,1)`        | `--text-primary` | `1px solid --border-subtle` | None         |
| Ghost      | transparent      | `--accent-primary` | `1px solid --accent-primary` | None        |
| Danger     | `rgba(255,93,108,0.15)` | `rgba(255,93,108,1)` | `1px solid rgba(255,93,108,0.40)` | None    |

- Height: 36 px (compact) / 40 px (standard) / 48 px (large).
- Padding: `--sp-4` horizontal (16 px), `--sp-2` vertical (8 px) for standard.
- Border radius: `--radius-md` (10 px) standard, `--radius-full` for pill style.
- Focus: `outline: 2px solid var(--accent-primary); outline-offset: 2px`.

### 7.2 Inputs & Forms

- Background: `rgba(35,40,49,1)`, border `--border-subtle`.
- Focus: border becomes `--border-active`, subtle glow shadow added.
- Error: border `rgba(255,93,108,1)`, background tint `rgba(255,93,108,0.10)`.
- Height: 40 px standard, 36 px compact.
- Label: `--type-label` above input, `--text-secondary` color.
- Helper/error text: `--type-caption` below input in corresponding color.
- Placeholder: `--text-muted` color.

```css
input:focus {
  border-color: var(--accent-primary);
  box-shadow: 0 0 0 3px rgba(139, 92, 246, 0.15);
  outline: none;
}

input:invalid {
  border-color: rgba(255,93,108,1);
  box-shadow: 0 0 0 3px rgba(255, 93, 108, 0.15);
}
```

### 7.3 Cards

- Background: `rgba(27,31,36,1)` with `--border-subtle` border.
- Shadow: Raised level (see §5.1).
- Padding: `--sp-6` (24 px) all sides.
- Content hierarchy: Section label → Title → Body → Actions.
- Hover: subtle shadow lift to Elevated level, no background change.

### 7.4 Navigation (Sidebar / Top Bar)

- Background: `rgba(21,24,27,1)` with subtle border-bottom `--border-subtle`.
- Active item: `--accent-primary` text + icon, left border accent 2px `--accent-primary`, subtle background `rgba(139,92,246,0.08)`.
- Inactive item: `--text-secondary`, no border or background.
- Hover: text becomes `--text-primary`, transition 150ms ease-in-out.
- Spacing: `--sp-4` (16 px) padding per item, `--sp-1` (4 px) gap.

### 7.5 Badges & Status Tags

| Semantic | Background               | Text         |
|----------|--------------------------|--------------|
| Success  | `rgba(139,92,246,0.20)`  | `rgba(139,92,246,1)`    |
| Warning  | `rgba(255,184,77,0.20)`  | `rgba(255,184,77,1)`    |
| Danger   | `rgba(255,93,108,0.20)`  | `rgba(255,93,108,1)`    |
| Info     | `rgba(75,159,255,0.20)`  | `rgba(75,159,255,1)`    |
| Neutral  | `rgba(44,52,64,1)`                | `--text-secondary` |

- Border radius: `--radius-full` (pill).
- Padding: `6px 12px`.
- Font: `--type-label`, 500 weight.
- Icon + label gap: `--sp-1` (4 px).

---

## 8. Motion & Interaction

- **Easing:** `cubic-bezier(0.22, 1, 0.36, 1)` (ease-out spring) for entrances and reveals; `ease-in-out` for toggles.
- **Duration:** 120 ms micro (hover, focus), 200 ms standard (panel transitions), 300 ms complex (modals, drawers).
- **Snappy feel.** Interactions should feel responsive and immediate, never laggy.
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

- **Text contrast:** minimum 4.5:1 for body text (`--text-secondary` on `--bg-base`), 3:1 for large headings.
- **Focus indicators:** visible 2px solid `--accent-primary` outline with 2px offset on all interactive elements.
- **Touch targets:** minimum 44x44 px for mobile, 40x40 px for desktop.
- **Color alone should not convey meaning** — pair status colors with text or icon labels.
- **Keyboard navigation:** full keyboard support, tab order follows visual flow, no keyboard traps.
- **Forms:** associated labels, clear error messages, hint text accessible to screen readers.

---

## 10. What to Avoid

| Anti-pattern                            | Reason                                          |
|-----------------------------------------|-------------------------------------------------|
| Light backgrounds on main canvas        | Breaks the dark, sophisticated aesthetic        |
| Warm colors mixed with cool purple      | Creates visual discord                          |
| Multiple accent colors per screen       | Creates confusion in a precision-focused style  |
| Shadows stronger than Float level       | Creates excessive visual noise                  |
| Animations longer than 300 ms           | Feels sluggish in a snappy, tech-focused UI     |
| Neon glow effects                       | Conflicts with the refined, restrained aesthetic |
| Colored text (anything but links)       | Reduces contrast and sophistication             |
| Rounded corners everywhere              | Use `--radius-md` consistently, not mixed       |
