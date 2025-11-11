---
title: "Component Gallery SOP"
description: "Standard Operating Procedure for building and maintaining the Hugo component library"
weight: 7
tags: ["sop", "components", "hugo", "workflow", "maintenance"]
status: "complete"
---

# Component Gallery SOP

**Purpose:** Standard Operating Procedure for building, deploying, and maintaining the R7 Creative Hugo component library

**Last Updated:** November 10, 2025

---

## Overview

The Component Gallery is R7 Creative's **master Hugo theme** that serves as the foundation for all client websites. It contains all the reusable components, layouts, and design systems needed to rapidly deploy professional, AEO-optimized websites.

**Key Concept:** Build once, clone and configure for each client.

→ Related Documentation: [Component Design System](/docs/03-production/website-services/website/hugo-framework/04-component-system)

---

## Part 1: Initial Component Library Setup

### Phase 1: Planning & Architecture (2-4 hours)

**Objective:** Define the complete scope of components before building

**Steps:**

1. **Review the Authoritative Component Needs List**
   - Located in: `help_me_claude/authoritative component needs list.md`
   - This defines the 4 categories of components needed

2. **Audit Existing Component Documentation**
   - Review: `/docs/03-production/website-services/website/hugo-framework/04-component-system.md`
   - Verify all documented components are included in build plan

3. **Create Component Inventory Checklist**
   - Use the checklist below as your master tracking document
   - Mark items as: `[ ]` Not Started | `[~]` In Progress | `[✓]` Complete

**Component Inventory Checklist:**

```markdown
## 1. Site-Wide (Global) Components
- [ ] Header (with logo, nav, mobile hamburger, CTA button)
- [ ] Footer (with GBP mirror: NAP, hours, service area, social links, secondary nav, copyright)

## 2. Page Layouts (Hugo Templates)
- [ ] Homepage (`layouts/index.html`) - modular stacking
- [ ] Default Single Page (`layouts/_default/single.html`)
- [ ] Default List Page (`layouts/_default/list.html`)
- [ ] Authority Hub List (styled blog/article hub)
- [ ] Authority Hub Single (styled article page with author bio)
- [ ] Services Hub (`layouts/section/services.html`)
- [ ] 404 Error Page

## 3. Content Components (Building Blocks)
- [ ] Hero - Simple (text + CTA)
- [ ] Hero - Image (text/CTA over background image)
- [ ] Hero - Split (image/video + text/form side-by-side)
- [ ] CTA Banner (headline + button, repeatable)
- [ ] Service List Grid (3-4 services with icons)
- [ ] Testimonial Slider (carousel, 3-5 testimonials)
- [ ] Testimonial Grid (full-page layout)
- [ ] About Us Block (2-column: image + text)
- [ ] Process Block (3-4 step "How It Works")
- [ ] Team Grid (photos, names, titles)
- [ ] Logo Ticker (scrolling brand logos)

## 4. Special Feature Modules
- [ ] Contact Form (Netlify Forms integration)
- [ ] FAQ Accordion (pulls from data file)
- [ ] Sortable Image Gallery (category filters + lightbox)
```

---

### Phase 2: Environment Setup (30 minutes)

**Objective:** Prepare development environment for theme building

**Steps:**

1. **Create New Hugo Theme Repository**
   ```bash
   hugo new theme r7-component-library
   cd themes/r7-component-library
   ```

2. **Set Up Directory Structure**
   ```
   r7-component-library/
   ├── layouts/
   │   ├── _default/
   │   │   ├── baseof.html
   │   │   ├── single.html
   │   │   ├── list.html
   │   ├── partials/
   │   │   ├── header.html
   │   │   ├── footer.html
   │   │   ├── feed-card.html
   │   │   ├── sidebar.html
   │   │   └── ...
   │   ├── shortcodes/
   │   │   ├── callout.html
   │   │   ├── hero.html
   │   │   ├── cta.html
   │   │   └── ...
   │   ├── index.html
   │   └── 404.html
   ├── assets/
   │   └── scss/
   │       ├── main.scss
   │       ├── _variables.scss
   │       ├── _base.scss
   │       ├── _layout.scss
   │       ├── _components/
   │       │   ├── _header.scss
   │       │   ├── _footer.scss
   │       │   ├── _feed-card.scss
   │       │   └── ...
   │       └── _utilities.scss
   ├── static/
   │   └── js/
   │       ├── main.js
   │       └── gallery.js
   └── theme.toml
   ```

3. **Install Hugo (if not already installed)**
   - Follow official Hugo installation: https://gohugo.io/installation/

4. **Create Test Site for Development**
   ```bash
   hugo new site component-library-test
   cd component-library-test
   git clone [your-theme-repo] themes/r7-component-library
   ```

---

### Phase 3: Build Global Components (4-6 hours)

**Objective:** Create header and footer that appear on every page

#### 3.1: Build Header Component

**File:** `layouts/partials/header.html`

**Requirements:**
- Logo placement (pulled from `config.toml`)
- Primary navigation (generates from main menu in `config.toml`)
- Mobile hamburger menu with JS toggle
- Main CTA button (configurable text and link)

**CSS File:** `assets/scss/_components/_header.scss`

**Checklist:**
- [ ] Desktop horizontal navigation
- [ ] Mobile hamburger menu with animation
- [ ] Sticky header variant (optional)
- [ ] Transparent header variant for hero sections
- [ ] Keyboard accessible navigation
- [ ] Proper ARIA labels

**Configuration Example (`config.toml`):**
```toml
[params]
  logo = "/images/logo.png"
  cta_text = "Get a Quote"
  cta_link = "/contact/"

[[menu.main]]
  name = "Services"
  url = "/services/"
  weight = 1
```

#### 3.2: Build Footer Component

**File:** `layouts/partials/footer.html`

**Critical Requirement:** **GBP Mirror Section**
- Name, Address, Phone (NAP) pulled from config
- Business Hours pulled from config
- Service Area text or map
- Social media links
- Secondary navigation
- Copyright line with auto-updating year

**CSS File:** `assets/scss/_components/_footer.scss`

**Checklist:**
- [ ] GBP mirror section (NAP, hours, service area)
- [ ] Social media icons (configurable in config)
- [ ] Secondary navigation menu
- [ ] Auto-updating copyright year
- [ ] Mobile responsive layout
- [ ] Accessible footer landmark

**Configuration Example (`config.toml`):**
```toml
[params.business]
  name = "ABC Plumbing"
  address = "123 Main St, Columbus, OH 43215"
  phone = "(614) 555-1234"
  hours = "Mon-Fri: 8am-6pm, Sat: 9am-3pm"
  service_area = "Serving Columbus and surrounding areas"

[params.social]
  facebook = "https://facebook.com/abcplumbing"
  instagram = "https://instagram.com/abcplumbing"
```

---

### Phase 4: Build Page Layouts (6-8 hours)

**Objective:** Create the template scaffolding for different page types

#### 4.1: Base Template

**File:** `layouts/_default/baseof.html`

**Purpose:** Master template that wraps all pages

```html
<!DOCTYPE html>
<html lang="{{ .Site.Language.Lang }}">
<head>
  {{ partial "head.html" . }}
</head>
<body>
  {{ partial "header.html" . }}
  <main>
    {{ block "main" . }}{{ end }}
  </main>
  {{ partial "footer.html" . }}
  {{ partial "scripts.html" . }}
</body>
</html>
```

#### 4.2: Homepage Template

**File:** `layouts/index.html`

**Purpose:** Modular homepage that stacks components

**Key Concept:** No hardcoded content. Homepage should be built by stacking shortcodes/partials.

**Example:**
```markdown
---
title: "Home"
---

{{</* hero type="image" */>}}
{{</* service-grid */>}}
{{</* testimonial-slider */>}}
{{</* cta-banner */>}}
```

#### 4.3: Other Layout Templates

Build these templates according to the Component Inventory Checklist:
- `layouts/_default/single.html` (basic content pages)
- `layouts/_default/list.html` (basic list pages)
- Authority Hub layouts (styled blog)
- Services hub layout (automatic grid of child services)
- 404 error page

---

### Phase 5: Build Content Components (10-15 hours)

**Objective:** Create all building block shortcodes and partials

**Process for Each Component:**

1. **Reference the Component Design System**
   - File: `/docs/03-production/website-services/website/hugo-framework/04-component-system.md`
   - Follow BEM naming conventions
   - Implement all required variants

2. **Create HTML Structure**
   - File location: `layouts/shortcodes/[component].html` or `layouts/partials/[component].html`
   - Use semantic HTML
   - Ensure accessibility (ARIA, keyboard nav, focus states)

3. **Create SCSS Styles**
   - File location: `assets/scss/_components/_[component].scss`
   - Follow BEM naming: `.component__element--modifier`
   - Import in `main.scss`

4. **Test Responsive Behavior**
   - Mobile (320px - 767px)
   - Tablet (768px - 1023px)
   - Desktop (1024px+)

5. **Document Usage**
   - Add usage examples to component documentation
   - Include configuration options

**Component Build Order (Recommended):**

**Week 1: Core Components**
- Hero variations (3 types)
- CTA Banner
- Service List Grid
- Button variants

**Week 2: Content Blocks**
- About Us Block
- Process Block
- Team Grid
- Logo Ticker

**Week 3: Advanced Components**
- Testimonial Slider
- Testimonial Grid
- Feed Card (for blog/portfolio)
- Sidebar

**Week 4: Special Features**
- Contact Form (with Netlify Forms)
- FAQ Accordion (with data file integration)
- Sortable Image Gallery (with JS filtering + lightbox)

---

### Phase 6: Build Special Feature Modules (8-10 hours)

#### 6.1: Contact Form with Netlify Forms

**File:** `layouts/partials/contact-form.html`

**Critical Requirement:** Must work automatically with Netlify Forms (no backend needed)

**Implementation:**
```html
<form class="contact-form" method="POST" name="contact" data-netlify="true">
  <input type="hidden" name="form-name" value="contact" />

  <div class="form-field">
    <label for="name" class="form-field__label">Name</label>
    <input type="text" id="name" name="name" class="form-field__input" required>
  </div>

  <div class="form-field">
    <label for="email" class="form-field__label">Email</label>
    <input type="email" id="email" name="email" class="form-field__input" required>
  </div>

  <div class="form-field">
    <label for="phone" class="form-field__label">Phone</label>
    <input type="tel" id="phone" name="phone" class="form-field__input">
  </div>

  <div class="form-field">
    <label for="message" class="form-field__label">Message</label>
    <textarea id="message" name="message" class="form-field__textarea" rows="5" required></textarea>
  </div>

  <div class="form-field">
    <button type="submit" class="button button--primary">Send Message</button>
  </div>
</form>
```

**Checklist:**
- [ ] `data-netlify="true"` attribute present
- [ ] Hidden `form-name` input for Netlify
- [ ] All inputs have proper labels
- [ ] Required fields marked
- [ ] Accessible (keyboard nav, ARIA)
- [ ] Responsive styling

#### 6.2: FAQ Accordion with Data File

**File:** `layouts/partials/faq-accordion.html`

**Purpose:** Pull FAQ questions/answers from a data file for easy AI configuration

**Data File Example (`data/faq.toml`):**
```toml
[[items]]
question = "How quickly can you start?"
answer = "We typically begin work within 2-3 business days of contract signing."

[[items]]
question = "What areas do you serve?"
answer = "We serve Columbus and all surrounding counties."
```

**Template:**
```html
<div class="faq-accordion">
  {{ range .Site.Data.faq.items }}
  <div class="faq-accordion__item">
    <button class="faq-accordion__question" aria-expanded="false">
      {{ .question }}
    </button>
    <div class="faq-accordion__answer" hidden>
      {{ .answer | markdownify }}
    </div>
  </div>
  {{ end }}
</div>
```

**JavaScript File:** `static/js/accordion.js`

**Checklist:**
- [ ] Data file integration working
- [ ] Accordion open/close functionality
- [ ] Keyboard accessible (Enter/Space to toggle)
- [ ] ARIA attributes (`aria-expanded`, `hidden`)
- [ ] Smooth animation
- [ ] Mobile responsive

#### 6.3: Sortable Image Gallery with Lightbox

**File:** `layouts/shortcodes/gallery.html`

**Purpose:** Display filterable image gallery with category buttons and lightbox popup

**Features Required:**
- Category filtering (based on folder structure or front matter)
- Lightbox on image click
- Responsive grid layout
- Lazy loading for performance

**JavaScript File:** `static/js/gallery.js`

**Checklist:**
- [ ] Category filter buttons working
- [ ] Images filter by category
- [ ] Lightbox opens on click
- [ ] Keyboard navigation in lightbox (ESC to close, arrows to navigate)
- [ ] Lazy loading implemented
- [ ] Mobile responsive grid
- [ ] Accessible (ARIA labels, keyboard nav)

---

### Phase 7: Testing & Quality Assurance (4-6 hours)

**Objective:** Ensure all components work correctly and meet standards

#### 7.1: Component Testing Checklist

**For Each Component:**
- [ ] Desktop view (1920px, 1440px, 1024px)
- [ ] Tablet view (768px, 1024px)
- [ ] Mobile view (375px, 414px, 320px)
- [ ] Keyboard navigation works
- [ ] Focus states visible
- [ ] Screen reader compatible (test with NVDA or VoiceOver)
- [ ] Color contrast meets WCAG AA standards
- [ ] Works without JavaScript (progressive enhancement)

#### 7.2: Cross-Browser Testing

**Test in:**
- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)
- [ ] Mobile Safari (iOS)
- [ ] Mobile Chrome (Android)

#### 7.3: Performance Testing

**Metrics to Check:**
- [ ] Lighthouse Performance Score > 90
- [ ] First Contentful Paint < 1.5s
- [ ] Largest Contentful Paint < 2.5s
- [ ] Cumulative Layout Shift < 0.1
- [ ] CSS file size < 50KB (minified + gzipped)
- [ ] JavaScript file size < 100KB (minified + gzipped)

---

### Phase 8: Documentation & Deployment (2-3 hours)

#### 8.1: Create Component Usage Guide

**File:** Create a `COMPONENT-USAGE.md` in the theme root

**Include for Each Component:**
- Component name and purpose
- Shortcode or partial syntax
- Configuration options
- Example usage
- Visual preview (screenshot or GIF)

**Example:**
```markdown
## Hero - Image Background

**Purpose:** Large hero section with background image overlay

**Shortcode:**
{{</* hero type="image" image="/images/hero-bg.jpg" */>}}
  # Your Headline Here
  Subheadline text goes here.
  {{</* button link="/contact/" text="Get Started" */>}}
{{</* /hero */>}}

**Options:**
- `type`: "image" | "split" | "simple"
- `image`: Path to background image
- `overlay`: true | false (darkens image for text readability)
```

#### 8.2: Version Control & Repository

**Checklist:**
- [ ] Initialize Git repository
- [ ] Create `.gitignore` file
- [ ] Write comprehensive `README.md`
- [ ] Tag initial release (v1.0.0)
- [ ] Push to GitHub/GitLab

**README.md Should Include:**
- Theme overview
- Installation instructions
- Configuration guide
- Link to full component documentation
- Changelog

#### 8.3: Deploy Demo Site

**Purpose:** Live demonstration of all components

**Steps:**
1. Create example content for all components
2. Build and deploy to Netlify
3. Configure custom domain (e.g., `components.r7creative.com`)
4. Add to internal documentation

---

## Part 2: Adding New Components Quarterly

### When to Add New Components

**Triggers:**
- Client requests a feature not in the library
- Identified gap during website builds
- Competitive analysis reveals missing components
- Quarterly component review identifies opportunities

### Quarterly Component Review Process

**Schedule:** Last week of each quarter (March, June, September, December)

**Duration:** 2-3 hours meeting + build time

---

### Step 1: Quarterly Review Meeting (2-3 hours)

**Attendees:**
- Website Production Lead
- Design Lead (if separate from production)
- Operations Director

**Agenda:**

1. **Review Recent Client Requests (30 min)**
   - Pull list of custom components built for clients in past quarter
   - Identify which are candidates for standardization
   - Prioritize by frequency of request

2. **Competitive Analysis (30 min)**
   - Review 3-5 competitor websites
   - Screenshot components we don't have
   - Assess value for our clients

3. **Component Gap Analysis (30 min)**
   - Review current component library
   - Identify missing patterns
   - Check against industry best practices

4. **Prioritization & Planning (30 min)**
   - Vote on top 3-5 components to add
   - Assign owner for each component
   - Set build deadlines (before next quarter)

5. **Document Decisions (15 min)**
   - Update Component Backlog spreadsheet
   - Create GitHub issues for each new component
   - Schedule build time in production calendar

**Output:**
- Prioritized list of 3-5 new components
- Assigned owners
- Build deadlines

---

### Step 2: Build New Component (4-8 hours per component)

**Process (Same as Initial Build):**

1. **Design & Spec** (1-2 hours)
   - Create visual mockup or sketch
   - Define variants needed
   - Specify configuration options
   - Document responsive behavior

2. **HTML Structure** (1-2 hours)
   - Create semantic HTML
   - Ensure accessibility
   - Add to `layouts/shortcodes/` or `layouts/partials/`

3. **CSS Styling** (2-3 hours)
   - Follow BEM naming conventions
   - Create `_components/_[name].scss`
   - Import in `main.scss`
   - Test all variants

4. **JavaScript (if needed)** (1-2 hours)
   - Add to `static/js/`
   - Ensure progressive enhancement
   - Test without JS enabled

5. **Documentation** (30 min)
   - Add to Component Usage Guide
   - Update Component Design System doc
   - Add example to demo site

6. **Testing** (1-2 hours)
   - Test responsively
   - Cross-browser testing
   - Accessibility audit
   - Performance check

---

### Step 3: Version Control & Deployment (30 min)

**Checklist:**
- [ ] Commit new component to Git
- [ ] Update CHANGELOG.md
- [ ] Bump version number (semantic versioning: v1.1.0, v1.2.0, etc.)
- [ ] Tag release in Git
- [ ] Update demo site with new component
- [ ] Announce new component to team

**Version Numbering:**
- Major (v2.0.0): Breaking changes, complete redesign
- Minor (v1.1.0): New components added
- Patch (v1.0.1): Bug fixes, small improvements

---

### Step 4: Retrospective Documentation (15 min)

**After Each Quarterly Update:**

Update the following files:
- [ ] Component Inventory Checklist (mark new items)
- [ ] Component Usage Guide (add new component docs)
- [ ] Demo site (add examples)
- [ ] Hugo framework documentation (if architecture changed)

---

## Component Backlog Management

### Backlog Spreadsheet Structure

**Columns:**
- Component Name
- Description
- Requested By (Client name or team member)
- Date Requested
- Priority (High/Medium/Low)
- Quarter Planned (Q1 2025, Q2 2025, etc.)
- Status (Backlog / In Progress / Complete)
- Owner
- GitHub Issue Link

**Example:**
| Component | Description | Requested By | Date | Priority | Quarter | Status | Owner |
|-----------|-------------|--------------|------|----------|---------|--------|-------|
| Pricing Table | 3-column pricing comparison | ABC Plumbing | 2025-01-15 | High | Q1 2025 | In Progress | Jane |
| Video Hero | Hero with background video | XYZ Electric | 2025-02-03 | Medium | Q2 2025 | Backlog | - |

**Location:** Internal project management tool or shared Google Sheet

---

## Maintenance & Updates

### Ongoing Maintenance Tasks

**Monthly:**
- [ ] Update dependencies (Hugo version, npm packages)
- [ ] Review and merge bug fix pull requests
- [ ] Check demo site for broken links/images

**Quarterly:**
- [ ] Conduct component review (see above)
- [ ] Audit accessibility compliance
- [ ] Performance audit
- [ ] Update documentation

**Annually:**
- [ ] Major version review
- [ ] Consider design refresh
- [ ] Evaluate if entire theme needs rebuild

---

## Success Metrics

**Key Performance Indicators:**

1. **Build Efficiency**
   - Average time to launch new client site
   - Target: < 5 days from kickoff to launch

2. **Component Reusability**
   - % of components reused across client sites
   - Target: > 80% component reuse

3. **Client Satisfaction**
   - Website performance scores
   - Target: Lighthouse > 90

4. **Maintenance Burden**
   - Hours spent on bug fixes per quarter
   - Target: < 10 hours/quarter

5. **Component Library Growth**
   - New components added per quarter
   - Target: 3-5 components/quarter

---

## Troubleshooting Common Issues

### Issue: Component doesn't display correctly

**Solutions:**
- Check SCSS import in `main.scss`
- Verify Hugo shortcode/partial syntax
- Clear Hugo cache: `hugo --cleanDestinationDir`
- Check browser console for JS errors

### Issue: Netlify form not submitting

**Solutions:**
- Verify `data-netlify="true"` attribute
- Confirm hidden `form-name` input matches form name
- Check Netlify dashboard for form detection
- Ensure form HTML is in a deployed `.html` file (not just JS-rendered)

### Issue: Gallery filter not working

**Solutions:**
- Check JavaScript file is loaded
- Verify category classes match filter buttons
- Check browser console for errors
- Test with JavaScript disabled (should still show all images)

---

## Resources & References

**Internal Documentation:**
- [Component Design System](/docs/03-production/website-services/website/hugo-framework/04-component-system)
- [Hugo Framework Overview](/docs/03-production/website-services/website/hugo-framework/_index)
- [AEO Copywriting Guide](/docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting)

**External Resources:**
- Hugo Documentation: https://gohugo.io/documentation/
- BEM Methodology: https://getbem.com/
- WCAG 2.1 Guidelines: https://www.w3.org/WAI/WCAG21/quickref/
- Netlify Forms: https://docs.netlify.com/forms/setup/

---

## Change Log

**v1.0.0 - November 10, 2025**
- Initial SOP created
- Comprehensive setup guide completed
- Quarterly maintenance process defined

---

**Questions or updates needed?** Contact the Operations Director or Website Production Lead.
