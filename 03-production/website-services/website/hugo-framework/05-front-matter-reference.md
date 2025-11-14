---
title: "Front Matter Reference"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/05-front-matter-reference
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
  - pattern-selection
deliverables:
  - validated-front-matter
  - archetype-templates
tags:
  - hugo
  - front-matter
  - metadata
  - validation
  - data-structure
---

# Front Matter Reference

Complete field definitions, data types, and validation rules for Hugo front matter.

---

## How to Use This Reference

### For Humans
Quick lookup for "What field do I need?" when creating content.

### For AI
Complete specification for validation, archetype generation, and template logic.

---

## Field Categories

1. [Core Content](#core-content-fields) - Required on all pages
2. [SEO & Metadata](#seo--metadata-fields) - Search engine optimization
3. [Imagery](#imagery-fields) - Images and visual content
4. [Taxonomies](#taxonomy-fields) - Categories and tags
5. [Display Control](#display-control-fields) - Template behavior
6. [Schema & Structured Data](#schema-fields) - Rich snippets
7. [Pattern-Specific](#pattern-specific-fields) - Used by specific patterns

---

## Core Content Fields

### `title`
**Type**: String
**Required**: Yes (all pages)
**Purpose**: The primary title of the page. Becomes the `<h1>`.
**Validation**:
- Not empty
- Ideally 40-70 characters
- Should be a clear question or statement

**Example**:
```yaml
title: "How to Build Hugo Sites Faster"
```

**Used In**: All templates
**Used By**: `{{ .Title }}`, SEO partial, schema

---

### `date`
**Type**: Date (ISO 8601 format: `YYYY-MM-DD`)
**Required**: Yes (posts), Optional (static pages)
**Purpose**: Publish date. Controls sorting in lists.
**Validation**: Valid date format

**Example**:
```yaml
date: "2025-11-06"
```

**Used In**: Blog posts, news, time-sensitive content
**Used By**: `{{ .Date }}`, archive pages, RSS feeds

---

### `draft`
**Type**: Boolean
**Required**: Yes
**Default**: `true` (in archetypes)
**Purpose**: Controls whether page appears in production builds.
**Values**: `true` | `false`

**Example**:
```yaml
draft: false
```

**Used In**: All pages
**Hugo Behavior**: `hugo` command ignores drafts; `hugo -D` includes them

---

### `lastmod`
**Type**: Date (ISO 8601)
**Required**: Recommended
**Purpose**: Last modified date. Shows content freshness.
**Validation**: Must be >= `date`

**Example**:
```yaml
lastmod: "2025-11-06"
```

**Used In**: All pages
**Used By**: Schema, SEO (shows search engines content is updated)

---

## SEO & Metadata Fields

### `seo_title`
**Type**: String
**Required**: Yes
**Purpose**: The `<title>` tag for browser tabs and search results.
**Validation**:
- 50-60 characters (optimal)
- Max 70 characters (hard limit)
- Should include primary keyword

**Example**:
```yaml
seo_title: "Hugo Tutorial: Build Sites 10x Faster"
```

**Used In**: All pages
**Used By**: `<title>` tag, Open Graph, Twitter Cards

**Fallback**: If not provided, uses `title`

---

### `description`
**Type**: String
**Required**: Yes
**Purpose**: Meta description for search results. **Must contain the 18-token core answer phrase.**
**Validation**:
- 150-160 characters (optimal)
- Max 320 characters
- Must directly answer page's core question

**Example**:
```yaml
description: "Hugo is a fast static site generator that builds websites from Markdown files in milliseconds, offering speed and simplicity for developers."
```

**Used In**: All pages
**Used By**: `<meta name="description">`, Open Graph, Twitter Cards, AI summaries

**Critical**: This is your AEO answer phrase. First sentence of page content should match.

---

### `keywords`
**Type**: Array of strings
**Required**: No
**Purpose**: Internal site search and taxonomy. **Not used for SEO** (search engines ignore meta keywords).
**Note**: Only use if you have internal search functionality.

**Example**:
```yaml
keywords: ["hugo", "static-site", "jamstack"]
```

---

## Imagery Fields

### `featured_image`
**Type**: String (relative path)
**Required**: Recommended (required for posts)
**Purpose**: Primary image for the page. Used for:
- Open Graph (social sharing)
- Twitter Cards
- Feed cards
- Page headers

**Validation**:
- Must be a valid image path
- Recommended: 1200x630px (optimal for Open Graph)
- Must exist in `static/` or `assets/`

**Example**:
```yaml
featured_image: "/images/posts/hugo-tutorial.jpg"
```

**Used In**: All public-facing pages
**Used By**: SEO partial, feed-card partial, social sharing

---

### `featured_image_alt`
**Type**: String
**Required**: Recommended (accessibility)
**Purpose**: Alt text for the featured image.
**Validation**: Descriptive, not generic

**Example**:
```yaml
featured_image_alt: "Developer working on Hugo site with terminal and code editor"
```

**Used By**: `<img alt="">`, Open Graph image alt, Twitter image alt

**Fallback**: If not provided, uses `title`

---

## Taxonomy Fields

### `categories`
**Type**: Array of strings
**Required**: Optional (recommended for posts)
**Purpose**: Primary classification. Typically broad topics.
**Best Practice**: 1-2 per post (keep focused)

**Example**:
```yaml
categories: ["Web Development", "Tutorials"]
```

**Used In**: Blog posts, portfolio items
**Used By**: Sidebar, taxonomy pages (`/categories/web-development/`)

---

### `tags`
**Type**: Array of strings
**Required**: Optional
**Purpose**: Detailed keywords. More specific than categories.
**Best Practice**: 3-5 per post

**Example**:
```yaml
tags: ["hugo", "jamstack", "static-site-generator", "golang"]
```

**Used In**: Blog posts
**Used By**: Sidebar, taxonomy pages (`/tags/hugo/`)

---

## Display Control Fields

### `layout`
**Type**: String
**Required**: Optional
**Purpose**: Override default template selection.
**Values**: Any template name (without extension)

**Example**:
```yaml
layout: "contact"  # Uses layouts/page/contact.html
```

**Used In**: Pages requiring custom layouts
**Hugo Behavior**: If not set, uses default template hierarchy

**Common Values**:
- `"single"` - Default single page
- `"contact"` - Contact page
- `"landing"` - Landing page

---

### `show_sidebar`
**Type**: Boolean
**Required**: Optional
**Default**: Context-dependent
**Purpose**: Controls sidebar visibility in single.html template.

**Example**:
```yaml
show_sidebar: true   # For posts
show_sidebar: false  # For legal pages, service pages
```

**Used In**: Single page template
**Used By**: `layouts/_default/single.html`

---

### `show_toc`
**Type**: Boolean
**Required**: Optional
**Default**: `false`
**Purpose**: Show Table of Contents in sidebar.
**Best Practice**: Use for long-form content (2000+ words)

**Example**:
```yaml
show_toc: true
```

**Used In**: Blog posts with sidebar
**Used By**: `partials/sidebar.html`

**Note**: Only works if `show_sidebar: true`

---

### `paginate`
**Type**: Integer
**Required**: Optional (only for `_index.md` list pages)
**Purpose**: Number of items per page on list views.
**Common Values**: 6, 9, 12 (multiples of grid columns)

**Example**:
```yaml
paginate: 9
```

**Used In**: `_index.md` files for sections
**Used By**: List templates

---

### `feed_layout`
**Type**: String
**Required**: Optional
**Default**: `"grid"`
**Purpose**: Controls list page layout style.
**Values**: `"grid"` | `"list"`

**Example**:
```yaml
feed_layout: "grid"
```

**Used In**: Section `_index.md` files
**Used By**: List template CSS classes

---

## Schema Fields

### `schema.type`
**Type**: String
**Required**: Optional
**Default**: Auto-determined by template
**Purpose**: Override default Schema.org type.
**Common Values**:
- `"Article"` (blog posts)
- `"WebPage"` (default pages)
- `"FAQPage"` (FAQ content)
- `"Service"` (service pages)
- `"Product"` (product pages)
- `"Recipe"` (recipe content)

**Example**:
```yaml
schema:
  type: "FAQPage"
```

**Used In**: All pages
**Used By**: `partials/schema.html`

---

### `author`
**Type**: String
**Required**: Optional (recommended for posts)
**Purpose**: Content author name. Used in Schema and sidebar.

**Example**:
```yaml
author: "Jane Doe"
```

**Used In**: Blog posts, articles
**Used By**: Sidebar, Schema (Person), meta byline

---

## Pattern-Specific Fields

### Homepage Fields (`hero`)

**Type**: Object
**Required**: For homepage pattern
**Purpose**: Hero section content

**Example**:
```yaml
hero:
  title: "Build Faster Websites"
  subtitle: "Hugo-powered sites deploy in seconds"
  cta_text: "Get Started"
  cta_link: "/contact/"
```

**Fields**:
- `hero.title` (string) - Main headline
- `hero.subtitle` (string) - Supporting text
- `hero.cta_text` (string) - Button text
- `hero.cta_link` (string) - Button URL

**Used In**: Homepage (`layouts/index.html`)

---

### Landing Page Fields

#### `hide_nav`
**Type**: Boolean
**Default**: `false`
**Purpose**: Hide main navigation for focused landing pages.

**Example**:
```yaml
hide_nav: true
```

**Used In**: Landing pages
**Used By**: `layouts/landing/single.html`

---

#### `hide_footer`
**Type**: Boolean
**Default**: `false`
**Purpose**: Hide footer for minimal landing pages.

**Example**:
```yaml
hide_footer: true
```

**Used In**: Landing pages
**Used By**: `layouts/landing/single.html`

---

## Open Graph Override Fields

### `og_title`
**Type**: String
**Required**: No
**Purpose**: Override title for social media sharing.
**Use Case**: When you want social share title to differ from page title.

**Example**:
```yaml
og_title: "🚀 Build Sites 10x Faster with Hugo"
```

**Fallback**: Uses `seo_title` if not provided

---

### `og_description`
**Type**: String
**Required**: No
**Purpose**: Override description for social media sharing.

**Example**:
```yaml
og_description: "The fastest static site generator, now with AI optimization"
```

**Fallback**: Uses `description` if not provided

---

## Validation Rules

### Required Field Matrix

| Field | Homepage | Blog Post | Service Page | Feed Index | Contact | Legal |
|-------|----------|-----------|--------------|------------|---------|-------|
| `title` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `seo_title` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `description` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `date` | ⚠️ | ✅ | ⚠️ | ⚠️ | ⚠️ | ✅ |
| `draft` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `featured_image` | ⚠️ | ✅ | ⚠️ | ⚠️ | ❌ | ❌ |
| `author` | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| `categories` | ❌ | ⚠️ | ❌ | ❌ | ❌ | ❌ |
| `layout` | ❌ | ❌ | ⚠️ | ❌ | ✅ | ❌ |

Legend:
- ✅ Required
- ⚠️ Recommended
- ❌ Not applicable

---

## Archetype Templates

### Default Archetype (`archetypes/default.md`)

```yaml
---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
seo_title: ""
description: ""
date: "{{ .Date }}"
lastmod: "{{ .Date }}"
draft: true
featured_image: ""
featured_image_alt: ""
---
```

### Post Archetype (`archetypes/post.md`)

```yaml
---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
seo_title: ""
description: ""
date: "{{ .Date }}"
lastmod: "{{ .Date }}"
draft: true
author: ""
featured_image: ""
featured_image_alt: ""
categories: []
tags: []
show_sidebar: true
show_toc: false
schema:
  type: "Article"
---
```

---

## Best Practices

### For Content Creators

1. **Always fill required fields** - Templates depend on them
2. **Write description first** - It forces you to clarify the core answer
3. **Keep seo_title under 60 chars** - Truncation hurts click-through
4. **Use descriptive alt text** - Accessibility and SEO
5. **Update lastmod** - Shows content freshness

### For AI Assistants

1. **Validate field types** - Dates must be ISO 8601, booleans must be true/false
2. **Check required fields by pattern** - Use the validation matrix
3. **Auto-generate when possible** - `date`, `lastmod`, title from filename
4. **Warn on long values** - Flag seo_title > 60 chars
5. **Suggest defaults** - Based on pattern being created

---

## Adding New Fields

When adding a new front matter field:

1. **Document the purpose** - Why does this exist?
2. **Define the type** - String, boolean, array, object?
3. **Set validation rules** - Required? Max length? Format?
4. **Specify where used** - Which templates/partials read it?
5. **Provide examples** - Show real usage
6. **Update archetypes** - Add to relevant archetype files
7. **Update this reference** - Keep documentation current

---

## Field Naming Conventions

- Use `snake_case` for multi-word fields (`featured_image`, not `featuredImage`)
- Be semantic (`seo_title`, not `title2`)
- Use boolean prefixes (`show_sidebar`, not `sidebar`)
- Avoid abbreviations unless standard (`seo` is fine, `desc` is not)
