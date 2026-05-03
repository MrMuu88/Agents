# Aurora Design Style — Ruleset

> Inspired by the Aurora Borealis (Northern Lights): deep cosmic darkness, soft luminous gradients that bleed and blend across surfaces, layered glassmorphism, and a calm otherworldly glow. This style balances drama with readability — premium, ethereal, and focused.

---

## 1. Core Philosophy

- **Dark canvas, luminous content.** The interface lives on near-black backgrounds where colored light emanates from elements, not from the background itself.
- **Gradient as atmosphere.** Aurora gradients are ambient — wide, soft, slow-moving color fields. They set mood without distraction.
- **Glass as depth.** Surfaces are semi-transparent frosted glass panels that sit above the gradient layer, giving dimensionality without harsh shadows.
- **Purposeful glow.** Glow effects are reserved for active states, primary actions, and key data. Never decorative noise.
- **Contrast-first readability.** Despite the dark palette, text must remain crisp — minimum 4.5:1 contrast on all body text.

---

## 2. Color System

### 2.1 Background & Canvas

| Token                  | Value        | Usage                                            |
|------------------------|--------------|--------------------------------------------------|
| `--bg-base`            | `rgba(8,12,20,1)`    | Deepest layer — main app background              |
| `--bg-mid`             | `rgba(13,18,32,1)`    | Secondary pages, panels                          |
| `--bg-surface`         | `rgba(255,255,255,0.05)` | Glass card base (frosted surface)   |
| `--bg-surface-hover`   | `rgba(255,255,255,0.08)` | Hovered glass surface                |
| `--bg-overlay`         | `rgba(8,12,20,0.72)`     | Modals, drawers backdrop             |

### 2.2 Aurora Gradient Palette

Aurora accent colors are used for ambient gradients, glows, and highlights. **Never apply raw as solid fills on UI controls** — blend them via gradients or opacity layers.

| Token              | Value     | Hue Name         |
|--------------------|-----------|------------------|
| `--aurora-teal`    | `rgba(0,232,200,1)` | Arctic Teal      |
| `--aurora-green`   | `rgba(61,255,154,1)` | Boreal Green     |
| `--aurora-blue`    | `rgba(75,159,255,1)` | Polar Blue       |
| `--aurora-violet`  | `rgba(139,92,246,1)` | Deep Violet      |
| `--aurora-magenta` | `rgba(224,64,251,1)` | Solar Magenta    |
| `--aurora-warm`    | `rgba(255,184,106,1)` | Twilight Amber   |

#### Ambient Background Gradient (reference)
```css
background: radial-gradient(ellipse 80% 60% at 20% 30%, rgba(0,232,200,0.12) 0%, transparent 60%),
            radial-gradient(ellipse 60% 50% at 80% 70%, rgba(139,92,246,0.14) 0%, transparent 60%),
            radial-gradient(ellipse 50% 40% at 50% 100%, rgba(75,159,255,0.10) 0%, transparent 55%),
            rgba(8,12,20,1);
```

### 2.3 Semantic / Functional Colors

| Token               | Value       | Usage                         |
|---------------------|-------------|-------------------------------|
| `--text-primary`    | `rgba(237,242,255,1)`   | Headings, key labels          |
| `--text-secondary`  | `rgba(139,155,187,1)`   | Meta, descriptions            |
| `--text-muted`      | `rgba(74,86,112,1)`   | Placeholders, disabled text   |
| `--text-inverse`    | `rgba(8,12,20,1)`   | Text on light/glow surfaces   |
| `--border-subtle`   | `rgba(255,255,255,0.08)` | Card and panel borders |
| `--border-active`   | `rgba(0,232,200,0.40)`   | Focused / active borders |
| `--accent-primary`  | `rgba(0,232,200,1)`   | Primary CTA, links, active nav|
| `--accent-glow`     | `rgba(0,232,200,0.25)`   | Glow halo behind CTAs  |
| `--danger`          | `rgba(255,83,112,1)`   | Errors, destructive actions   |
| `--warning`         | `rgba(255,184,106,1)`   | Warnings                      |
| `--success`         | `rgba(61,255,154,1)`   | Confirmations, success badges |

### 2.4 Color Usage Rules

- **Do not** use raw aurora values (`--aurora-*`) as button fill colors.
- **Do** blend them in `linear-gradient` or `radial-gradient` with opacity ≤ 30% for backgrounds.
- Primary button uses `--accent-primary` with a subtle glow (`box-shadow: 0 0 18px var(--accent-glow)`).
- Destructive actions use `--danger` only — never mix aurora hues with error states.
- A single screen should use **at most 2 aurora hues** in ambient gradients.

---

## 3. Typography

### 3.1 Font Stack

```
Primary:   "Inter", "Manrope", system-ui, sans-serif
Monospace: "JetBrains Mono", "Fira Code", monospace   (code, IDs, counters)
```

Inter is the baseline. Manrope may be used for display headings only if a softer, geometric feel is preferred.

### 3.2 Type Scale

| Role            | Size   | Weight | Line Height | Letter Spacing | Token              |
|-----------------|--------|--------|-------------|----------------|--------------------|
| Display XL      | 40 px  | 700    | 1.15        | −0.02em        | `--type-display-xl`|
| Display L       | 32 px  | 700    | 1.20        | −0.01em        | `--type-display-l` |
| Heading 1       | 24 px  | 600    | 1.30        | 0              | `--type-h1`        |
| Heading 2       | 20 px  | 600    | 1.35        | 0              | `--type-h2`        |
| Heading 3       | 16 px  | 600    | 1.40        | 0              | `--type-h3`        |
| Body L          | 16 px  | 400    | 1.60        | 0              | `--type-body-l`    |
| Body M (base)   | 14 px  | 400    | 1.60        | 0              | `--type-body-m`    |
| Body S          | 13 px  | 400    | 1.55        | 0.01em         | `--type-body-s`    |
| Label / UI      | 12 px  | 500    | 1.40        | 0.04em         | `--type-label`     |
| Caption         | 11 px  | 400    | 1.40        | 0.02em         | `--type-caption`   |
| Mono / Code     | 13 px  | 400    | 1.50        | 0              | `--type-mono`      |

### 3.3 Typography Rules

- Headings are always `--text-primary`. Never apply aurora gradient directly to body text.
- **Gradient text** is allowed **only** on Display headings (max 1 per screen) using `background-clip: text`.
  ```css
  background: linear-gradient(90deg, rgba(0,232,200,1) 0%, rgba(139,92,246,1) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  ```
- Secondary/meta text must meet WCAG AA (4.5:1 on `--bg-base`).
- Do not use font weights below 400 in UI.
- All-caps is only permitted for `--type-label` tokens (badges, section headers, table column headers).

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
| `--sp-16`  | 64 px | Hero / splash top padding                |
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

## 5. Elevation & Glassmorphism

Aurora UI uses **glass layers** instead of traditional drop shadows. Depth is created through:
1. Background gradient bleeding through the frosted pane.
2. A hairline border of subtle luminosity.
3. Optional radial glow spot behind elevated elements.

### 5.1 Glass Surface Levels

| Level   | Background                       | Blur      | Border                                    | When to use              |
|---------|----------------------------------|-----------|-------------------------------------------|--------------------------|
| Base    | `rgba(255,255,255,0.04)`         | 0         | `1px solid rgba(255,255,255,0.07)`        | Flat panels, table rows  |
| Raised  | `rgba(255,255,255,0.06)`         | `blur(12px)` | `1px solid rgba(255,255,255,0.11)`     | Cards, list items        |
| Float   | `rgba(255,255,255,0.09)`         | `blur(20px)` | `1px solid rgba(255,255,255,0.16)`     | Dropdowns, popovers      |
| Modal   | `rgba(13,18,32,0.88)`            | `blur(32px)` | `1px solid rgba(255,255,255,0.12)`     | Modal dialogs, drawers   |

```css
/* Example: Raised card */
.card {
  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.11);
  border-radius: var(--radius-lg);
}
```

### 5.2 Glow Halos

Glow is used sparingly — only for primary CTAs, active states, and key data points.

```css
/* Primary button glow */
box-shadow: 0 0 0 1px rgba(0,232,200,0.30),
            0 0 20px rgba(0,232,200,0.20),
            0 4px 12px rgba(0,0,0,0.40);

/* Active nav item indicator */
box-shadow: 0 0 10px rgba(0,232,200,0.50);
```

---

## 6. Iconography

### 6.1 Icon Library

**Recommended:** [Lucide Icons](https://lucide.dev/) or [Phosphor Icons](https://phosphoricons.com/) (outline/regular weight).

Rationale: Both libraries offer consistent stroke weight, clean geometry, and excellent coverage for application UI.

### 6.2 Size Tokens

| Token          | Size  | Use                                        |
|----------------|-------|--------------------------------------------|
| `--icon-xs`    | 12 px | Inline meta, badges                        |
| `--icon-sm`    | 16 px | Standard UI icons (buttons, nav items)     |
| `--icon-md`    | 20 px | List row leading icons, action icons       |
| `--icon-lg`    | 24 px | Section titles, feature icons              |
| `--icon-xl`    | 32 px | Empty states, modal headers                |
| `--icon-hero`  | 48 px | Onboarding, illustration-level markers     |

### 6.3 Icon Style Rules

- Use **outline** (1.5–2 px stroke) icons exclusively — filled icons only for active/selected toggles.
- Icons should feel soft and calm: use a **single icon color per screen**.
- Recommended icon color: `rgba(165,188,224,1)` for default and active states, with opacity shifts for hierarchy.
- Icon + label gap: always `--sp-1` (4 px) or `--sp-2` (8 px) depending on size.
- Never scale icons non-proportionally.
- Avoid multicolor or gradient-filled icons; Aurora gradients belong to atmosphere layers, not icon glyphs.

```css
/* Soft single-color icon */
.icon-soft {
  color: rgba(165,188,224,1);
  opacity: 0.9;
}
```

### 6.4 Icon in Context

| Context           | Size Token   | Color                  | Style    |
|-------------------|--------------|------------------------|----------|
| Navigation item   | `--icon-sm`  | `--text-secondary`     | Outline  |
| Navigation active | `--icon-sm`  | `rgba(165,188,224,1)`  | Outline  |
| Button (with text)| `--icon-sm`  | Inherits button color  | Outline  |
| Button (icon-only)| `--icon-md`  | `rgba(165,188,224,1)`  | Outline  |
| Table row action  | `--icon-sm`  | `rgba(165,188,224,0.80)` | Outline |
| Empty state       | `--icon-xl`  | `rgba(165,188,224,0.70)` | Outline |

---

## 7. Component Patterns

### 7.1 Buttons

| Variant    | Background                              | Text             | Border                          | Glow              |
|------------|-----------------------------------------|------------------|---------------------------------|-------------------|
| Primary    | `linear-gradient(135deg, rgba(0,232,200,1), rgba(75,159,255,1))` | `rgba(8,12,20,1)`   | none                            | Yes (see §5.2)    |
| Secondary  | `rgba(255,255,255,0.07)`                | `--text-primary` | `1px solid rgba(255,255,255,0.13)` | No             |
| Ghost      | transparent                             | `--accent-primary` | `1px solid --accent-primary`  | No                |
| Danger     | `rgba(255,83,112,0.15)`                 | `rgba(255,83,112,1)`        | `1px solid rgba(255,83,112,0.40)` | No              |

- Height: 36 px (compact) / 40 px (standard) / 48 px (large).
- Padding: `--sp-4` horizontal (16 px), `--sp-2` vertical (8 px) for standard.
- Border radius: `--radius-md` (10 px) standard, `--radius-full` for pill style.

### 7.2 Inputs & Forms

- Background: `rgba(255,255,255,0.05)`, border `rgba(255,255,255,0.10)`.
- Focus: border becomes `rgba(0,232,200,0.50)`, inner shadow `0 0 0 3px rgba(0,232,200,0.12)`.
- Error: border `rgba(255,83,112,0.60)`, inner shadow in danger color.
- Height: 40 px standard.
- Label: `--type-label` (12 px / 500 / 0.04em) above input, `--text-secondary` color.
- Helper/error text: `--type-caption` below input.

### 7.3 Cards

- Glass Raised surface (see §5.1).
- Padding: `--sp-6` (24 px) all sides.
- Content hierarchy: Section label → Title → Body → Actions.
- Optional: thin aurora accent top border as visual category marker:
  ```css
  border-top: 2px solid rgba(0,232,200,0.45);
  ```

### 7.4 Navigation (Sidebar / Top Bar)

- Background: `--bg-mid` with `backdrop-filter: blur(16px)`.
- Active item: `--accent-primary` text + icon, left border marker 2px `--accent-primary`, subtle row highlight `rgba(0,232,200,0.08)`.
- Inactive item: `--text-secondary`, no border.
- Spacing between nav items: `--sp-1` (4 px) gap.

### 7.5 Badges & Status Tags

| Semantic | Background               | Text         |
|----------|--------------------------|--------------|
| Success  | `rgba(61,255,154,0.15)`  | `rgba(61,255,154,1)`    |
| Warning  | `rgba(255,184,106,0.15)` | `rgba(255,184,106,1)`    |
| Danger   | `rgba(255,83,112,0.15)`  | `rgba(255,83,112,1)`    |
| Info     | `rgba(75,159,255,0.15)`  | `rgba(75,159,255,1)`    |
| Neutral  | `rgba(255,255,255,0.08)` | `--text-secondary` |

- Border radius: `--radius-full` (pill).
- Padding: `4px 10px`.
- Font: `--type-label`.

---

## 8. Motion & Interaction

- **Easing:** `cubic-bezier(0.22, 1, 0.36, 1)` (ease-out spring) for entrances; `ease-in-out` for state toggles.
- **Duration:** 150 ms micro (hover, focus), 220 ms standard (panel open/close), 350 ms page transitions.
- **Glow pulse** (active indicators only): 2 s `ease-in-out` infinite, opacity oscillates 0.4→0.9.
- Avoid: bounce, overshoot, or spring on data-heavy tables.
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

- **Text contrast:** minimum 4.5:1 for body (`--text-secondary` on `--bg-base`), 3:1 for large headings.
- **Focus rings:** visible outline on all interactive elements — use `outline: 2px solid var(--accent-primary); outline-offset: 3px`.
- **Glassmorphism caveat:** Always test `backdrop-filter` surfaces — if blur reduces contrast below 4.5:1, add a solid color fallback background.
- **Don't convey information by color alone** — pair color badges with icon or text label.
- **Keyboard navigation:** tab order must follow visual order. All interactive elements must be reachable.

---

## 10. What to Avoid

| Anti-pattern                            | Reason                                          |
|-----------------------------------------|-------------------------------------------------|
| Full-saturation aurora fills on surfaces| Destroys readability; aurora is ambient, not fill|
| More than 2 aurora hues per screen      | Causes visual noise and unfocused atmosphere    |
| Glow on every element                   | Glow loses meaning; reserve for primary actions |
| Gradient text on body/meta              | Reduces legibility at small sizes               |
| White or light backgrounds              | Breaks the dark-canvas paradigm                 |
| Hard opaque shadows (box-shadow black)  | Clashes with glass aesthetic                    |
| Mixing aurora with bright warm tones    | Breaks the cool-spectrum consistency            |
| Animation on every render               | Creates distraction and performance cost        |
