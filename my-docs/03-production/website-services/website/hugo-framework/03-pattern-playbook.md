---
title: "Pattern Playbook"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/03-pattern-playbook
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
  - approved-designs
  - optimized-content
deliverables:
  - pattern-selection
  - implementation-specs
tags:
  - patterns
  - templates
  - hugo
  - content-types
  - implementation
---

# Pattern Playbook

Named content patterns with purpose and implementation specifications.

---

## How to Use This Playbook

### For Humans
Scan the **Purpose** and **When to Use** sections to find the right pattern for your needs.

### For AI
Read all sections. The **Structure** section contains implementation requirements.

---

## Pattern Index

1. [Homepage](#pattern-homepage)
2. [Blog Post (Article)](#pattern-blog-post-article)
3. [Service/Product Page](#pattern-serviceproduct-page)
4. [Feed/List Page](#pattern-feedlist-page)
5. [Contact Page](#pattern-contact-page)
6. [Legal Page](#pattern-legal-page)
7. [Landing Page](#pattern-landing-page)

---

## Pattern: Homepage

### Purpose (Human)
The main entry point that introduces the brand, showcases key content, and guides visitors to primary actions.

### When to Use (Human)
- Root domain landing page (`/`)
- First impression for new visitors
- Central navigation hub

### Structure (AI)

**File Location**: `content/_index.md`

**Template**: `layouts/index.html`

**Required Front Matter**:
```yaml
title: "Homepage H1 Title"
seo_title: "Brand Name | Tagline (50-60 chars)"
description: "Core value proposition in 150-160 characters"
featured_image: "/images/og-homepage.jpg"

hero:
  title: "Main Headline"
  subtitle: "Supporting message"
  cta_text: "Primary Action"
  cta_link: "/contact/"
```

**Section Composition**:
1. Hero section (title, subtitle, CTA)
2. Main content area (from markdown content)
3. Featured content (latest posts, services, portfolio)

**Components Used**:
- `partials/seo.html`
- `partials/feed-card.html` (for featured items)
- `partials/schema.html` (type: "WebSite")

**Schema Type**: `WebSite` or `Organization`

---

## Pattern: Blog Post (Article)

### Purpose (Human)
Long-form educational or narrative content that answers one specific question with supporting evidence, examples, and context.

### When to Use (Human)
- Tutorials and how-to guides
- Thought leadership articles
- Case studies
- Industry analysis
- Any content that answers: "How?", "Why?", or "What?"

### Structure (AI)

**File Location**: `content/blog/[slug].md`

**Archetype**: `archetypes/post.md`

**Template**: `layouts/_default/single.html` (with sidebar)

**Required Front Matter**:
```yaml
title: "The Question as a Statement (The H1)"
seo_title: "Keyword-Rich Version (50-60 chars)"
description: "The 18-token core answer phrase (150-160 chars)"
date: "2025-11-06"
lastmod: "2025-11-06"
draft: false
author: "Author Name"
featured_image: "/images/posts/slug-name.jpg"
featured_image_alt: "Descriptive alt text"
categories: ["Category Name"]
tags: ["tag1", "tag2"]
show_sidebar: true
show_toc: false
```

**Content Structure**:
```markdown
# [Title - H1]

[Core answer phrase as first paragraph]

## Main Section 1 (H2)
Content...

### Sub-point A (H3)
Content...

### Sub-point B (H3)
Content...

## Main Section 2 (H2)
Content...
```

**Available Shortcodes**:
- `{{</* wide-image src="/path" alt="text" */>}}`
- `{{</* callout type="info|warning|tip" */>}}content{{</* /callout */>}}`

**Components Used**:
- `partials/seo.html`
- `partials/sidebar.html`
- `partials/schema.html` (type: "Article")

**Schema Type**: `Article`

---

## Pattern: Service/Product Page

### Purpose (Human)
Single-topic promotional or informational page focused on one service, product, or concept. More focused than a blog post, less academic.

### When to Use (Human)
- Service descriptions
- Product pages
- About pages
- Team member bios
- Portfolio project pages

### Structure (AI)

**File Location**: `content/services/[slug].md` or `content/pages/[slug].md`

**Template**: `layouts/_default/single.html` (without sidebar)

**Required Front Matter**:
```yaml
title: "Service/Product Name"
seo_title: "Service Name - Benefit (50-60 chars)"
description: "What this service solves in 150-160 chars"
date: "2025-11-06"
draft: false
featured_image: "/images/services/service-name.jpg"
featured_image_alt: "Alt text"
show_sidebar: false
layout: "single"  # Uses default single.html
```

**Content Structure**:
```markdown
# [Title - H1]

[Core answer: What this service does]

## What We Do (H2)
Details...

## How It Works (H2)
Process...

## Benefits (H2)
Value proposition...

## Get Started (H2)
Call to action...
```

**Available Shortcodes**: All standard shortcodes

**Components Used**:
- `partials/seo.html`
- `partials/schema.html` (type: "WebPage" or "Service")

**Schema Type**: `WebPage`, `Service`, or `Product`

---

## Pattern: Feed/List Page

### Purpose (Human)
A landing page that lists multiple items (blog posts, portfolio pieces, testimonials) as cards in a grid or list layout.

### When to Use (Human)
- Blog index (`/blog/`)
- Portfolio gallery (`/portfolio/`)
- Testimonials page (`/testimonials/`)
- Any collection of similar items

### Structure (AI)

**File Location**: `content/blog/_index.md` (or whichever section)

**Template**: `layouts/_default/list.html` or `layouts/blog/list.html`

**Required Front Matter**:
```yaml
title: "Section Title (e.g., 'Our Blog')"
seo_title: "Section SEO Title"
description: "What visitors will find in this collection"
date: "2025-01-01"
draft: false
featured_image: "/images/blog-header.jpg"
paginate: 9
feed_layout: "grid"  # or "list"
```

**Content in _index.md**:
```markdown
Introductory text that appears above the feed of cards.
Explains what the collection is about.
```

**Template Logic** (for AI implementation):
- Loop through `.Pages` in this section
- For each page, call `partials/feed-card.html`
- Implement pagination if `paginate` is set
- Use `feed_layout` to determine CSS class

**Components Used**:
- `partials/feed-card.html` (for each item)
- `partials/seo.html`

**Schema Type**: `CollectionPage` or `Blog`

---

## Pattern: Contact Page

### Purpose (Human)
A dedicated page with a form for visitors to reach out. May include additional contact methods (email, phone, map).

### When to Use (Human)
- Primary contact page (`/contact/`)
- Support request pages
- Consultation booking pages

### Structure (AI)

**File Location**: `content/contact.md`

**Template**: `layouts/page/contact.html` (custom layout)

**Required Front Matter**:
```yaml
title: "Contact Us"
seo_title: "Contact [Brand Name] | Get in Touch"
description: "Reach out to our team for support, quotes, or questions."
date: "2025-01-01"
draft: false
layout: "contact"  # Triggers layouts/page/contact.html
show_sidebar: false
```

**Content**:
```markdown
Optional introductory text before the form.
```

**Template Requirements**:
- Must include `partials/contact-form.html`
- Should display email/phone if provided in site config
- Two-column layout: content/details + form

**Components Used**:
- `partials/contact-form.html`
- `partials/seo.html`

**Schema Type**: `ContactPage`

---

## Pattern: Legal Page

### Purpose (Human)
Terms of Service, Privacy Policy, Cookie Policy, or other legal documentation. Single-column, text-focused, minimal distraction.

### When to Use (Human)
- Privacy Policy (`/privacy/`)
- Terms of Service (`/terms/`)
- Cookie Policy
- Disclaimer pages

### Structure (AI)

**File Location**: `content/legal/privacy-policy.md`

**Template**: `layouts/_default/single.html` (no sidebar)

**Required Front Matter**:
```yaml
title: "Privacy Policy"
seo_title: "Privacy Policy - [Brand Name]"
description: "How we collect, use, and protect your data."
date: "2025-01-01"
lastmod: "2025-01-01"
draft: false
show_sidebar: false
```

**Content Structure**:
```markdown
# Privacy Policy

Last updated: [Date]

## Section 1
Content...

## Section 2
Content...
```

**Notes**:
- Word count can be very long (legal text)
- Must display `lastmod` date prominently
- No featured image needed

**Components Used**:
- `partials/seo.html`

**Schema Type**: `WebPage`

---

## Pattern: Landing Page

### Purpose (Human)
A single-purpose page designed for a campaign, ad, or specific conversion goal. Highly focused, minimal navigation.

### When to Use (Human)
- Ad campaign destinations
- Product launches
- Event registrations
- Lead magnets / downloads

### Structure (AI)

**File Location**: `content/landing/[campaign-name].md`

**Template**: `layouts/landing/single.html` (custom, minimal header/footer)

**Required Front Matter**:
```yaml
title: "Campaign Headline"
seo_title: "Offer - Benefit (50-60 chars)"
description: "Compelling offer description"
draft: false
featured_image: "/images/landing/campaign.jpg"
layout: "landing"

hero:
  headline: "Main Promise"
  subheadline: "Supporting statement"
  cta_text: "Take Action"
  cta_link: "/signup/"

hide_nav: true  # Optional: hide main navigation
hide_footer: true  # Optional: hide footer
```

**Content**: Usually minimal—most content defined in front matter sections.

**Template Features**:
- Streamlined header (logo only, no full nav)
- Multiple CTA buttons
- Focused on single conversion goal

**Schema Type**: `WebPage`

---

## Adding New Patterns

When you identify a new pattern:

1. **Document the purpose** (why this exists)
2. **Define when to use it** (use cases)
3. **Specify the structure**:
   - File location
   - Template used
   - Required front matter
   - Content structure
   - Components used
   - Schema type
4. **Add to this playbook**

Patterns should be **common enough to reuse** (3+ times) but **specific enough to be meaningful**.

---

## Pattern Decision Tree

```
Is it the main landing page?
  → Homepage

Does it have a form?
  → Contact Page

Is it a collection of items?
  → Feed/List Page

Is it long-form educational content?
  → Blog Post

Is it promotional/service-focused?
  → Service/Product Page

Is it legal text?
  → Legal Page

Is it a campaign/conversion-focused?
  → Landing Page
```
