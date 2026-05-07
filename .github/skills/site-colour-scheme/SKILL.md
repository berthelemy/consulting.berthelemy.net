---
name: site-colour-scheme
description: 'Apply or extend the site colour scheme consistently, including a dark mode variant. Use when adding new pages, components, or templates that must match the existing palette, or when implementing CSS dark mode support.'
argument-hint: 'Component or page being styled, and any colour constraints'
user-invocable: true
---

# Site Colour Scheme and Dark Mode

Apply the established site palette consistently and implement dark mode support using CSS custom properties, so every new or modified component matches the existing design without introducing ad-hoc colour values.

## When to Use
- Styling a new page, section, layout, or include.
- Adding a Bootstrap 5 component that needs to match the site palette.
- Implementing or extending dark mode across pages or components.
- Auditing existing markup for off-palette colour values.

## Established Colour Palette

These are the canonical design tokens for this site, sourced from `assets/sass/libs/_vars.scss` and `assets/css/overrides.scss`.

| Token | Value | Purpose |
|---|---|---|
| `bg` | `#312450` | Page background |
| `bg-alt` | `darken(#312450, 5)` ≈ `#261b3d` | Alternate / recessed background |
| `fg` | `rgba(255,255,255,0.55)` | Body text |
| `fg-bold` | `#ffffff` | Headings and emphasis |
| `fg-light` | `rgba(255,255,255,0.35)` | Muted / secondary text |
| `border` | `rgba(255,255,255,0.15)` | Dividers and borders |
| `border-bg` | `rgba(255,255,255,0.05)` | Subtle background tint |
| `accent1` | `#5e42a6` | Primary interactive colour |
| `accent1-alt` | `darken(#5e42a6, 10)` ≈ `#4a3382` | Hover/active state for accent1 |
| `accent2` | `#5052b5` | Secondary interactive colour |
| `accent2-alt` | `darken(#5052b5, 10)` ≈ `#3c3e91` | Hover/active state for accent2 |
| `accent3` | `#b74e91` | Highlight / call-to-action colour |
| `accent3-alt` | `darken(#b74e91, 10)` ≈ `#93366e` | Hover/active state for accent3 |
| Logo text | `#77228f` | Logo foreground |
| Logo hover | `#a752bf` | Logo hover state |
| Wrapper style1/1-alt | `#333` | Content section background |
| Wrapper style2/2-alt | `#222` | Deep content section background |
| Wrapper style3/3-alt | `#444` | Light-variant content section background |

## Workflow
1. Map existing palette tokens to CSS custom properties.
2. Apply light-mode (default) values.
3. Define dark-mode overrides via `prefers-color-scheme: dark` or a `data-theme` attribute.
4. Apply tokens to new or modified components.
5. Validate contrast, consistency, and dark mode rendering.

## Detailed Procedure

### 1) Define CSS Custom Properties
Declare tokens as CSS custom properties on `:root` so Bootstrap utilities and custom rules share the same values.

```css
:root {
  --color-bg:         #312450;
  --color-bg-alt:     #261b3d;
  --color-fg:         rgba(255, 255, 255, 0.55);
  --color-fg-bold:    #ffffff;
  --color-fg-light:   rgba(255, 255, 255, 0.35);
  --color-border:     rgba(255, 255, 255, 0.15);
  --color-border-bg:  rgba(255, 255, 255, 0.05);
  --color-accent1:    #5e42a6;
  --color-accent1-alt:#4a3382;
  --color-accent2:    #5052b5;
  --color-accent2-alt:#3c3e91;
  --color-accent3:    #b74e91;
  --color-accent3-alt:#93366e;
}
```

Decision points:
- If the project already defines SCSS variables in `_vars.scss`, generate the custom properties from those values rather than duplicating them.
- Prefer `var(--color-*)` in new CSS over referencing SCSS variables directly, so the dark-mode override layer can work without recompiling SCSS.

### 2) Apply Light Mode (Default)
- Use `var(--color-bg)` for page and section backgrounds.
- Use `var(--color-fg)` for body text; `var(--color-fg-bold)` for headings.
- Use `var(--color-accent1)` for primary links and buttons; `var(--color-accent1-alt)` for `:hover`/`:focus`.
- Use `var(--color-accent3)` for calls-to-action and highlights.
- Map Bootstrap 5 theme variables to site tokens in SCSS where applicable:
  ```scss
  $primary:   #5e42a6;
  $secondary: #5052b5;
  $body-bg:   #312450;
  $body-color: rgba(255,255,255,0.55);
  ```

Quality checks:
- No hex or rgba values appear directly in component CSS — all colours reference `var(--color-*)` tokens.
- Interactive elements use accent colours, not generic greys.

### 3) Define Dark Mode Overrides
The site is already dark-by-default. Dark mode should deepen backgrounds and increase contrast.

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-bg:        #1a1030;
    --color-bg-alt:    #120b22;
    --color-fg:        rgba(255, 255, 255, 0.75);
    --color-fg-light:  rgba(255, 255, 255, 0.50);
    --color-border:    rgba(255, 255, 255, 0.20);
  }
}
```

For user-toggleable dark mode, add a `data-theme="dark"` attribute on `<html>` and scope overrides to `[data-theme="dark"] :root` or `[data-theme="dark"]` directly.

Decision points:
- If the site only needs OS-level dark mode, use `prefers-color-scheme` only.
- If a manual toggle is required, use `data-theme` combined with a small JavaScript toggle that persists preference to `localStorage`.

Quality checks:
- Dark mode renders no new contrast failures (re-run contrast checks after applying overrides).
- Light mode is unaffected when `prefers-color-scheme: light` is active.

### 4) Apply to Components
- Replace any hardcoded colour in Bootstrap component overrides with `var(--color-*)` equivalents.
- For wrapper sections (`style1`, `style2`, `style3`), derive tokens rather than hardcoding `#333`, `#222`, `#444`:
  ```scss
  .wrapper.style1    { background-color: var(--color-bg-alt); }
  .wrapper.style2    { background-color: #222; } // deepest — define as --color-bg-deep if reused
  .wrapper.style3    { background-color: #444; } // lightest section — define as --color-bg-light if reused
  ```

### 5) Validation
- Verify all text/background combinations against WCAG 2.2 AA contrast minimums (≥4.5:1 normal text, ≥3:1 large text).
- Toggle OS dark mode and confirm no element reverts to an off-palette value.
- Confirm the colour scheme renders correctly in a deployed build, not only in local SCSS output.

Completion criteria — **all must pass**:
- All colours in new/modified components reference `var(--color-*)` tokens — no ad-hoc values.
- Light and dark mode both pass WCAG 2.2 AA contrast for all text and interactive elements.
- Bootstrap component overrides use site tokens.
- Dark mode activates correctly via `prefers-color-scheme` (and `data-theme` if a toggle is implemented).
- No existing pages are visually broken by the changes.

## Common Anti-Patterns to Avoid
- Copying hex values inline rather than referencing tokens.
- Adding a Bootstrap `bg-dark` class while the site already uses a custom dark palette.
- Defining dark mode only in SCSS without a CSS custom property layer, making runtime toggles impossible.
- Using `!important` to override Bootstrap colours instead of properly setting Bootstrap SCSS variables.

## Deliverables
- Updated or new CSS/SCSS with `var(--color-*)` token usage.
- Dark mode override block (media query and/or `data-theme` selector).
- Contrast check results for light and dark modes.
- Notes on any palette gaps (missing tokens for new components) and proposed additions.

## Example Prompts
- /site-colour-scheme Style this new card component to match the site palette with dark mode support.
- /site-colour-scheme Audit existing pages for off-palette colour values and replace them with tokens.
- /site-colour-scheme Add a user-toggleable dark mode to the site with localStorage persistence.
