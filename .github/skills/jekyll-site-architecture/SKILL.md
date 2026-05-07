---
name: jekyll-site-architecture
description: 'Design and implement well-structured Jekyll websites. Use when planning content architecture, collections, layouts/includes, data-driven pages, navigation, SEO metadata, and build validation for maintainable static sites.'
argument-hint: 'Site goal, target pages, and constraints'
user-invocable: true
---

# Jekyll Site Architecture

Create or improve a Jekyll website so it is easy to maintain, easy to extend, and consistent for content authors.

## When to Use
- Starting a new Jekyll site from scratch.
- Refactoring a legacy Jekyll site with duplicated templates.
- Adding new sections (blog, services, case studies, docs) that need predictable structure.
- Standardizing front matter, URLs, navigation, and SEO behavior.

## Inputs to Gather
- Primary site goal and audience.
- Content types needed (posts, pages, custom collections).
- Navigation expectations (top-level pages, footer links, taxonomy pages).
- Localization requirements (single-language or multilingual).
- Required integrations (forms, analytics, newsletter, search, feeds).

If inputs are incomplete, ask concise follow-up questions before implementation.

## Workflow
1. Define the information architecture.
2. Design the content model and front matter contracts.
3. Establish layout/include/component boundaries.
4. Configure global behavior in `_config.yml`.
5. Implement data-driven rendering where repetition exists.
6. Validate URLs, metadata, accessibility, and build output.
7. Document conventions for future contributors.

## Detailed Procedure

### 1) Information Architecture
- List top-level sections and map each to a page or collection.
- Keep URL patterns short, descriptive, and stable.
- Reserve special pages for taxonomy, legal content, and utility routes (`404`, feeds, sitemap).

Decision points:
- Use `_posts` when entries are chronological and date-driven.
- Use `collections` when entries are domain objects (projects, resources, lessons).
- Use `_data` when content is tabular/shared and rendered across many pages.

### 2) Content Model
- Define required front matter keys per content type (title, description, permalink, tags, date, status).
- Normalize naming conventions for categories/tags/slugs.
- Provide defaults in `_config.yml` where possible to reduce per-file repetition.

Quality checks:
- Every page has meaningful `title` and summary metadata.
- No conflicting permalink patterns.
- Draft vs published states are explicit.

### 3) Layout and Include Strategy
- Keep `_layouts` focused on page-level skeletons.
- Move reusable UI fragments into `_includes`.
- Prefer composition over copy-paste: shared blocks should become includes.

Decision points:
- If markup repeats in 2+ places, convert it into an include.
- If a page type differs mainly by data source, keep one layout and vary input data.

Quality checks:
- Layout names reflect intent (`post`, `resource`, `tool`, etc.).
- Includes accept clear parameters and avoid hidden dependencies.

### 4) Configuration and Defaults
- Set canonical URL, plugins, markdown/highlighter options, and collection output rules in `_config.yml`.
- Define `defaults` for common front matter by path or type.
- Configure exclusions to keep build output clean.

Quality checks:
- No environment-specific values hardcoded without overrides.
- Collections that should render publicly have `output: true`.
- Build works without manual edits after clean checkout.

### 5) Data-Driven Pages
- Move repeated lists (services, platforms, links, FAQs) into `_data/*`.
- Render with Liquid loops and includes.
- Keep data schemas stable and documented.

Decision points:
- Prefer YAML for human-edited nested structures.
- Prefer CSV only when tabular imports are the source of truth.

Quality checks:
- Empty or missing data does not break page rendering.
- Sorting and filtering logic is deterministic.

### 6) Cross-Cutting Quality Pass
- Run local build and inspect generated pages for broken links and missing assets.
- Verify semantic heading hierarchy and alt text.
- Ensure metadata coverage (Open Graph, canonical, language attributes, feed/sitemap consistency).
- Confirm mobile readability and navigation behavior.

Completion criteria:
- Build succeeds without errors.
- Navigation matches the planned architecture.
- Required content types have templates and index/list pages.
- Repeated structures are componentized or data-driven.
- Editorial conventions are documented.

### 7) Maintenance Documentation
- Add a short contributor section in project docs describing:
  - folder purpose (`_layouts`, `_includes`, `_data`, collections)
  - front matter contract per content type
  - how to add a new section/page type
  - how to run and verify local builds

## Deliverables
- A clear architecture map (sections, routes, templates, data sources).
- Updated Jekyll structure with reusable layouts/includes.
- Standardized front matter conventions.
- Verified build and quality checklist results.
- Contributor-oriented maintenance notes.

## Example Prompts
- `/jekyll-site-architecture Refactor this repository into a clearer content architecture with fewer duplicated templates.`
- `/jekyll-site-architecture Add a new lessons collection with index pages, tags, and consistent SEO metadata.`
- `/jekyll-site-architecture Standardize front matter and permalinks across pages and collections.`
