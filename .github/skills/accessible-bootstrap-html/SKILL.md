---
name: accessible-bootstrap-html
description: 'Create accessible Bootstrap HTML from scratch. Use when authoring new pages, templates, or components with Bootstrap 5 that must meet WCAG 2.2 Level AA. Covers semantic structure, ARIA patterns, keyboard operability, colour contrast, and form accessibility for Bootstrap components including navbars, modals, tabs, accordions, cards, and forms.'
argument-hint: 'Page or component purpose, required Bootstrap components, and any known accessibility constraints'
user-invocable: true
---

# Accessible Bootstrap HTML

Author Bootstrap 5 markup that is semantically correct, keyboard-operable, and meets WCAG 2.2 Level AA from the first draft — not as a retrofit.

## When to Use
- Building new pages or templates with Bootstrap 5.
- Creating individual Bootstrap components (navbars, forms, cards, modals, tabs, accordions).
- Converting wireframes or designs into production-ready, accessible HTML.
- Establishing accessible markup patterns for a component library.

This skill is for **creation**. For auditing and remediating existing markup, use `wcag22-aa-accessibility` instead.

## Inputs to Gather
- Page or component purpose and primary user tasks.
- Required Bootstrap components (list them explicitly).
- Responsive breakpoint requirements.
- Any colour palette in use (to evaluate contrast).
- Assistive technology targets if known (screen reader, keyboard-only, voice control).

If inputs are incomplete, ask concise follow-up questions before writing any markup.

---

## Workflow

1. Plan semantic structure and landmarks.
2. Choose elements before choosing classes.
3. Apply Bootstrap layout without breaking semantics.
4. Add Bootstrap components with correct ARIA and keyboard patterns.
5. Apply colour contrast and focus indicator rules.
6. Validate with the quality checklist.

---

## Detailed Procedure

### 1) Plan Semantic Structure

Before writing any markup:
- Define one `<h1>` per page and a logical heading hierarchy (`h2` → `h3`).
- Map landmark regions: `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>`.
- Keep one `<main>` per page.
- List every discrete content block and the semantic element it needs.

Decision points:
- `<section>` only when the block has a heading and thematic grouping.
- `<article>` for independently reusable content (blog post, standalone card).
- `<div>` only when no semantic element fits.

Quality checks:
- [ ] Single `<main>` landmark.
- [ ] No skipped heading levels.
- [ ] All landmark regions are distinguishable (use `aria-label` on duplicate landmarks such as secondary `<nav>`).

---

### 2) Choose Elements Before Classes

Author the content structure before adding any Bootstrap utilities or component classes.

Rules:
- Use `<button>` for actions that operate on the current page.
- Use `<a href>` for navigation to another resource or location.
- Use `<ul>` / `<ol>` for collections of items.
- Use `<figure>` + `<figcaption>` when media and caption are conceptually linked.
- Do **not** use clickable `<div>` or `<span>` as controls.

For forms:
- Every `<input>`, `<select>`, and `<textarea>` must have an explicit `<label for="id">`.
- Hint text goes in a `<div id="hint-id">` referenced via `aria-describedby`.
- Error messages go in a live region or are associated via `aria-describedby`.

Quality checks:
- [ ] No interactive `<div>` or `<span>` elements.
- [ ] All form controls have explicit labels with matching `for`/`id` pairs.
- [ ] Buttons have descriptive text (not just "click here" or an icon with no `aria-label`).

---

### 3) Apply Bootstrap Layout

- Use `container`, `container-fluid`, or breakpoint-specific containers intentionally.
- Build layout with `row` + `col-*`; keep semantic wrappers — do not flatten the DOM for Bootstrap's benefit.
- Use spacing utilities (`mb-3`, `py-4`) to reduce custom CSS.

Decision points:
- Prefer grid (`row`/`col-*`) for page-level and section-level layout.
- Prefer flex utilities (`d-flex`, `align-items-*`) for local alignment within a component.
- Never nest grid rows without a valid reason.

Quality checks:
- [ ] Responsive behavior declared at each required breakpoint.
- [ ] Grid structure readable without visual inspection of classes.

---

### 4) Bootstrap Component ARIA Patterns

Apply ARIA only where Bootstrap 5 documentation requires it. Do **not** add redundant ARIA to elements that already have native semantics.

#### Navbar
```html
<nav aria-label="Primary navigation" class="navbar navbar-expand-lg">
  <button class="navbar-toggler" type="button"
          data-bs-toggle="collapse" data-bs-target="#main-nav"
          aria-controls="main-nav" aria-expanded="false"
          aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="main-nav">
    <ul class="navbar-nav">…</ul>
  </div>
</nav>
```
- Multiple `<nav>` elements on the same page must have distinct `aria-label` values.

#### Modal
```html
<div class="modal" id="exampleModal" tabindex="-1"
     aria-labelledby="exampleModalLabel" aria-modal="true" role="dialog">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h2 class="modal-title fs-5" id="exampleModalLabel">Dialog Title</h2>
        <button type="button" class="btn-close" data-bs-dismiss="modal"
                aria-label="Close"></button>
      </div>
      …
    </div>
  </div>
</div>
```
- Focus must move to the modal on open and return to the trigger on close (Bootstrap handles this when markup is correct).
- Ensure the trigger element (`data-bs-target`) is a `<button>`.

#### Tabs
```html
<ul class="nav nav-tabs" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" id="tab-1" data-bs-toggle="tab"
            data-bs-target="#panel-1" type="button" role="tab"
            aria-controls="panel-1" aria-selected="true">Tab One</button>
  </li>
</ul>
<div class="tab-content">
  <div class="tab-pane active" id="panel-1"
       role="tabpanel" aria-labelledby="tab-1" tabindex="0">…</div>
</div>
```

#### Accordion
```html
<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header">
      <button class="accordion-button" type="button"
              data-bs-toggle="collapse" data-bs-target="#collapseOne"
              aria-expanded="true" aria-controls="collapseOne">
        Section heading
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show"
         data-bs-parent="#accordionExample">
      <div class="accordion-body">…</div>
    </div>
  </div>
</div>
```
- Use a real heading element (`h2`–`h4`) wrapping the button; do not use `aria-level`.

#### Alert / Status Messages
```html
<div class="alert alert-success" role="alert">
  Action completed successfully.
</div>
```
- Use `role="alert"` for important, time-sensitive messages (maps to `aria-live="assertive"`).
- Use `role="status"` for low-priority status updates.

#### Cards as Links
```html
<article class="card">
  <div class="card-body">
    <h3 class="card-title">
      <a href="/page">Card Title</a>
    </h3>
    <p class="card-text">Description text.</p>
  </div>
</article>
```
- Use `<article>` for independently meaningful cards; use `<div>` for layout-only cards.
- Make only the title a link; do not wrap the whole card in `<a>`.

Quality checks:
- [ ] All Bootstrap components follow the ARIA pattern above.
- [ ] No duplicate or conflicting ARIA attributes.
- [ ] Icon-only buttons have `aria-label` or visually-hidden text.

---

### 5) Colour Contrast and Focus Indicators

Contrast requirements (WCAG 2.2 AA):
- Normal text (< 18pt / < 14pt bold): **≥ 4.5:1** against background.
- Large text (≥ 18pt or ≥ 14pt bold): **≥ 3:1**.
- UI components and focus indicators: **≥ 3:1** against adjacent colours.

Bootstrap 5 defaults:
- Default Bootstrap body text passes contrast on white, but verify when using custom colour schemes.
- Bootstrap 5.3+ focus rings use `box-shadow: 0 0 0 0.25rem rgba(...)` — verify contrast against the element's background.
- If using the site colour scheme, load `site-colour-scheme` skill to verify palette values.

Focus indicators:
- Never use `outline: none` or `outline: 0` without a custom replacement that meets ≥ 3:1 contrast.
- Use Bootstrap's `.visually-hidden-focusable` for skip-navigation links.

Skip navigation:
```html
<a href="#main-content" class="visually-hidden-focusable">Skip to main content</a>
…
<main id="main-content">…</main>
```

Quality checks:
- [ ] All text colour/background combinations checked for contrast.
- [ ] Focus indicator visible and ≥ 3:1 against surrounding colours.
- [ ] Skip link present and functional.

---

### 6) Quality Checklist

Run through every item before finalising markup.

**Structure**
- [ ] Single `<h1>`, no skipped heading levels.
- [ ] All landmark regions present and labelled where duplicated.
- [ ] `lang` attribute set on `<html>` (e.g. `lang="en"`).
- [ ] Page `<title>` is descriptive and unique.

**Interactivity**
- [ ] All interactive elements reachable and operable by keyboard alone.
- [ ] No keyboard trap.
- [ ] Focus order follows reading order.
- [ ] Skip navigation link present.

**Forms**
- [ ] Every control has an explicit `<label>`.
- [ ] Required fields marked with `aria-required="true"` or `required`.
- [ ] Error messages associated via `aria-describedby`.

**Images and Media**
- [ ] All non-decorative images have meaningful `alt` text.
- [ ] Decorative images use `alt=""`.
- [ ] No images of text (except logos).

**Bootstrap Components**
- [ ] ARIA patterns followed for navbars, modals, tabs, accordions.
- [ ] Icon-only controls labelled.
- [ ] Dynamic content uses appropriate live region or role.

**Colour and Visual**
- [ ] Text contrast ≥ 4.5:1 (normal) / ≥ 3:1 (large).
- [ ] UI component contrast ≥ 3:1.
- [ ] Focus indicators visible and ≥ 3:1 contrast.
- [ ] Information not conveyed by colour alone.

---

---

## Jekyll Component Integration

When the accessible component is ready, split it into a reusable Jekyll `_includes` file.

### Naming and Location
- Place the file in `_includes/` with a descriptive name that matches the component: `_includes/navbar.html`, `_includes/modal-confirm.html`.
- Use a `components/` subfolder for components that are not page-level includes: `_includes/components/card.html`.

### Parameterise with Liquid
Replace hard-coded content with Liquid variables so the include can be reused across pages:

```liquid
{% comment %} _includes/components/card.html {% endcomment %}
<article class="card">
  <div class="card-body">
    <h3 class="card-title">
      <a href="{{ include.url }}">{{ include.title }}</a>
    </h3>
    <p class="card-text">{{ include.description }}</p>
  </div>
</article>
```

Call it with named parameters:

```liquid
{% include components/card.html
   title="Service Name"
   url="/services/name/"
   description="Short description of the service." %}
```

### ARIA Labels in Includes
When an ARIA label references a dynamic value, pass it as a parameter rather than hard-coding it:

```liquid
<nav aria-label="{{ include.nav_label | default: 'Site navigation' }}" class="navbar navbar-expand-lg">
```

Using `| default:` ensures the component degrades gracefully when the parameter is omitted.

### One Landmark per Include
Each include that wraps a landmark element (`<nav>`, `<header>`, `<footer>`, `<aside>`) should contain **exactly one** landmark. Do not combine `<header>` and `<nav>` in the same include unless they are always used together.

### Skip Link Placement
The skip link must appear as the **first child of `<body>`**, not inside a layout include. Add it directly to the layout file:

```html
<!-- _layouts/default.html -->
<body>
  <a href="#main-content" class="visually-hidden-focusable">Skip to main content</a>
  {% include navbar.html nav_label="Primary navigation" %}
  <main id="main-content">
    {{ content }}
  </main>
  {% include footer.html %}
</body>
```

### Quality checks for Jekyll includes
- [ ] Each include is self-contained and does not rely on variables set outside `include.*`.
- [ ] ARIA label parameters have sensible `| default:` fallbacks.
- [ ] Landmark includes contain exactly one landmark element.
- [ ] Skip link is in the layout, not an include.

---

## Related Skills

- [`bootstrap5-semantic-html`](../bootstrap5-semantic-html/SKILL.md) — deeper guidance on Bootstrap layout composition and semantic markup decisions.
- [`wcag22-aa-accessibility`](../wcag22-aa-accessibility/SKILL.md) — full audit and remediation workflow for existing pages.
- [`site-colour-scheme`](../site-colour-scheme/SKILL.md) — verify palette contrast values for this site.
- [`jekyll-site-architecture`](../jekyll-site-architecture/SKILL.md) — broader guidance on Jekyll collections, layouts, and data-driven pages.
