---
description: "Use when creating or editing HTML, Markdown, Sass, or Jekyll files in this site. Enforces use of the project's established skills for Bootstrap markup, accessibility, Jekyll architecture, and colour scheme."
applyTo: "**/*.{html,md,sass,scss,yml,yaml}"
---

# Site Skill Conventions

This Jekyll site has established skills that must be followed for all authoring work. Load and apply the relevant skill before writing or modifying any markup, styles, or site structure.

## Which Skill to Use

| Task | Skill to load |
|------|---------------|
| Authoring new HTML pages or Bootstrap components that must be accessible | `accessible-bootstrap-html` |
| Refactoring or reviewing Bootstrap markup for semantic correctness | `bootstrap5-semantic-html` |
| Auditing or remediating existing pages for WCAG 2.2 AA compliance | `wcag22-aa-accessibility` |
| Planning or changing Jekyll collections, layouts, includes, navigation, or SEO | `jekyll-site-architecture` |
| Adding new pages, components, or templates that must match the site palette | `site-colour-scheme` |

## Hard Rules

- **Never create a Bootstrap component without following `accessible-bootstrap-html`**. Semantic markup and ARIA patterns must be correct from the first draft.
- **Never add custom colours or override Bootstrap colour variables** without first loading `site-colour-scheme` to verify contrast.
- **Never create a new Jekyll layout, include, collection, or data file** without following `jekyll-site-architecture`.
- **Always use `_includes/` for reusable markup**. Do not duplicate component HTML across layout files.
- **Never use `outline: none` or `outline: 0`** without a custom focus replacement that meets WCAG 2.2 AA 3:1 contrast.

## Precedence

When a task spans multiple skills (e.g. adding an accessible component to a new Jekyll page), load all relevant skills and apply them in this order:

1. `jekyll-site-architecture` — file location, front matter, and layout selection.
2. `accessible-bootstrap-html` — markup authoring and component ARIA patterns.
3. `site-colour-scheme` — palette and contrast verification.
