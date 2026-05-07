---
name: bootstrap5-semantic-html
description: 'Create well-structured semantic HTML using Bootstrap 5 markup. Use for accessible page architecture, correct landmark usage, responsive layout composition, and standards-based Bootstrap components without div soup.'
argument-hint: 'Page purpose, required sections, and UI constraints'
user-invocable: true
---

# Bootstrap 5 Semantic HTML

Design and implement pages that are semantically correct first, then styled with Bootstrap 5 classes and components.

## When to Use
- Building new pages with Bootstrap 5.
- Refactoring legacy markup with excessive non-semantic wrappers.
- Converting wireframes into production-ready HTML.
- Standardizing frontend markup quality across a team.

## Inputs to Gather
- Page purpose and primary user tasks.
- Required content regions (hero, navigation, main content, sidebar, footer).
- Component requirements (forms, cards, tables, alerts, modals, tabs, accordions).
- Accessibility and compliance constraints.
- Responsive expectations and breakpoint behavior.

If inputs are incomplete, ask concise follow-up questions before implementation.

## Workflow
1. Map page information architecture and landmarks.
2. Choose semantic elements for each content block.
3. Apply Bootstrap 5 layout system without breaking semantics.
4. Add Bootstrap components with accessible attribute patterns.
5. Validate document outline, keyboard flow, and responsive behavior.
6. Run quality checks and finalize maintainable markup.

## Detailed Procedure

### 1) Landmark and Structure Planning
- Define one primary page heading and a logical heading hierarchy.
- Map landmarks using semantic elements: `header`, `nav`, `main`, `aside`, `footer`, `section`, `article`.
- Keep one `main` element per page unless route-level constraints require otherwise.

Decision points:
- Use `section` only when the content block has a heading and thematic grouping.
- Use `article` for independently reusable content (posts, cards that stand alone, feed items).
- Use `div` only when no semantic element fits.

Quality checks:
- Landmark roles are clear and non-duplicative.
- Heading levels are sequential and meaningful.

### 2) Semantic Markup First
- Author content structure before utility or spacing classes.
- Use proper element types for meaning: lists for collections, buttons for actions, anchors for navigation.
- Associate labels and helper text correctly for forms.

Decision points:
- If an element triggers behavior on the current page, use `button`.
- If an element navigates to another resource or location, use `a`.
- Use `figure` and `figcaption` when media and caption are conceptually linked.

Quality checks:
- No clickable non-interactive elements used as controls.
- Form controls have explicit labels and valid IDs.

### 3) Bootstrap 5 Layout Composition
- Use containers intentionally: `container`, `container-fluid`, or breakpoint-specific containers.
- Build layout with `row` and `col-*` classes while preserving semantic wrappers.
- Use spacing and display utilities to reduce custom CSS when appropriate.

Decision points:
- Prefer semantic wrapper element plus Bootstrap classes over anonymous nested wrappers.
- Use grid for page-level and section-level layout; use flex utilities for local alignment only.

Quality checks:
- Grid structure remains readable and does not flatten semantics.
- Responsive behavior is explicit at required breakpoints.

### 4) Accessible Bootstrap Components
- Follow Bootstrap 5 component structure for navbars, dropdowns, collapse, tabs, and modals.
- Keep ARIA usage minimal and accurate; do not add redundant ARIA where native semantics already apply.
- Ensure component controls expose visible text and accessible names.

Decision points:
- **Default: avoid Bootstrap JavaScript components.** Use plain HTML patterns unless interactive behavior is explicitly required by the user.
- When Bootstrap JS is required (modal, collapse, dropdown, tabs), use the minimal necessary attributes and verify keyboard operability.
- Prefer progressive enhancement: the page must remain usable without JavaScript.

Quality checks:
- Interactive components are keyboard reachable and operable.
- State and expanded/collapsed indicators are reflected correctly.

### 5) Content and Metadata Integrity
- Set document language and meaningful page title.
- Ensure link text is descriptive and context-aware.
- Add image alt text based on intent (informative, decorative, functional).

Quality checks:
- No placeholder or generic labels remain.
- Tab order follows visual and logical reading flow.

### 6) Completion Review
- Validate HTML for structural correctness.
- Check headings, landmarks, and list/table semantics.
- Verify Bootstrap classes are purposeful and avoid class bloat.
- Confirm page remains understandable if CSS fails to load.

Completion criteria — **all must pass; any failure blocks completion**:
- Semantic structure accurately reflects content meaning.
- Bootstrap 5 markup is valid and minimal for the intended UI.
- Heading levels are strictly sequential with no skipped levels.
- All form controls have explicit `<label>` elements with matching IDs.
- Landmark regions are correct and non-duplicative.
- Accessibility baseline passes manual keyboard and landmark checks.
- Responsive layout works at agreed breakpoints.
- Markup is readable and maintainable for future edits.

**Fail conditions** (do not mark complete if any are present):
- Any heading level is skipped (e.g. `h2` directly followed by `h4`).
- Any form input or textarea lacks an associated visible label.
- Any landmark element is missing or misused (e.g. `main` absent, `nav` used for non-navigation groups).
- Any clickable element uses a non-interactive element type (e.g. `div` or `span` with a click handler).

## Common Anti-Patterns to Remove
- Div-only structure with no landmarks.
- Heading levels skipped for visual size only.
- Anchors styled as buttons for non-navigation actions.
- Duplicate IDs in form and component markup.
- Excessive wrapper nesting only for spacing.

## Deliverables
- Semantically structured HTML page or template.
- Bootstrap 5 class composition aligned with semantic elements.
- Accessibility and responsiveness validation notes.
- Clean, maintainable markup ready for iteration.

## Example Prompts
- /bootstrap5-semantic-html Build a marketing landing page skeleton with semantic landmarks and Bootstrap 5 grid.
- /bootstrap5-semantic-html Refactor this existing template to remove div soup and improve semantic accessibility.
- /bootstrap5-semantic-html Create a dashboard layout with accessible nav, cards, forms, and responsive sections.
