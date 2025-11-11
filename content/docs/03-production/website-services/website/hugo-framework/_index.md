# R7 Hugo Framework Documentation

**A standardized, AI-friendly Hugo development system for repeatable, AEO-optimized websites.**

---

## Quick Start for Humans

**Starting a new project?**
1. Start with **[Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md)** - Gather requirements and create designs (happens BEFORE Hugo)
2. Complete **[AEO Copywriting](/docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting.md)** - Transform interviews into optimized content
3. Read **[Core Principles](/docs/03-production/website-services/website/hugo-framework/02-core-principles.md)** - The "why" behind our approach (5 min read)
4. Follow **[Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md)** - Step-by-step Hugo implementation
5. Reference as needed: **[Pattern Playbook](/docs/03-production/website-services/website/hugo-framework/03-pattern-playbook.md)**, **[Component System](/docs/03-production/website-services/website/hugo-framework/04-component-system.md)**, **[Front Matter Reference](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md)**

**Adding to existing project?**
1. Browse **[Pattern Playbook](/docs/03-production/website-services/website/hugo-framework/03-pattern-playbook.md)** - Choose the pattern you need
2. Reference **[Component System](/docs/03-production/website-services/website/hugo-framework/04-component-system.md)** - Visual/CSS guidelines
3. Check **[Front Matter Reference](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md)** - Required fields

## Quick Start for AI

**Full project workflow**:
1. Load **[Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md)** for pre-Hugo phase
2. Load **[AEO Copywriting](/docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting.md)** for content optimization
3. Load **[Core Principles](/docs/03-production/website-services/website/hugo-framework/02-core-principles.md)** for context
4. Follow **[Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md)** for implementation sequence
5. Reference **[Pattern Playbook](/docs/03-production/website-services/website/hugo-framework/03-pattern-playbook.md)** for implementation specs
6. Follow **[Front Matter Schema](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md)** for data structure
7. Use **[Component System](/docs/03-production/website-services/website/hugo-framework/04-component-system.md)** for styling conventions

---

## Documentation Structure

### [00 - Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md)
The client-facing design process that happens BEFORE Hugo implementation.

**For**: Gathering requirements, creating designs, building component libraries
**When**: Starting a new project (pre-development phase)
**Duration**: 1-2 weeks

### [01 - AEO Copywriting](/docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting.md)
Transform client interviews into AEO-optimized copy using the "One Page, One Question" framework.

**For**: Content creation and optimization
**When**: After designs are approved, before Hugo implementation
**Duration**: Varies by project size

### [02 - Core Principles](/docs/03-production/website-services/website/hugo-framework/02-core-principles.md)
The foundational philosophy and rules. Short, memorable, human-focused.

**For**: Understanding the "why"
**When**: Starting a project, onboarding, making strategic decisions

### [03 - Pattern Playbook](/docs/03-production/website-services/website/hugo-framework/03-pattern-playbook.md)
Named content patterns with purpose and implementation details.

**For**: Choosing the right approach for each page type
**When**: Planning site structure, creating new content types

### [04 - Component Design System](/docs/03-production/website-services/website/hugo-framework/04-component-system.md)
Visual components, CSS architecture, and styling conventions.

**For**: Consistent visual implementation
**When**: Building templates, styling components

### [05 - Front Matter Reference](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md)
Complete front matter field definitions and validation rules.

**For**: Data structure reference
**When**: Creating archetypes, debugging templates

### [06 - Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md)
Step-by-step process for building a new Hugo site with this framework.

**For**: Project execution
**When**: Starting a new site, onboarding team members

---

## Philosophy in One Sentence

**We build focused, answer-first websites where every page solves one problem, uses semantic structure for both humans and AI Answer Engines, and follows repeatable patterns for speed and consistency.**

---

## What is AEO?

**Answer Engine Optimization (AEO)** is the strategy of optimizing content to be directly understood and used by AI-powered search tools (like Google's SGE, Perplexity, ChatGPT search).

Unlike traditional SEO (ranking a link), AEO focuses on having your content selected as the definitive answer itself.

This framework integrates AEO principles throughout the entire process—from copywriting to technical implementation.

---

## Document Metadata

Every document in this framework includes structured YAML front matter for improved scannability and RAG retrieval.

### What You'll See

Each document starts with metadata like this:

```yaml
---
title: "Document Title"
phase: design | content | foundation | development
audience: human | ai | both
duration: "time estimate"
type: process-guide | reference | philosophy
effort: low | medium | high
human_interaction: none | input-required | review-required | collaborative
sequence_order: 1 | 2 | 3 | null
parallelizable: true | false
ai_role: understand | execute | reference
requires: [prerequisites]
deliverables: [what-it-produces]
tags: [relevant-keywords]
---
```

### Why This Helps

**For Humans**:
- Quick context at a glance
- Understand time commitment and complexity
- See when human involvement is needed (QA, decisions, approvals)
- Know task sequencing and dependencies
- Navigate via related docs

**For AI/RAG Systems**:
- Better context preservation in chunks
- Filterable by phase, type, audience, effort
- Dependency graph construction
- Improved semantic search
- Understand parallelization opportunities

**For AI Workflow Planning**:
- **`effort`**: Understand computational complexity (not calendar time)
- **`human_interaction`**: Know when to pause for human input/QA/approval
- **`sequence_order`**: Enforce correct task ordering (prevents skipping prerequisites)
- **`parallelizable`**: Optimize by running independent tasks concurrently
- **`duration`**: Estimate real-world timeline (includes human dependencies)

**Human-in-the-Loop Enforcement**:
AI assistants must ALWAYS pause for human judgment when `human_interaction` is set. This ensures quality control and keeps humans involved in subjective decisions, QA checkpoints, and final approvals.

### Full Schema Documentation

See **[METADATA-SCHEMA.md](/docs/03-production/website-services/website/hugo-framework/METADATA-SCHEMA.md)** for complete field definitions and controlled vocabularies.

---

## Version & Updates

- **Current Version**: 2.2.0
- **Last Updated**: 2025-11-06
- **Changelog**:
- **Based on**: Gemini design advice + AEO copywriting process + Hugo best practices
