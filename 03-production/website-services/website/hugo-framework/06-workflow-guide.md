---
title: "Hugo Implementation Workflow"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/06-workflow-guide
phase: development
audience: both
duration: "1-2 weeks"
type: process-guide
effort: high
human_interaction: review-required
sequence_order: 3
parallelizable: true
ai_role: execute
requires:
  - approved-designs
  - optimized-content
  - design-tokens
deliverables:
  - deployed-hugo-site
  - content-management-system
tags:
  - hugo
  - implementation
  - workflow
  - deployment
  - step-by-step
---

# Workflow Guide

Step-by-step process for building a new Hugo site with the R7 Framework.

---

## ⚠️ Before You Start: Design & Content Phase

**This workflow assumes you have completed the Design & Discovery Phase AND the AEO Copywriting Phase.**

If you're starting a brand new project, you must first complete:

1. **[Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md)** - That phase covers:

2. **[AEO Copywriting](/docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting.md)** - That phase covers:

**What you should have before starting this workflow**:
- ✅ Approved page designs (all templates)
- ✅ Component gallery with specifications
- ✅ Design tokens documented (colors, fonts, spacing)
- ✅ AEO-optimized copy for all pages
- ✅ Content structure defined
- ✅ Brand assets collected

**If you already have designs and content**, proceed with this workflow.

**If you're starting from scratch**, complete [Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md) and [AEO Copywriting](/docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting.md) first.

---

## Overview

This workflow follows a specific order designed to:
1. **Build foundation first** (architecture before content)
2. **Create reusable pieces** (components before pages)
3. **Progress from general to specific** (templates before unique layouts)
4. **Test incrementally** (verify each phase works)

**Estimated Time**: 2-4 hours for basic structure, then content creation as needed.

**Total Project Time** (including Design & Discovery): 2-3 weeks

---

## Phase 0: Technical Planning

**Goal**: Map approved designs to Hugo implementation strategy.

**Note**: This is NOT client discovery—that was done in [Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md). This is technical planning for Hugo implementation.

### Tasks

#### 1. Review Design Deliverables
**Check that you have**:
- [ ] Component gallery with full specifications
- [ ] All page designs (desktop, tablet, mobile)
- [ ] Design tokens (colors, fonts, spacing)
- [ ] Content structure and copy

**If anything is missing**, return to Design & Discovery phase.

#### 2. Map Designs to Hugo Patterns
**Questions to answer**:
- Which patterns from the Pattern Playbook match these designs?
- Are there any custom patterns needed?
- Do any components require custom Hugo partials?

**Output**: List of Hugo patterns to implement (e.g., "Homepage, Blog Post pattern, Feed Page pattern, Contact Page pattern").

**Example Mapping**:
- Design "About Us Page" → Hugo Pattern: Service/Product Page
- Design "Blog Listing" → Hugo Pattern: Feed/List Page
- Design "Blog Post" → Hugo Pattern: Blog Post (Article)

#### 3. Create Component Inventory
**From the component gallery, list**:
- Global components (header, footer)
- Reusable content components (cards, CTAs, heroes)
- Form components
- Interactive elements (buttons, inputs)

**Output**: Checklist of components to build in Hugo.

#### 4. Define Hugo Structure
**Plan**:
- Content types needed (`blog`, `pages`, `portfolio`, etc.)
- Taxonomy requirements (categories, tags)
- Custom layouts vs. default templates
- Shortcodes needed for content elements

**Output**: Hugo directory structure plan.

**⏱ Phase Duration**: 30-60 minutes

---

## Phase 1: Foundation Setup

**Goal**: Create Hugo project structure with R7 Framework architecture.

### Tasks

#### 1. Initialize Hugo Project
```bash
hugo new site [project-name]
cd [project-name]
git init
```

#### 2. Create Directory Structure
```bash
mkdir -p layouts/_default
mkdir -p layouts/partials
mkdir -p layouts/shortcodes
mkdir -p layouts/page
mkdir -p assets/scss/_components
mkdir -p archetypes
mkdir -p content/blog
mkdir -p content/pages
mkdir -p static/images
```

#### 3. Configure hugo.toml
Set basic configuration:
```toml
baseURL = "https://example.com"
languageCode = "en-us"
title = "Site Title"

[params]
  description = "Site description"
  author = "Your Name"
  twitter_handle = "@handle"
  logo = "/images/logo.png"

[taxonomies]
  category = "categories"
  tag = "tags"
```

#### 4. Create Archetypes
Copy from [Front Matter Reference](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md):
- `archetypes/default.md`
- `archetypes/post.md`

#### 5. Initialize Git
```bash
git add .
git commit -m "Initial Hugo structure with R7 Framework"
```

**⏱ Phase Duration**: 15-30 minutes

---

## Phase 2: Core Component Library

**Goal**: Build reusable partials that all templates will use.

### Build Order (in sequence)

#### 1. SEO Partial (`layouts/partials/seo.html`)
**Purpose**: Meta tags, Open Graph, Twitter Cards

**Implementation checklist**:
- [ ] Reads `seo_title`, `description` from front matter
- [ ] Includes Open Graph tags
- [ ] Includes Twitter Card tags
- [ ] Falls back to site config if page values missing
- [ ] Outputs proper `<title>` tag

**Test**: Add to a minimal `baseof.html`, view page source.

---

#### 2. Schema Partial (`layouts/partials/schema.html`)
**Purpose**: JSON-LD structured data

**Implementation checklist**:
- [ ] Checks `schema.type` from front matter
- [ ] Implements `Article` type (minimum)
- [ ] Implements `WebPage` type
- [ ] Outputs valid JSON-LD

**Test**: Validate with [Google Rich Results Test](https://search.google.com/test/rich-results).

---

#### 3. Header Partial (`layouts/partials/header.html`)
**Purpose**: Site navigation and branding

**Implementation checklist**:
- [ ] Logo/site title links to homepage
- [ ] Navigation menu (config-driven or hardcoded)
- [ ] Semantic HTML (`<header>`, `<nav>`)
- [ ] Responsive (mobile menu placeholder)

**Test**: View on mobile and desktop sizes.

---

#### 4. Footer Partial (`layouts/partials/footer.html`)
**Purpose**: Site footer with links and copyright

**Implementation checklist**:
- [ ] Copyright notice with year
- [ ] Footer links (About, Privacy, etc.)
- [ ] Semantic HTML (`<footer>`)

**Test**: Appears on all pages.

---

#### 5. Feed Card Partial (`layouts/partials/feed-card.html`)
**Purpose**: Preview card for blog posts/portfolio items

**Implementation checklist**:
- [ ] Takes page context as input
- [ ] Displays featured image, title, summary, date
- [ ] Uses semantic HTML (`<article>`)
- [ ] Accessible (alt text, time element)

**Test**: Call manually in a test page with sample data.

---

#### 6. Sidebar Partial (`layouts/partials/sidebar.html`)
**Purpose**: Post metadata and navigation

**Implementation checklist**:
- [ ] Displays author (if present)
- [ ] Shows categories and tags
- [ ] Table of contents (if `show_toc: true`)
- [ ] Semantic HTML (`<aside>`)

**Test**: Include in a test single page template.

---

#### 7. Contact Form Partial (`layouts/partials/contact-form.html`)
**Purpose**: User contact form

**Implementation checklist**:
- [ ] Name, email, message fields
- [ ] Accessible labels and structure
- [ ] Form handler configured (Netlify Forms, Formspree, etc.)

**Test**: Submit test form.

**⏱ Phase Duration**: 2-3 hours

---

## Phase 3: Master Template

**Goal**: Create the `baseof.html` that all pages inherit from.

### Tasks

#### 1. Create `layouts/_default/baseof.html`

**Implementation checklist**:
- [ ] DOCTYPE and `<html>` structure
- [ ] `<head>` includes SEO partial
- [ ] `<head>` includes CSS link
- [ ] `<body>` includes header partial
- [ ] `<main>` contains `{{- block "main" . }}{{- end -}}`
- [ ] `<body>` includes footer partial
- [ ] Before `</body>`, includes schema partial
- [ ] Before `</body>`, includes JS (if needed)

**Reference**: See Gemini advice Document 4 for structure.

**Test**: Create a minimal content file, run `hugo server`, verify structure renders.

**⏱ Phase Duration**: 30 minutes

---

## Phase 4: Page Templates

**Goal**: Build templates for each pattern identified in Phase 0.

### Build Order (by pattern priority)

#### 1. Single Page Template (`layouts/_default/single.html`)

**Implementation checklist**:
- [ ] Defines `{{- define "main" -}}` block
- [ ] Displays page title as `<h1>`
- [ ] Shows author and date (if present)
- [ ] Renders `.Content`
- [ ] Conditionally shows sidebar (if `show_sidebar: true`)
- [ ] Responsive layout (sidebar moves on mobile)

**Test**: Create test content file (`content/test-page.md`), verify rendering.

---

#### 2. List Page Template (`layouts/_default/list.html`)

**Implementation checklist**:
- [ ] Defines `{{- define "main" -}}` block
- [ ] Displays section title
- [ ] Renders intro content from `_index.md`
- [ ] Loops through `.Pages`
- [ ] Calls `feed-card.html` partial for each page
- [ ] Implements pagination (if `paginate` set)
- [ ] Uses grid layout

**Test**: Create `content/blog/_index.md` and sample posts, verify list renders.

---

#### 3. Homepage Template (`layouts/index.html`)

**Implementation checklist**:
- [ ] Defines `{{- define "main" -}}` block
- [ ] Hero section using `hero` front matter
- [ ] Main content area
- [ ] Featured posts/content section
- [ ] Calls `feed-card.html` for featured items

**Test**: Create `content/_index.md` with hero data, verify homepage renders.

---

#### 4. Contact Page Template (`layouts/page/contact.html`)

**Implementation checklist**:
- [ ] Defines `{{- define "main" -}}` block
- [ ] Two-column layout
- [ ] Includes contact form partial
- [ ] Displays contact info from content or config

**Test**: Create `content/contact.md` with `layout: "contact"`, verify custom layout works.

---

#### 5. Additional Custom Templates (as needed)
Based on Phase 0 planning:
- Landing page template
- Portfolio template
- Custom page layouts

**⏱ Phase Duration**: 2-3 hours

---

## Phase 5: Styling (CSS)

**Goal**: Translate design system from Design & Discovery into CSS.

**Reference**: Your component gallery from [Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md) Phase 3.

### Tasks

#### 1. Setup Sass Structure
Create files from [Component System](/docs/03-production/website-services/website/hugo-framework/04-component-system.md):
```
assets/scss/
├── main.scss
├── _variables.scss
├── _base.scss
├── _layout.scss
├── _utilities.scss
└── _components/
    ├── _header.scss
    ├── _footer.scss
    ├── _feed-card.scss
    ├── _sidebar.scss
    ├── _buttons.scss
    ├── _forms.scss
    └── _hero.scss
```

#### 2. Define Variables (`_variables.scss`)
**Source**: Design tokens from [Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md) Step 3 (Component Gallery).

Transfer your approved design specifications:
- **Colors**: Primary, secondary, accent, text, backgrounds (exact hex codes from component gallery)
- **Typography**: Font stacks, sizes, weights, line-heights (from typography scale)
- **Spacing**: Margin/padding scale (from spacing system)
- **Breakpoints**: Mobile, tablet, desktop widths

#### 3. Base Styles (`_base.scss`)
- CSS reset/normalize
- Body typography
- Heading styles
- Link styles

#### 4. Layout (`_layout.scss`)
- Container widths
- Grid system
- Responsive utilities

#### 5. Component Styles
Style each component built in Phase 2:
- Header (navigation, logo)
- Footer
- Feed cards
- Sidebar
- Buttons
- Forms
- Hero section

**Follow**: BEM naming from Component System documentation.

#### 6. Compile and Test
Configure Hugo to process Sass:
```toml
# hugo.toml
[build]
  writeStats = true
```

Link in `baseof.html`:
```html
{{ $styles := resources.Get "scss/main.scss" | toCSS | minify | fingerprint }}
<link rel="stylesheet" href="{{ $styles.RelPermalink }}">
```

**Test**: View all pages, verify styling works, test responsive behavior.

**⏱ Phase Duration**: 3-5 hours (varies by design complexity)

---

## Phase 6: Content Shortcodes

**Goal**: Create reusable content components for authors.

### Tasks

#### 1. Wide Image Shortcode (`layouts/shortcodes/wide-image.html`)

**Implementation**:
```html
{{- $src := .Get "src" -}}
{{- $alt := .Get "alt" -}}
<figure class="img-wide">
  <img src="{{ $src }}" alt="{{ $alt }}" loading="lazy">
</figure>
```

**Test**: Use in content file, verify rendering.

---

#### 2. Callout Shortcode (`layouts/shortcodes/callout.html`)

**Implementation**:
```html
{{- $type := .Get "type" | default "info" -}}
<div class="callout callout--{{ $type }}">
  {{ .Inner | markdownify }}
</div>
```

**Test**: Create callouts with types: info, warning, tip, danger.

---

#### 3. Additional Shortcodes (as needed)
Based on content requirements:
- Video embed
- Code block with syntax highlighting
- Image gallery
- Quote block

**⏱ Phase Duration**: 30-60 minutes

---

## Phase 7: Content Creation

**Goal**: Populate site with actual content.

### Process (for each page/post)

#### 1. Choose Pattern
Refer to [Pattern Playbook](/docs/03-production/website-services/website/hugo-framework/03-pattern-playbook.md) to select appropriate pattern.

#### 2. Create Content File
```bash
hugo new blog/my-post.md       # Uses archetypes/post.md
hugo new pages/about.md        # Uses archetypes/default.md
```

#### 3. Fill Front Matter
Use [Front Matter Reference](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md) to complete all required fields:
- `title`, `seo_title`, `description` (critical!)
- `featured_image`, `featured_image_alt`
- `date`, `author` (for posts)
- Pattern-specific fields

#### 4. Write Content
Follow [Core Principles](/docs/03-production/website-services/website/hugo-framework/02-core-principles.md):
- Start with 18-token core answer phrase
- Use proper heading hierarchy
- Write to topic completion (no word count target)

#### 5. Add Images
- Place in `static/images/`
- Use descriptive filenames
- Optimize file sizes

#### 6. Review and Publish
- Preview with `hugo server -D`
- Check responsive layout
- Validate SEO with browser extensions
- Set `draft: false`

**⏱ Phase Duration**: Ongoing (per content piece: 30 min - 2 hours)

---

## Phase 8: Testing & Validation

**Goal**: Ensure site meets quality standards.

### Checklist

#### SEO & Metadata
- [ ] All pages have unique `seo_title` and `description`
- [ ] Meta descriptions are 150-160 characters
- [ ] Open Graph tags present and correct
- [ ] Twitter Cards display properly (test with [Card Validator](https://cards-dev.twitter.com/validator))

#### Schema & Structured Data
- [ ] All pages have appropriate Schema type
- [ ] JSON-LD validates (use [Schema Markup Validator](https://validator.schema.org/))
- [ ] Rich results preview correctly ([Google Rich Results Test](https://search.google.com/test/rich-results))

#### Accessibility
- [ ] All images have alt text
- [ ] Heading hierarchy is logical (one H1, proper nesting)
- [ ] Forms have proper labels
- [ ] Color contrast meets WCAG AA (use [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/))
- [ ] Keyboard navigation works
- [ ] Focus states visible

#### Performance
- [ ] Images optimized (use WebP, proper sizes)
- [ ] CSS/JS minified
- [ ] Lazy loading enabled for images
- [ ] Lighthouse score 90+ (run in Chrome DevTools)

#### Responsive Design
- [ ] Test on mobile (320px width)
- [ ] Test on tablet (768px width)
- [ ] Test on desktop (1280px+ width)
- [ ] All components adapt properly

#### Content Quality
- [ ] Every page answers one question
- [ ] Core answer phrase appears first
- [ ] Heading hierarchy correct
- [ ] No broken links (use `hugo --check`)
- [ ] Spelling and grammar checked

**⏱ Phase Duration**: 1-2 hours

---

## Phase 9: Deployment

**Goal**: Publish site to production.

### Recommended Platforms
- **Netlify** (easiest, CI/CD built-in)
- **Vercel** (excellent performance)
- **Cloudflare Pages** (fast CDN)
- **GitHub Pages** (free, basic)

### Netlify Deployment (recommended)

#### 1. Create `netlify.toml`
```toml
[build]
  publish = "public"
  command = "hugo --gc --minify"

[build.environment]
  HUGO_VERSION = "0.120.0"
  HUGO_ENV = "production"

[context.production.environment]
  HUGO_ENV = "production"

[[redirects]]
  from = "/*"
  to = "/404.html"
  status = 404
```

#### 2. Connect Git Repository
- Push to GitHub/GitLab
- Connect repo in Netlify dashboard
- Configure build settings (should auto-detect)

#### 3. Configure Domain
- Add custom domain in Netlify
- Enable HTTPS (automatic with Let's Encrypt)

#### 4. Enable Forms (if using contact form)
Forms with `data-netlify="true"` work automatically on Netlify.

**⏱ Phase Duration**: 30-60 minutes

---

## Phase 10: Maintenance & Updates

**Goal**: Keep site fresh and functional.

### Regular Tasks

#### Weekly
- [ ] Review analytics
- [ ] Check for broken links
- [ ] Monitor site speed (Lighthouse)

#### Monthly
- [ ] Update Hugo version
- [ ] Review and update lastmod dates on changed content
- [ ] Audit SEO performance

#### Quarterly
- [ ] Content audit (remove outdated, update stats)
- [ ] Accessibility audit
- [ ] Security review (dependencies)

#### When Adding New Content
1. Choose pattern from playbook
2. Use appropriate archetype
3. Follow content principles
4. Test before publishing
5. Monitor performance

---

## Workflow Shortcuts for AI

When instructing an AI assistant to build a site:

### Quick Setup Command
```
"Build a Hugo site using R7 Framework with:
- Pattern X, Y, Z (from Pattern Playbook)
- Color scheme: [colors]
- Follow all documentation in /hugo-framework/

Start with Phase 1 (Foundation Setup)."
```

### Iterative Development
```
"We're on Phase [N]. Complete all tasks for this phase:
- [list specific tasks from this guide]
- Follow [relevant doc reference]
- Test each component before proceeding"
```

### Content Creation
```
"Create a [pattern name] at [path]:
- Use archetype from Front Matter Reference
- Follow content principles (18-token answer, heading hierarchy)
- Include all required fields
- Content topic: [topic]"
```

---

## Troubleshooting Common Issues

### "Page not rendering"
- Check `draft: false` in front matter
- Verify template exists for pattern
- Check Hugo server terminal for errors

### "Styles not loading"
- Verify Sass compilation in `hugo.toml`
- Check file path in `baseof.html`
- Clear browser cache

### "Schema validation errors"
- Ensure required fields present in front matter
- Check JSON-LD syntax (commas, brackets)
- Validate with Schema.org validator

### "Sidebar not showing"
- Confirm `show_sidebar: true` in front matter
- Check template conditional logic
- Verify sidebar partial exists

---

## Success Metrics

A successful R7 Framework implementation has:

✅ **Structure**
- All patterns documented
- All components reusable
- Archetypes for all content types

✅ **Quality**
- 90+ Lighthouse score
- WCAG AA accessibility
- Valid Schema markup

✅ **Performance**
- Sub-second page loads
- Optimized images
- Minified CSS/JS

✅ **SEO**
- Unique meta descriptions on all pages
- Proper heading hierarchy
- Answer-first content

✅ **Maintainability**
- Clear documentation
- Consistent naming conventions
- Git history with meaningful commits

---

## Next Steps After Launch

1. **Set up monitoring**

2. **Create content calendar**

3. **Document customizations**

4. **Share learnings**

---

## Conclusion

This workflow is designed to be:
- **Repeatable**: Same process every time
- **Flexible**: Choose patterns as needed
- **Scalable**: Add complexity incrementally
- **AI-friendly**: Clear instructions for automation

**Follow this sequence, refer to the framework docs, and you'll build consistent, high-quality Hugo sites every time.**
