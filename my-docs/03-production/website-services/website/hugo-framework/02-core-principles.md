---
title: "Core Principles"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/02-core-principles
phase: foundation
audience: human
duration: "5-10 min"
type: philosophy
effort: low
human_interaction: none
sequence_order: null
parallelizable: true
ai_role: understand
requires: []
deliverables:
  - strategic-context
  - aeo-understanding
tags:
  - philosophy
  - aeo
  - one-page-one-question
  - answer-first
  - semantic-html
---

# Core Principles

The foundational philosophy for R7 Hugo Framework.

---

## The Big Idea

**Modern search is changing from "find a link" to "get an answer."**

Our framework builds websites that excel in both traditional SEO and Answer Engine Optimization (AEO) by being clear, focused, and structured.

---

## 7 Core Principles

### 1. One Page, One Question
Every page answers exactly one question comprehensively.

**Why**: AI models and search engines reward definitive, focused answers. If you need to answer a second question, create a second page and link them.

**Example**: Don't create "Everything About Hugo." Create "What is Hugo?", "How to Install Hugo?", "Hugo vs Jekyll?" as separate pages.

---

### 2. Answer First, Always
The core answer appears immediately—in the meta description AND the first paragraph.

**Why**: AI scrapers and impatient humans both scan for the answer first. Put it up front.

**The 18-Token Rule**: Your "core answer phrase" should be 18-25 words (one clear sentence) that directly answers the page's question.

**Example**:
```
BAD: "In this comprehensive guide, we'll explore..."
GOOD: "Hugo is a fast, open-source static site generator written in Go that builds websites from Markdown files in milliseconds."
```

---

### 3. Headings Create Outlines, Not Style
Use heading tags (`<h1>`, `<h2>`, `<h3>`) to create logical document structure, never for visual design.

**The Hierarchy**:
- **One `<h1>`** per page = The main question/title
- **`<h2>` tags** = Main sections (chapters)
- **`<h3>` tags** = Sub-sections within an `<h2>`
- **`<h4>`-`<h6>`** = Rarely needed

**Why**: Search engines and AI models use headings to understand your content's structure. A broken hierarchy confuses them.

---

### 4. Topic Completion Over Word Count
There is no minimum word count. Write exactly enough to answer the question completely.

**Why**: "Rich content" used to mean "long content." Now it means "complete content."

**Examples**:
- A privacy policy might be 2,000 words
- "What is the capital of France?" might be 150 words
- Both are valid if they fully answer their question

---

### 5. Metadata is Not Optional
Every page needs:
- `title` (the `<h1>`)
- `seo_title` (50-60 characters for search results)
- `description` (150-160 characters, contains your core answer phrase)
- `featured_image` (for social sharing)

**Why**: This data powers search results, social media cards, and AI summaries. Skip it and you're invisible.

---

### 6. Structure is Reusable, Content is Unique
We build with patterns (templates, components, archetypes) so structure never needs reinventing.

**Why**: Consistency = speed. When every blog post uses the same structure, you spend time on content, not layout decisions.

**What this means**:
- Templates are standardized
- Components are reusable
- Only the content and styling vary per project

---

### 7. Semantic HTML, Accessible Always
Use the right HTML elements for their intended purpose. Make everything keyboard and screen-reader friendly.

**Why**: Accessibility isn't extra work—it's correct implementation. Semantic HTML also helps AI understand content context.

**Examples**:
- Use `<article>` for posts, not `<div class="post">`
- Use `<nav>` for navigation, not `<div id="menu">`
- Use `<button>` for actions, not `<div onclick="...">`

---

## In Practice

These principles inform every decision in this framework:
- **Front matter schema** → Built for complete metadata (Principle 5)
- **Pattern playbook** → Reusable structures (Principle 6)
- **Single.html template** → Proper heading hierarchy (Principle 3)
- **Shortcodes** → Semantic components (Principle 7)

---

## Meta-Principle: Documentation Matters

If it's not documented, it doesn't exist. Every pattern, component, and decision is recorded so both humans and AI can extend the system consistently.

**This document is part of that commitment.**
