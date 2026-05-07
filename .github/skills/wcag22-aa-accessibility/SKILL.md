---
name: wcag22-aa-accessibility
description: 'Audit and remediate a website to meet WCAG 2.2 Level AA accessibility. Use when checking or fixing perceivability, operability, understandability, and robustness across pages, components, forms, navigation, and interactive elements.'
argument-hint: 'Page or component scope, known issues, and target output (audit report, remediated markup, or both)'
user-invocable: true
---

# WCAG 2.2 Level AA Accessibility

Evaluate and remediate site content and markup so it meets WCAG 2.2 Level AA success criteria across all four principles: Perceivable, Operable, Understandable, Robust.

## When to Use
- Auditing an existing page or site for accessibility compliance.
- Remediating failing markup, color, or interaction patterns.
- Reviewing a new feature or template before publication.
- Establishing a site-wide accessibility baseline.

## Inputs to Gather
- Scope: full site, specific page type, or single component.
- Output required: audit findings only, remediated code, or both.
- Known assistive technology targets (screen readers, keyboard-only, voice control).
- Any existing audit results or known issues to prioritize.

If scope is unclear, default to auditing the whole site and producing both findings and remediated code.

## Workflow
1. Audit perceivability (content, images, color, structure).
2. Audit operability (keyboard, timing, focus, navigation).
3. Audit understandability (language, predictability, input assistance).
4. Audit robustness (valid markup, name/role/value, assistive technology compatibility).
5. Produce prioritized findings.
6. Remediate all Level A and AA failures.
7. Verify fixes against each success criterion.

## Detailed Procedure

### 1) Perceivable (WCAG Principle 1)

**Text alternatives (1.1)**
- All non-decorative images have meaningful `alt` text describing purpose, not appearance.
- Decorative images use `alt=""` and no `role`.
- Functional images (buttons, links with images) describe the action/destination.

**Time-based media (1.2) — if present**
- Pre-recorded audio has a text transcript.
- Pre-recorded video has captions and audio description.

**Adaptable content (1.3)**
- Information conveyed through structure, not only through visual presentation.
- Reading order is correct when CSS is removed.
- Instructions do not rely solely on sensory characteristics (colour, shape, position).
- Content is not restricted to a single orientation (portrait/landscape lock fails — 1.3.4 AA).
- Input purpose is programmatically determinable for common fields (1.3.5 AA).

**Distinguishable (1.4)**
- Text contrast is ≥ 4.5:1 for normal text, ≥ 3:1 for large text (≥18pt / ≥14pt bold) (1.4.3 AA).
- Text can be resized to 200% without loss of content or functionality (1.4.4 AA).
- Images of text are avoided except for logotypes (1.4.5 AA).
- Content reflows without horizontal scrolling at 320px equivalent viewport width (1.4.10 AA).
- Non-text contrast for UI components and focus indicators is ≥ 3:1 (1.4.11 AA).
- Text spacing overrides (line/letter/word spacing) do not break layout (1.4.12 AA).
- Content triggered on hover/focus can be dismissed, hovered over, and persists (1.4.13 AA).

Quality checks:
- Run a color contrast check on all body text, headings, placeholder text, and interactive element labels.
- Verify reflow by setting viewport to 320px width.

**Fail conditions:**
- Any normal text falls below 4.5:1 contrast.
- Any interactive element or focus indicator falls below 3:1 contrast.
- Zoom to 200% causes content loss or horizontal overflow.

---

### 2) Operable (WCAG Principle 2)

**Keyboard accessible (2.1)**
- All functionality is operable without a mouse.
- No keyboard trap prevents focus from leaving a component (2.1.2).
- Character key shortcuts, if present, can be disabled or remapped (2.1.4 AA).

**Enough time (2.2)**
- Time limits can be turned off, adjusted, or extended unless essential.
- No content blinks, moves, or auto-updates in a way that cannot be paused.

**Seizures and physical reactions (2.3)**
- No content flashes more than 3 times per second.

**Navigable (2.4)**
- Blocks of content can be bypassed by a skip link (2.4.1 AA).
- Page title is descriptive and unique (2.4.2 AA).
- Focus order is logical (2.4.3 AA).
- Link purpose is determinable from link text or context (2.4.4 AA).
- Multiple ways to find content exist (search, sitemap, or navigation) (2.4.5 AA).
- Headings and labels are descriptive (2.4.6 AA).
- Focus indicator is visible (2.4.7 AA).

**Input modalities (2.5)**
- Pointer gestures requiring multi-point or path-based gestures have a single-pointer alternative (2.5.1 AA).
- Pointer down-events can be aborted or reversed (2.5.2 AA).
- Visible labels match accessible names on controls (2.5.3 AA).
- Motion-based activation has an alternative and can be disabled (2.5.4 AA).
- Dragging movements have a single-pointer alternative (2.5.7 AA — new in 2.2).
- Target size for pointer inputs is at least 24×24 CSS pixels (2.5.8 AA — new in 2.2).

Quality checks:
- Tab through the entire page without a mouse; verify all controls are reachable and operable.
- Check that focus indicator is visible and has sufficient contrast.
- Verify skip link is the first focusable element and works correctly.

**Fail conditions:**
- Any interactive element unreachable or inoperable by keyboard.
- Visible focus indicator absent on any focusable element.
- Target size below 24×24 CSS pixels without adequate spacing (2.5.8).

---

### 3) Understandable (WCAG Principle 3)

**Readable (3.1)**
- `lang` attribute is set on `<html>` with a valid language code (3.1.1 AA).
- `lang` attribute is set on passages in a different language (3.1.2 AA).

**Predictable (3.2)**
- Focus does not trigger unexpected context changes (3.2.1 AA).
- Changing a form control does not trigger unexpected submission or navigation (3.2.2 AA).
- Navigation repeated across pages is consistent in order (3.2.3 AA).
- Components with the same function are identified consistently (3.2.4 AA).
- Changes of context are initiated only by user request (3.2.6 AA — new in 2.2).

**Input assistance (3.3)**
- Required fields and input errors are identified in text (3.3.1 AA).
- Error suggestions are provided where possible (3.3.2 AA).
- Important legal/financial actions have a review, confirm, or reverse mechanism (3.3.4 AA).
- Accessible authentication does not rely solely on a cognitive function test unless an alternative or help is provided (3.3.7 AA — new in 2.2).
- Redundant entry is not required within a single session unless essential (3.3.8 AA — new in 2.2).

Quality checks:
- Submit a form with errors and verify each error message is descriptive and associated with the field.
- Verify `lang` attribute matches the page's primary language.

**Fail conditions:**
- Any error identified only by color or icon without a text description.
- `lang` attribute missing or set to an invalid code.

---

### 4) Robust (WCAG Principle 4)

**Compatible (4.1)**
- Markup is valid: no duplicate IDs, complete start/end tags, no illegal nesting (4.1.1 AA).
- All UI components have accessible name, role, and state programmatically exposed (4.1.2 AA).
- Status messages are programmatically determinable without receiving focus (4.1.3 AA).

Quality checks:
- Run HTML validation; resolve all errors affecting name, role, or value exposure.
- Inspect all custom widgets for `role`, `aria-label`/`aria-labelledby`, and state attributes.
- Verify dynamic status messages use `aria-live` or equivalent.

**Fail conditions:**
- Duplicate IDs anywhere in the document.
- Any interactive custom widget missing name, role, or state.
- Status messages (success notices, errors) that receive no focus and have no live region.

---

### 5) Findings Report
Produce a prioritized list of failures:
1. **Critical** — Hard WCAG 2.2 AA failures (contrast, keyboard trap, missing labels, missing alt).
2. **Major** — Failures likely to impede specific user groups (focus order, skip links, error handling).
3. **Minor** — Violations that degrade experience but have workarounds.

Each finding should state: criterion reference, element/location, description, and remediation action.

---

### 6) Remediation
- Fix all Critical and Major findings before marking complete.
- Document any Minor findings deferred with a rationale and owner.
- Prefer native HTML over ARIA; add ARIA only where native semantics are insufficient.
- Do not add ARIA that duplicates existing native semantics.

---

### 7) Verification
For each remediated item, re-check the specific criterion and confirm the fix does not introduce a new failure.

Completion criteria — **all must pass; any failure blocks completion**:
- All WCAG 2.2 Level A and AA success criteria pass for the in-scope pages.
- No Critical or Major findings remain open.
- HTML validation passes with no errors affecting accessibility.
- All forms have labels, error handling, and accessible names.
- Keyboard navigation covers all interactive elements with visible focus.
- Color contrast passes for all text and UI components.
- `lang` attribute is present and correct.
- WCAG 2.2-specific criteria (2.5.7, 2.5.8, 3.2.6, 3.3.7, 3.3.8) have been explicitly checked.

## Deliverables
- Prioritized audit findings with criterion references and locations.
- Remediated HTML/CSS with inline comments noting each fix.
- Summary of deferred Minor issues with rationale.
- Verification pass confirming all Critical and Major items resolved.

## Example Prompts
- /wcag22-aa-accessibility Audit this page and produce a prioritized findings report.
- /wcag22-aa-accessibility Remediate all WCAG 2.2 AA failures in this template.
- /wcag22-aa-accessibility Check this form for input assistance, error handling, and label compliance.
- /wcag22-aa-accessibility Verify the new WCAG 2.2 criteria (2.5.7, 2.5.8, 3.2.6, 3.3.7, 3.3.8) across these pages.
