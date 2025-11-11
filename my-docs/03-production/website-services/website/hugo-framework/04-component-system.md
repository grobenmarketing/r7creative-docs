---
title: "Component Design System"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/04-component-system
phase: development
audience: both
duration: reference
type: reference
effort: low
human_interaction: none
sequence_order: null
parallelizable: true
ai_role: reference
requires:
  - component-gallery
  - design-tokens
deliverables:
  - css-architecture
  - component-specs
  - bem-naming
tags:
  - design-system
  - css
  - bem
  - components
  - styling
  - accessibility
---

# Component Design System

Visual components, CSS architecture, and styling conventions for consistent implementation.

---

## Design System Philosophy

**Components are predictable building blocks.**

Every component has:
- A clear **purpose**
- A consistent **naming pattern**
- Expected **variants**
- Accessibility **requirements**

This allows any AI or developer to create or extend components that fit the system.

---

## CSS Architecture

### Approach: Semantic BEM with Utility Support

We use a **hybrid approach**:
- **BEM (Block Element Modifier)** for component structure
- **Semantic class names** for meaning
- **Utility classes** for spacing/layout adjustments

**Why BEM?**
- Clear hierarchy (`.card`, `.card__title`, `.card__title--large`)
- No naming conflicts
- AI-friendly (predictable patterns)

**Why Semantic?**
- `.feed-card` is clearer than `.card-type-3`
- Self-documenting code
- Easier for humans to scan

### File Organization

```
assets/
├── scss/
│   ├── main.scss              # Entry point
│   ├── _variables.scss        # Colors, fonts, spacing
│   ├── _base.scss            # Reset, typography, global elements
│   ├── _layout.scss          # Grid, containers, wrappers
│   ├── _components/
│   │   ├── _header.scss
│   │   ├── _footer.scss
│   │   ├── _feed-card.scss
│   │   ├── _sidebar.scss
│   │   ├── _callout.scss
│   │   └── ...
│   └── _utilities.scss       # Spacing, display helpers
```

### Naming Convention

**Pattern**: `.[block]__[element]--[modifier]`

**Examples**:
```css
.feed-card                    /* Block */
.feed-card__image            /* Element */
.feed-card__title            /* Element */
.feed-card__title--large     /* Modifier */
.feed-card--featured         /* Block modifier */
```

**Key Rule**: Keep it semantic and specific.
- ✅ `.callout--warning`
- ❌ `.box--red`

---

## Core Component Library

### 1. Component: Header

**Purpose**: Site-wide navigation and branding

**File**: `layouts/partials/header.html` + `_components/_header.scss`

**Structure**:
```html
<header class="site-header">
  <div class="site-header__container">
    <div class="site-header__brand">
      <a href="/" class="site-header__logo">
        [Logo/Site Name]
      </a>
    </div>
    <nav class="site-header__nav">
      <ul class="nav-menu">
        <li class="nav-menu__item">
          <a href="/about/" class="nav-menu__link">About</a>
        </li>
      </ul>
    </nav>
  </div>
</header>
```

**Variants**:
- `.site-header--transparent` (for homepage heroes)
- `.site-header--sticky` (fixed on scroll)

**Responsive Behavior**:
- Desktop: Horizontal nav
- Mobile: Hamburger menu (requires JS toggle)

**Accessibility**:
- Use `<nav>` landmark
- Skip-to-content link for keyboard users
- Proper ARIA labels on mobile toggle

---

### 2. Component: Footer

**Purpose**: Site-wide footer with links, copyright, social

**File**: `layouts/partials/footer.html` + `_components/_footer.scss`

**Structure**:
```html
<footer class="site-footer">
  <div class="site-footer__container">
    <div class="site-footer__columns">
      <div class="footer-column">
        <h4 class="footer-column__title">About</h4>
        <ul class="footer-column__list">
          <li><a href="/about/">About Us</a></li>
        </ul>
      </div>
    </div>
    <div class="site-footer__bottom">
      <p class="site-footer__copyright">© 2025 Brand Name</p>
    </div>
  </div>
</footer>
```

**Accessibility**:
- Use `<footer>` landmark
- Ensure links have adequate contrast

---

### 3. Component: Feed Card

**Purpose**: Preview card for blog posts, portfolio items, etc.

**File**: `layouts/partials/feed-card.html` + `_components/_feed-card.scss`

**Structure**:
```html
<article class="feed-card">
  <a href="[permalink]" class="feed-card__image-link">
    <img src="[image]" alt="[alt]" class="feed-card__image" loading="lazy">
  </a>
  <div class="feed-card__content">
    <div class="feed-card__category">[Category]</div>
    <h3 class="feed-card__title">
      <a href="[permalink]" class="feed-card__title-link">[Title]</a>
    </h3>
    <p class="feed-card__summary">[Summary]</p>
    <footer class="feed-card__meta">
      <time datetime="[ISO date]" class="feed-card__date">[Date]</time>
    </footer>
  </div>
</article>
```

**Variants**:
- `.feed-card--featured` (larger, highlighted)
- `.feed-card--horizontal` (side-by-side layout)

**Responsive Behavior**:
- Mobile: Stack vertically
- Tablet+: Grid layout (defined by parent)

**Accessibility**:
- Use `<article>` for semantic meaning
- Image must have descriptive alt text
- Date uses proper `<time>` element with `datetime`

---

### 4. Component: Sidebar

**Purpose**: Metadata and navigation for single posts

**File**: `layouts/partials/sidebar.html` + `_components/_sidebar.scss`

**Structure**:
```html
<aside class="sidebar">
  <div class="sidebar-block">
    <h4 class="sidebar-block__title">Author</h4>
    <div class="sidebar-block__content">
      [Author info]
    </div>
  </div>

  <div class="sidebar-block sidebar-block--toc">
    <h4 class="sidebar-block__title">On This Page</h4>
    <div class="sidebar-block__content">
      [Table of Contents]
    </div>
  </div>
</aside>
```

**Variants**:
- `.sidebar-block--toc` (table of contents styling)
- `.sidebar-block--sticky` (fixed on scroll)

**Responsive Behavior**:
- Desktop: Right rail (25-30% width)
- Mobile: Below content OR accordion

**Accessibility**:
- Use `<aside>` landmark
- Headings for each block (not just visual)

---

### 5. Component: Callout Box

**Purpose**: Inline emphasized content blocks

**File**: `layouts/shortcodes/callout.html` + `_components/_callout.scss`

**Structure**:
```html
<div class="callout callout--info">
  <div class="callout__content">
    [Markdown content rendered here]
  </div>
</div>
```

**Variants** (required):
- `.callout--info` (blue, informational)
- `.callout--warning` (yellow/orange, caution)
- `.callout--tip` (green, helpful hint)
- `.callout--danger` (red, important warning)

**Visual Requirements**:
- Icon or visual indicator for each type
- Distinct background color
- Adequate padding
- Border or shadow for definition

**Accessibility**:
- Use ARIA role if semantic meaning needed (`role="note"` for tips)
- Ensure color is not the only differentiator (use icons)

---

### 6. Component: Button

**Purpose**: Primary and secondary actions/links

**File**: `_components/_buttons.scss`

**Structure**:
```html
<a href="/contact/" class="button button--primary">Get Started</a>
<button type="submit" class="button button--secondary">Learn More</button>
```

**Variants** (required):
- `.button--primary` (main CTA, bold color)
- `.button--secondary` (outline or muted)
- `.button--large`
- `.button--small`

**States** (required):
```css
.button:hover { }
.button:focus { }
.button:active { }
.button:disabled { }
```

**Accessibility**:
- Use `<button>` for actions, `<a>` for navigation
- Visible focus state (not `outline: none` without replacement)
- Adequate click target size (min 44x44px)

---

### 7. Component: Hero Section

**Purpose**: Large prominent section (often on homepage)

**File**: `_components/_hero.scss`

**Structure**:
```html
<section class="hero">
  <div class="hero__content">
    <h1 class="hero__title">[Headline]</h1>
    <p class="hero__subtitle">[Supporting text]</p>
    <a href="[link]" class="button button--primary hero__cta">[CTA]</a>
  </div>
</section>
```

**Variants**:
- `.hero--with-image` (background image)
- `.hero--centered` (text alignment)
- `.hero--minimal` (less padding)

**Responsive Behavior**:
- Mobile: Smaller text, vertical padding
- Desktop: Larger text, more dramatic

---

### 8. Component: Contact Form

**Purpose**: User input form for contact/inquiries

**File**: `layouts/partials/contact-form.html` + `_components/_forms.scss`

**Structure**:
```html
<form class="contact-form" method="POST">
  <div class="form-field">
    <label for="name" class="form-field__label">Name</label>
    <input type="text" id="name" name="name" class="form-field__input" required>
  </div>

  <div class="form-field">
    <button type="submit" class="button button--primary">Send</button>
  </div>
</form>
```

**States** (required):
```css
.form-field__input:focus { }
.form-field__input:invalid { }
.form-field__input:disabled { }
```

**Accessibility**:
- Every input has a `<label>` with matching `for` attribute
- Use `required` attribute for validation
- Error messages associated with fields (ARIA)
- Visible focus states

---

## Layout Components

### Grid System

**Purpose**: Responsive grid for feed cards, galleries, columns

**Class Pattern**: `.grid` + modifiers

**Example**:
```html
<div class="grid grid--3-col">
  <div class="grid__item">[Card]</div>
  <div class="grid__item">[Card]</div>
  <div class="grid__item">[Card]</div>
</div>
```

**Modifiers**:
- `.grid--2-col`
- `.grid--3-col`
- `.grid--4-col`
- `.grid--auto` (auto-fit based on min-width)

**Responsive Behavior**:
- Mobile: Always 1 column
- Tablet: 2 columns
- Desktop: As specified

---

### Container

**Purpose**: Content width constraint

**Class**: `.container`

**Usage**:
```html
<div class="container">
  [Content constrained to max-width]
</div>
```

**Modifiers**:
- `.container--narrow` (max-width: 800px, for reading)
- `.container--wide` (max-width: 1400px)

---

## Responsive Breakpoints

Standardized breakpoints for consistency:

```scss
$breakpoint-mobile: 480px;
$breakpoint-tablet: 768px;
$breakpoint-desktop: 1024px;
$breakpoint-wide: 1280px;
```

**Mobile-First Approach**: Base styles are mobile, use `min-width` media queries to enhance.

---

## Color System

### Semantic Naming

Colors should have semantic names, not literal:

```scss
// ✅ Good
$color-primary: #0066cc;
$color-accent: #ff6b35;
$color-text: #1a1a1a;
$color-background: #ffffff;

// ❌ Bad
$blue: #0066cc;
$orange: #ff6b35;
```

### Required Colors

Every project needs:
- `$color-primary` (brand color, main CTAs)
- `$color-accent` (secondary brand color)
- `$color-text` (body text)
- `$color-text-light` (muted text)
- `$color-background`
- `$color-border`
- `$color-success` (for positive feedback)
- `$color-warning` (for caution)
- `$color-danger` (for errors)

---

## Typography System

### Font Stack

```scss
$font-primary: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
$font-secondary: Georgia, "Times New Roman", serif; // For headings or accents
$font-mono: "Courier New", Courier, monospace;
```

### Scale

Use a modular scale for consistency:

```scss
$text-xs: 0.75rem;   // 12px
$text-sm: 0.875rem;  // 14px
$text-base: 1rem;    // 16px
$text-lg: 1.125rem;  // 18px
$text-xl: 1.25rem;   // 20px
$text-2xl: 1.5rem;   // 24px
$text-3xl: 1.875rem; // 30px
$text-4xl: 2.25rem;  // 36px
```

---

## Accessibility Requirements

Every component must:

1. **Use semantic HTML** (correct elements for purpose)
2. **Support keyboard navigation** (focusable, logical tab order)
3. **Have visible focus states** (never remove outlines without replacement)
4. **Meet WCAG 2.1 AA contrast ratios**:
5. **Include ARIA labels** where semantic HTML isn't enough
6. **Work without JavaScript** (progressive enhancement)

---

## Adding New Components

When creating a new component:

1. **Define the purpose** (what problem does it solve?)
2. **Create the HTML structure** (semantic, accessible)
3. **Name with BEM** (`.component__element--modifier`)
4. **Document variants** (what options exist?)
5. **Test responsively** (mobile, tablet, desktop)
6. **Verify accessibility** (keyboard, screen reader, contrast)
7. **Add to this document**

---

## Component Checklist

Before finalizing any component:

- [ ] Semantic HTML elements used
- [ ] BEM naming convention followed
- [ ] Responsive behavior defined
- [ ] Accessible (keyboard, ARIA, focus states)
- [ ] Color contrast meets WCAG AA
- [ ] Works without JavaScript
- [ ] Documented in this file
