# Bootstrap 5 Migration Implementation Plan

**Project:** Migrate consulting.berthelemy.net from Pico CSS to Bootstrap 5  
**Document Version:** 2.0  
**Date:** May 8, 2026  

---

## 1. Project Overview

### 1.1 Current State
- **Framework:** Pico CSS (minimal, classless CSS framework)
- **Static Site Generator:** Jekyll 3.10.0 with GitHub Pages
- **Layout:** `_layouts/simple_default.html` (primary template)
- **CSS Architecture:** Pico CSS CDN + `/assets/css/simple_overrides.css`
- **HTML Structure:** Already semantic (`<header>`, `<nav>`, `<main>`, `<footer>`)
- **Includes:** 14 component partials (most deprecated Hyperspace-era)
- **Collections:** 6 Jekyll collections (unchanged)

### 1.2 Target State
- **Framework:** Bootstrap 5 (component-rich utility framework)
- **CSS Architecture:** Bootstrap 5 utilities + minimal custom CSS
- **HTML Structure:** Leverage existing semantic foundation
- **Component Library:** Use Bootstrap's built-in components (navbar, cards, grid, forms, etc.)
- **Color Scheme:** Maintain current branding with Bootstrap CSS custom properties
- **Accessibility:** WCAG 2.2 Level AA compliance

### 1.3 Key Advantages of Current State
- ✅ Already semantic HTML (no div soup to clean up)
- ✅ Minimal custom CSS (easier migration)
- ✅ Clean, readable template structure
- ✅ Good foundation for Bootstrap adoption
- ✅ Reduced refactoring scope compared to legacy frameworks

### 1.4 Migration Objectives
1. Replace Pico CSS with Bootstrap 5
2. Enhance grid and layout capabilities (Pico has limited grid)
3. Add component library (cards, alerts, modals, badges, etc.)
4. Maintain semantic HTML integrity
5. Reduce custom CSS footprint
6. Improve component reusability
7. Ensure WCAG 2.2 AA compliance
8. Improve responsive behavior and mobile UX

---

## 2. Scope & Inventory

### 2.1 Core Files to Refactor

#### Primary Layout (Foundation)
- **`_layouts/simple_default.html`** — Main template for all pages (CRITICAL)

#### Specialized Layouts (Inherit from simple_default.html)
- `_layouts/expertise.html` — Individual expertise page (breadcrumb, CTA, related expertise/articles)
- `_layouts/lesson.html` — Individual lesson page (aside sidebar, related lessons by category/level, prev/next nav)
- `_layouts/post.html` — Blog post/article page (breadcrumb, figure/figcaption, metadata, related posts)
- `_layouts/tool.html` — Toolkit item page (breadcrumb, grid layout, related tools)
- `_layouts/resource.html` — Resource page (breadcrumb, Brevo form, contact CTA)
- `_layouts/tag.html` — Article tag archive (breadcrumb, article grid, categories list)
- `_layouts/standard.html` — Standards/compliance page (breadcrumb, sidebar, strengths/limitations grid)

#### Includes (Active)
- `_includes/simple_head.html` — Replace Pico CSS CDN with Bootstrap
- `_includes/simple_nav.html` — Update navbar to Bootstrap Navbar
- `_includes/simple_footer.html` — Refactor footer with Bootstrap utilities
- `_includes/menu-list.html` — Update menu structure for Bootstrap Nav
- `_includes/brevo-form.html` — Apply Bootstrap form styles
- `_includes/scripts.html` — Add Bootstrap JS bundle

#### Includes (Secondary/Conditional)
- `_includes/cta.html` — Refactor CTA with Bootstrap buttons/layout
- `_includes/ribbon.html` — Pico-specific, update to Bootstrap
- `_includes/youtube.html` — Add responsive wrapper for embeds
- `_includes/curriculum.html` — Update layout
- `_includes/expertise-list.html` — Convert to Bootstrap list/cards
- `_includes/services.html` — Convert to Bootstrap grid/cards
- `_includes/websites.html` — Convert to Bootstrap cards

#### CSS Files
- `assets/css/simple_overrides.css` — Replace/consolidate with Bootstrap customization
- `assets/css/noscript.css` — Update for Bootstrap

#### Legacy Layouts (Deprecated - Hyperspace)
- `_layouts/default.html` — Old Hyperspace layout (archive or remove - low priority)

### 2.2 No Changes Required
- `_config.yml` — No changes needed
- `_data/*.yaml` — Data files unchanged
- `collections/` — Content collections unchanged
- `_pages/` — Content unchanged (markup only in conditionals)

### 2.3 Bootstrap Components to Implement
- **Grid:** `.container`, `.row`, `.col-*` (replace custom grid)
- **Navbar:** Bootstrap Navbar with responsive collapse
- **Forms:** `.form-label`, `.form-control`, Bootstrap form styling
- **Buttons:** `.btn`, `.btn-primary`, `.btn-outline-*`
- **Cards:** `.card`, `.card-body` for content blocks
- **Utilities:** Spacing (`.m-*`, `.p-*`), text (`.text-center`), colors (`.text-primary`)
- **Typography:** Bootstrap heading and text utilities
- **Flexbox:** `.d-flex`, `.justify-content-*`, `.align-items-*`

---

## 3. Implementation Plan

### Phase 1: Bootstrap Setup & Head Configuration (1-2 days)
**Goal:** Establish Bootstrap infrastructure and validate CDN approach

#### 1.1 Update `simple_head.html`
- [ ] Replace Pico CSS CDN with Bootstrap 5 CSS
  ```html
  <!-- OLD: -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@picocss/pico@2/css/pico.cyan.min.css" />
  
  <!-- NEW: -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  ```
- [ ] Keep all existing meta tags (OpenGraph, Twitter, etc.)
- [ ] Keep datatable and featherlight CDN links
- [ ] Update noscript fallback CSS

#### 1.2 Update `scripts.html`
- [ ] Add Bootstrap 5 JS bundle (required for navbar collapse, modals, etc.)
  ```html
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
  ```
- [ ] Keep existing datatable and other JS libraries

#### 1.3 Create Brand Customization CSS
- [ ] Create `assets/css/bootstrap-custom.css`:
  - CSS custom properties for brand colors
  - Font family overrides
  - Spacing adjustments
  - Dark mode support (if needed)
- [ ] Document all custom variables

#### 1.4 Validation
- [ ] Test build locally: `bundle exec jekyll serve`
- [ ] Verify Bootstrap CSS loads correctly
- [ ] Check for conflicts with existing scripts
- [ ] Visual spot-check on homepage

**Deliverables:**
- Updated `simple_head.html` with Bootstrap CSS
- Updated `scripts.html` with Bootstrap JS
- `assets/css/bootstrap-custom.css` created
- Local build verification complete

---

### Phase 2: Core Template Refactoring (4-5 days)
**Goal:** Update main layout and navigation with Bootstrap patterns

#### 2.1 Refactor `simple_default.html`
- [ ] Review current structure (already semantic, good foundation)
- [ ] Update layout containers:
  - Ensure `.container` class used correctly
  - Apply Bootstrap grid where needed (rarely needed for this layout)
  - Verify responsive behavior at all breakpoints
- [ ] Test header section rendering
- [ ] Test main content area
- [ ] Test footer rendering
- [ ] Responsive testing: 320px, 768px, 1024px, 1440px+

#### 2.2 Refactor Navigation & Footer
- [ ] `simple_nav.html`:
  - Use `.navbar`, `.navbar-expand-lg`, `.navbar-light/.navbar-dark`
  - Implement responsive collapse with `.navbar-toggler`
  - Update logo positioning
  - Implement active link styling
- [ ] `simple_footer.html`:
  - Update footer styling with Bootstrap utilities
  - Use `.container` and grid if multi-column
- [ ] `menu-list.html`:
  - Convert to Bootstrap `.nav` and `.nav-link` classes
  - Update active state styling
  - Test with navbar collapse

#### 2.3 Refactor Specialized Layouts (Inherit from simple_default.html)
- [ ] `expertise.html` — Add Bootstrap styling to breadcrumb, CTA section, related items list
- [ ] `lesson.html` — Convert aside sidebar to Bootstrap sidebar/offcanvas, style related lessons list
- [ ] `post.html` — Update breadcrumb, figure/figcaption styling, metadata display, related articles
- [ ] `tool.html` — Convert grid layout to Bootstrap grid, style summary section, related tools list
- [ ] `resource.html` — Update breadcrumb, Brevo form styling (will be refined in Phase 3)
- [ ] `tag.html` — Convert article grid and categories grid to Bootstrap grid/cards
- [ ] `standard.html` — Convert aside sidebar to Bootstrap, refactor strengths/limitations grid

**Deliverables:**
- Refactored `simple_default.html` (foundation)
- Refactored navigation and footer includes
- Refactored `menu-list.html`
- Refactored all 7 specialized layouts
- Testing results: responsive, keyboard accessible

---

### Phase 3: Component Refactoring (2-3 days)
**Goal:** Update reusable includes to use Bootstrap components

#### 3.1 Forms & CTAs
- [ ] Refactor `brevo-form.html`:
  - Apply Bootstrap `.form-label`, `.form-control` classes
  - Use `.btn` for submit buttons
  - Ensure form spacing with Bootstrap utilities
- [ ] Refactor `cta.html`:
  - Use `.btn` and button utilities (`.btn-primary`, `.btn-outline-*`)
  - Apply Bootstrap flexbox for layout

#### 3.2 Content Components
- [ ] Refactor `services.html`:
  - Convert to Bootstrap `.row` and `.col-md-*` grid
  - Use Bootstrap `.card` for service items
  - Responsive column sizing
- [ ] Refactor `expertise-list.html`:
  - Bootstrap list or card layout
  - Apply `.badge` for tags/labels if needed
- [ ] Refactor `curriculum.html`:
  - Bootstrap grid for layout
  - Utility classes for spacing
- [ ] Refactor `websites.html`:
  - Bootstrap `.card` components
  - Grid layout with responsive columns

#### 3.3 Special Components
- [ ] Refactor `ribbon.html`:
  - Use Bootstrap `.alert` or custom banner with utilities
- [ ] Review `youtube.html`:
  - Add Bootstrap-compatible responsive wrapper if needed
- [ ] Verify `zoho-form.html` (if active):
  - Apply Bootstrap form styles if in use

**Deliverables:**
- All reusable includes refactored to Bootstrap
- Component testing complete
- Visual consistency verified

---

### Phase 4: CSS Consolidation & Optimization (2-3 days)
**Goal:** Clean up and optimize CSS footprint

#### 4.1 CSS Analysis & Cleanup
- [ ] Analyze `assets/css/simple_overrides.css`:
  - Identify Pico-specific overrides that are no longer needed
  - Extract brand-specific styles (colors, fonts, spacing)
  - Move to `bootstrap-custom.css`
  - Remove conflicts with Bootstrap
- [ ] Update `assets/css/noscript.css`:
  - Ensure critical styles work without CSS
  - Bootstrap-compatible fallbacks

#### 4.2 CSS Organization
- [ ] Final CSS file structure:
  ```
  assets/css/
  ├── bootstrap-custom.css    (Brand colors, fonts, custom variables)
  ├── simple_overrides.css    (Minimal component-specific overrides, if any)
  └── noscript.css            (No-JS fallback)
  ```
- [ ] Consolidate duplicate styles
- [ ] Remove Pico-specific hacks
- [ ] Minimize custom CSS size

#### 4.3 Performance Testing
- [ ] Measure CSS file sizes (before → after)
- [ ] Test CSS load time
- [ ] Verify no layout shifts (CLS)
- [ ] Lighthouse performance score

**Deliverables:**
- Optimized CSS structure
- Performance metrics (file sizes, load time)
- CSS documentation for future maintainers

---

### Phase 5: Testing & Validation (3-4 days)
**Goal:** Comprehensive QA across all devices, browsers, and accessibility

#### 5.1 Cross-Browser Testing
- [ ] Chrome/Edge (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Mobile Chrome, Safari (iOS)
- [ ] Test result matrix documented

#### 5.2 Responsive Testing
- [ ] Mobile: 320px, 375px, 425px
- [ ] Tablet: 768px
- [ ] Desktop: 1024px, 1440px, 1920px
- [ ] All navigation, forms, content readable at each size
- [ ] Test result matrix documented

#### 5.3 Functional Testing
- [ ] All links working
- [ ] Navigation menu toggle working (mobile)
- [ ] Forms submitting correctly
- [ ] Images loading and displaying
- [ ] Videos/embeds rendering
- [ ] Search functionality (if applicable)

#### 5.4 Accessibility Audit
- [ ] Semantic HTML validation:
  - Proper heading hierarchy (no skipped levels)
  - Correct landmark regions
  - Image alt text completeness
  - Form label associations
- [ ] Keyboard navigation:
  - Tab order logical
  - Focus indicators visible
  - Modal/dropdown keyboard operation
- [ ] Screen reader testing:
  - Page outline makes sense
  - Links descriptive
  - Form labels associated
- [ ] Color contrast (WCAG AA: 4.5:1 for text, 3:1 for UI)
- [ ] WCAG 2.2 AA compliance verification

#### 5.5 Visual Regression Testing
- [ ] Before/after screenshot comparison
- [ ] Brand consistency
- [ ] Typography and spacing
- [ ] Color application
- [ ] Button/link styling

**Deliverables:**
- Browser compatibility matrix (passed)
- Responsive testing report (passed)
- Functional testing checklist (passed)
- Accessibility audit report (WCAG 2.2 AA compliant)
- Visual regression report (approved)

---

### Phase 6: Documentation & Cleanup (1-2 days)
**Goal:** Document changes and prepare for deployment

#### 6.1 Migration Documentation
- [ ] Bootstrap 5 migration guide:
  - Components used in templates
  - Bootstrap version and CDN info
  - CSS customization approach
- [ ] Template documentation:
  - How to use `simple_default.html`
  - Available front-matter variables
  - Component usage examples
- [ ] Deprecation notes:
  - Old Hyperspace layouts (`default.html`, etc.)
  - Recommendation: archive or remove

#### 6.2 Maintenance Guide
- [ ] How to add new pages using Bootstrap
- [ ] Common Bootstrap patterns reference
- [ ] How to customize brand colors/fonts
- [ ] Troubleshooting common issues

#### 6.3 Code Cleanup
- [ ] Remove deprecated Hyperspace layouts (or archive)
- [ ] Remove unused includes
- [ ] Clean up commented-out code
- [ ] Verify Git history is clean

**Deliverables:**
- Bootstrap 5 migration guide
- Template usage documentation
- Maintenance runbook
- Clean Git history

---

### Phase 7: Deployment & Post-Launch (1 day)
**Goal:** Deploy to production and monitor

#### 7.1 Pre-Deployment Checklist
- [ ] All testing passed and documented
- [ ] No broken links
- [ ] SEO metadata intact
- [ ] Forms working
- [ ] Backup created
- [ ] Rollback plan documented

#### 7.2 Deployment
- [ ] Deploy to GitHub Pages / staging
- [ ] Verify build succeeds: `bundle exec jekyll build`
- [ ] Smoke test critical pages:
  - Homepage
  - Services page
  - Contact form
  - Navigation on mobile
- [ ] Monitor error logs

#### 7.3 Post-Launch Monitoring (1 week)
- [ ] Monitor analytics for traffic changes
- [ ] Check error logs
- [ ] Collect user feedback
- [ ] Monitor performance metrics
- [ ] Quick-fix any urgent issues

**Deliverables:**
- Deployment verification report
- Post-launch monitoring summary

---

## 4. Technical Details

### 4.1 Bootstrap CDN URLs
```html
<!-- CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">

<!-- JS (includes Popper.js) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
```

### 4.2 Bootstrap 5 Utility Classes (Quick Reference)
| Category | Common Classes |
|----------|-----------------|
| **Grid** | `.container`, `.row`, `.col-*`, `.col-md-*`, `.col-lg-*` |
| **Spacing** | `.m-3`, `.p-2`, `.mt-4`, `.mb-3`, `.ms-auto`, `.me-auto` |
| **Display** | `.d-flex`, `.d-grid`, `.d-none`, `.d-block`, `.d-inline` |
| **Flexbox** | `.justify-content-center`, `.align-items-center`, `.flex-column` |
| **Text** | `.text-center`, `.text-start`, `.text-end`, `.fw-bold`, `.fs-5` |
| **Colors** | `.text-primary`, `.bg-light`, `.border-primary` |
| **Sizing** | `.w-100`, `.h-100`, `.min-vh-100` |

### 4.3 Bootstrap Breakpoints
- **xs:** < 576px
- **sm:** ≥ 576px
- **md:** ≥ 768px
- **lg:** ≥ 992px
- **xl:** ≥ 1200px
- **xxl:** ≥ 1400px

### 4.4 CSS Custom Properties Strategy
```css
/* assets/css/bootstrap-custom.css */
:root {
  /* Brand Colors (override Bootstrap defaults if needed) */
  --bs-primary: #your-brand-color;
  --bs-secondary: #your-secondary-color;
  
  /* Typography */
  --bs-body-font-family: 'Your Font', sans-serif;
  
  /* Spacing */
  --bs-spacer: 1rem;
}

/* Dark mode (optional) */
@media (prefers-color-scheme: dark) {
  :root {
    --bs-body-bg: #dark-bg;
    --bs-body-color: #dark-text;
  }
}
```

---

## 5. Timeline & Effort Estimate

| Phase | Tasks | Duration | Notes |
|-------|-------|----------|-------|
| 1 | Bootstrap setup & config | 1-2 days | Fast, mostly copy/paste |
| 2 | Core template + 7 specialized layouts + nav/footer | 4-5 days | Increased from 3-4 days to account for 7 layout variants |
| 3 | Component refactoring (includes) | 2-3 days | Lighter scope now, focused on includes only |
| 4 | CSS consolidation | 2-3 days | Light cleanup expected |
| 5 | Testing & QA | 3-4 days | Thorough cross-browser testing |
| 6 | Documentation | 1-2 days | Update guides, deprecate old files |
| 7 | Deployment | 1 day | Smooth deployment expected |
| **Total** | | **15-24 days** | **2-3 weeks (12-16 hrs/week)** |

**Timeline Advantages:**
- ✅ Shorter than Hyperspace migration (already semantic HTML)
- ✅ Pico CSS is minimal, so less to replace
- ✅ Existing template structure is clean
- ✅ No major refactoring needed, mostly swapping utilities
- ✅ 7 specialized layouts are relatively lightweight (mostly content + minor styling)

---

## 6. Risk Assessment

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|-----------|
| Breaking existing page layout | High | Low | Use Bootstrap's tested system; continuous testing |
| SEO/ranking loss | High | Low | Maintain existing URLs, meta tags, structure |
| Lost functionality | Medium | Low | Comprehensive testing before deployment |
| Performance degradation | Medium | Low | Monitor metrics; Bootstrap is lightweight |
| Accessibility regression | Medium | Low | WCAG 2.2 AA audit; keyboard testing |
| Browser compatibility issues | Medium | Low | Cross-browser testing matrix |
| Form submission issues | Medium | Low | Functional testing of all forms |

---

## 7. Success Criteria

### Functional (Must-Have)
- ✅ All pages render correctly at all breakpoints (320px, 768px, 1024px, 1440px+)
- ✅ All links, navigation, and forms functional
- ✅ 100% content parity with current site
- ✅ Homepage, key pages, and mobile menu tested and working

### Code Quality (Must-Have)
- ✅ Semantic HTML structure maintained/improved
- ✅ Bootstrap classes used correctly (no misuse)
- ✅ Custom CSS reduced by 60%+ from Pico overrides
- ✅ No deprecated or conflicting CSS

### Accessibility (Must-Have)
- ✅ WCAG 2.2 Level AA compliance verified
- ✅ Keyboard navigation fully functional
- ✅ Screen reader compatible
- ✅ Color contrast meets standards

### Performance (Nice-to-Have)
- ✅ Page load time maintained or improved
- ✅ No cumulative layout shift issues
- ✅ Lighthouse scores: Performance ≥ 80, Accessibility ≥ 95

---

## 8. Resources & Team

### Skillsets Needed
- **Frontend Developer:** Bootstrap, HTML, CSS expertise (primary)
- **QA/Tester:** Cross-browser, responsive, accessibility testing
- **DevOps:** GitHub Pages deployment verification (minimal)

### Tools Required
- Local Jekyll environment
- Modern browsers (Chrome, Firefox, Safari)
- Accessibility tools: Axe, WAVE, NVDA/VoiceOver
- Git for version control
- Text editor (VS Code, etc.)

### Assumptions
- Bootstrap 5 CDN remains stable and available
- Existing Jekyll environment remains stable
- GitHub Pages deployment unchanged
- IE11 support not required (can drop with Bootstrap 5)

---

## 9. Next Steps

### Before Starting
1. [ ] Review and approve this plan
2. [ ] Confirm Bootstrap 5 CDN approach (vs. npm/SASS)
3. [ ] Assign team member(s) to project
4. [ ] Create Git branch for refactoring: `feature/bootstrap5-migration`
5. [ ] Set up tracking (GitHub Issues, project board)

### Phase 1 Immediate Actions
1. [ ] Fork/branch the repo
2. [ ] Update `_includes/simple_head.html` with Bootstrap CSS CDN
3. [ ] Update `_includes/scripts.html` with Bootstrap JS
4. [ ] Create `assets/css/bootstrap-custom.css`
5. [ ] Test local build: `bundle exec jekyll serve`
6. [ ] Document any issues or blockers

### Communication Plan
- Kickoff meeting to review plan
- Daily standups during active phases (optional)
- Testing sign-off before Phase 5
- Pre-deployment review before Phase 7

---

## 10. Reference & Resources

### Bootstrap 5 Documentation
- **Main Docs:** https://getbootstrap.com/docs/5.3/
- **Grid System:** https://getbootstrap.com/docs/5.3/layout/grid/
- **Components:** https://getbootstrap.com/docs/5.3/components/
- **Utilities:** https://getbootstrap.com/docs/5.3/utilities/

### Accessibility
- **WCAG 2.2 Guidelines:** https://www.w3.org/WAI/WCAG22/quickref/
- **Bootstrap Accessibility:** https://getbootstrap.com/docs/5.3/getting-started/accessibility/

### Jekyll & Static Sites
- **Jekyll Docs:** https://jekyllrb.com/docs/
- **GitHub Pages:** https://pages.github.com/

---

## Appendix A: Pico CSS → Bootstrap 5 Cheat Sheet

| Pico CSS | Bootstrap 5 | Notes |
|----------|------------|-------|
| Classless styling | `.btn`, `.form-control`, `.card` | Bootstrap requires explicit classes |
| `<button>` default style | `.btn .btn-primary` | Add classes for styling |
| `<input>` default style | `.form-control` | Add class for Bootstrap styling |
| Custom grid (limited) | `.container`, `.row`, `.col-*` | Bootstrap has more powerful grid |
| Color theme (CSS var) | `--bs-primary`, etc. | Override Bootstrap color vars |
| Responsive typography | Same concept, Bootstrap utilities | Use `.fs-*` for font sizes |

---

**Document Status:** READY FOR REVIEW  
**Last Updated:** May 8, 2026  
**Prepared by:** Copilot

**Approvals Required:**
- [ ] Project Lead / Product Owner
- [ ] Technical Lead
- [ ] (Optional) QA Lead

