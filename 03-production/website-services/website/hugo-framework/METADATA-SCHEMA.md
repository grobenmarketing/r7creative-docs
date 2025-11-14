# Metadata Schema Reference

**Front matter fields for all R7 Hugo Framework documents.**

---

## Purpose

Every document in this framework includes structured YAML front matter to:
- Provide quick context for humans scanning documents
- Help RAG systems understand document purpose and relationships
- Enable AI assistants to sequence tasks and estimate effort
- Make the framework self-documenting

---

## Field Definitions

### Essential Fields (Always Include)

#### `title`
**Type**: String
**Purpose**: Human-readable document name
**Example**: `"AEO Copywriting Guide"`

#### `phase`
**Type**: String (controlled vocabulary)
**Purpose**: Where this fits in the project workflow
**Valid Values**:
- `design` - Pre-development, client-facing design work
- `content` - Content creation and optimization
- `foundation` - Core philosophy and principles
- `development` - Hugo implementation and coding
- `deployment` - Launching and maintaining sites

**Example**: `phase: content`

#### `audience`
**Type**: String (controlled vocabulary)
**Purpose**: Primary intended reader
**Valid Values**:
- `human` - For human reading and decision-making
- `ai` - For AI execution or processing
- `both` - Useful for both humans and AI

**Example**: `audience: both`

#### `duration`
**Type**: String
**Purpose**: Time commitment expected
**Format**: Free-form but consistent
**Examples**:
- `"1-2 weeks"` - Process that takes weeks
- `"3-5 days"` - Multi-day effort
- `"30-60 min"` - Short task
- `"5-10 min"` - Quick read
- `"reference"` - Ongoing reference, no fixed duration
- `"varies"` - Depends on project scope

#### `type`
**Type**: String (controlled vocabulary)
**Purpose**: Document category
**Valid Values**:
- `process-guide` - Step-by-step instructions to execute
- `reference` - Lookup documentation (specifications, field definitions)
- `checklist` - Validation or completion checklist
- `philosophy` - Conceptual/strategic principles
- `template` - Reusable code or content template

**Example**: `type: process-guide`

#### `effort`
**Type**: String (controlled vocabulary)
**Purpose**: Computational/cognitive complexity for AI execution
**Valid Values**:
- `low` - Simple reads, lookups, template filling, reference checks
- `medium` - Content generation, optimization, multi-step logic, pattern application
- `high` - Complex system design, multiple iterations, architectural decisions

**Example**: `effort: medium`

**Why this matters**: Helps AI understand actual work complexity vs. calendar time. A "1-2 week" process might be `effort: high` due to complexity, not because AI needs weeks to compute.

#### `human_interaction`
**Type**: String (controlled vocabulary)
**Purpose**: Level of human involvement required - critical for keeping humans in the loop for QA and subjective decisions
**Valid Values**:
- `none` - AI completes autonomously (pure reference docs)
- `input-required` - Human must provide info first (interview, assets, requirements)
- `review-required` - Human must approve output at end (design sign-off, content QA, deployment approval)
- `collaborative` - Ongoing back-and-forth throughout process (discovery, design iteration, strategy)

**Example**: `human_interaction: review-required`

**Why this matters**: Ensures AI knows when to pause for human judgment, QA, and subjective decisions. This is the framework's "human-in-the-loop" enforcement mechanism.

#### `sequence_order`
**Type**: Integer or null
**Purpose**: Strict workflow position - enforces dependencies
**Valid Values**:
- `1, 2, 3...` - Must complete in this exact order
- `null` - Reference doc, use anytime, no strict ordering

**Example**: `sequence_order: 2`

**Why this matters**: Prevents AI from skipping prerequisites. For example, can't start Hugo implementation (sequence_order: 3) without completing design (sequence_order: 1) and content (sequence_order: 2).

#### `parallelizable`
**Type**: Boolean
**Purpose**: Can this task run alongside other tasks?
**Valid Values**:
- `true` - Independent work (writing different pages, referencing docs, parallel component builds)
- `false` - Sequential dependency (can't design homepage while doing discovery, blocks other work)

**Example**: `parallelizable: true`

**Why this matters**: Enables AI to optimize workflow by running independent tasks concurrently. Multiple pages can be written simultaneously, but design must complete before development starts.

#### `tags`
**Type**: Array of strings
**Purpose**: Keywords for RAG search and filtering
**Guidelines**:
- Use 3-7 relevant tags
- Keep lowercase with hyphens
- Focus on key concepts and use cases

**Example**:
```yaml
tags:
  - optimization
  - content-strategy
  - one-page-one-question
  - answer-engines
```

---

### Optional Fields (Use When Helpful)

#### `ai_role`
**Type**: String (controlled vocabulary)
**Purpose**: How AI assistants should use this document
**Valid Values**:
- `understand` - Read for context, don't execute
- `execute` - Follow steps and implement
- `reference` - Look up information as needed

**Example**: `ai_role: execute`

#### `requires`
**Type**: Array of strings
**Purpose**: Prerequisites needed before using this doc
**Format**: Use kebab-case identifiers
**Examples**:
```yaml
requires:
  - client-availability
  - approved-designs
  - interview-transcript
```

#### `outputs`
**Type**: Array of strings
**Purpose**: What this process/document produces
**Format**: Use kebab-case identifiers
**Examples**:
```yaml
deliverables:
  - aeo-optimized-content
  - core-answer-phrases
  - front-matter
```

#### `related_docs`
**Type**: Array of strings
**Purpose**: Cross-references to other framework docs
**Format**: Document IDs (00, 01, 02, etc.) or full filenames
**Examples**:
```yaml
```

---

## Controlled Vocabularies

### Phase Values
| Value | Meaning | Typical Docs |
|-------|---------|--------------|
| `design` | Client-facing design and discovery | 00-design-discovery |
| `content` | Content creation and optimization | 01-aeo-copywriting |
| `foundation` | Core principles and philosophy | 02-core-principles |
| `development` | Hugo implementation | 03, 04, 05, 06 |
| `deployment` | Launch and maintenance | (future docs) |

### Audience Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `human` | Human reading and decision-making | Client-facing processes, strategy |
| `ai` | AI execution or processing | Pure implementation specs |
| `both` | Useful for both | Most technical references |

### Type Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `process-guide` | Step-by-step instructions | Workflow, implementation guides |
| `reference` | Lookup documentation | Specs, field definitions, patterns |
| `checklist` | Validation lists | Quality checks, completeness |
| `philosophy` | Conceptual principles | Core principles, strategy |
| `template` | Reusable patterns | Code templates, content samples |

### Effort Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `low` | Simple, quick tasks | Reading, lookups, references, template filling |
| `medium` | Moderate complexity | Content generation, optimization, pattern application |
| `high` | Complex, multi-step | System design, architecture, iterative refinement |

### Human Interaction Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `none` | Fully autonomous | Pure reference docs, lookups |
| `input-required` | Need human data first | Interviews, asset collection, requirements |
| `review-required` | Need approval at end | QA checkpoints, design sign-off, deployment approval |
| `collaborative` | Ongoing involvement | Discovery, strategy, iterative design |

### Sequence Order Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `1, 2, 3...` | Strict ordering | Process guides with dependencies |
| `null` | No ordering | Reference docs, supporting materials |

### Parallelizable Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `true` | Can run alongside others | Independent tasks, reference docs |
| `false` | Must complete first | Blocking processes, dependencies |

### AI Role Values
| Value | Meaning | Use When |
|-------|---------|----------|
| `understand` | Read for context | Strategy docs, principles |
| `execute` | Follow and implement | Workflows, processes |
| `reference` | Look up as needed | Specifications, field definitions |

---

## Standard Tags by Category

### By Workflow Phase
- `pre-development`
- `design-system`
- `content-strategy`
- `implementation`
- `deployment`

### By Content Focus
- `client-facing`
- `optimization`
- `aeo`
- `hugo`
- `patterns`
- `components`
- `metadata`

### By Methodology
- `one-page-one-question`
- `answer-first`
- `component-based`
- `homepage-first`
- `semantic-html`

### By Technical Area
- `css`
- `bem`
- `front-matter`
- `templates`
- `styling`
- `accessibility`

### By Purpose
- `philosophy`
- `reference`
- `workflow`
- `validation`
- `translation`

---

## Complete Example

```yaml
---
title: "AEO Copywriting Guide"
phase: content
audience: both
duration: varies
type: process-guide
effort: medium
human_interaction: review-required
sequence_order: 2
parallelizable: true
ai_role: execute
requires:
  - client-interview-transcript
  - approved-designs
deliverables:
  - aeo-optimized-content
  - core-answer-phrases
  - structured-markdown
tags:
  - optimization
  - content-strategy
  - one-page-one-question
  - answer-engines
  - translation
---

# AEO Copywriting Guide

Content begins here...
```

---

## Usage Guidelines

### For Document Authors

1. **Always include essential fields** - These are required
2. **Use controlled vocabulary** - Don't invent new phase/type values
3. **Be consistent with duration format** - Match existing patterns
4. **Choose 3-7 relevant tags** - Not too few, not too many
5. **Update related_docs** - Keep cross-references current

### For AI Assistants

**When reading documents**:
- Check `ai_role` to understand how to use the doc
- Check `effort` to estimate computational complexity
- Check `human_interaction` to know when to pause for humans
- Check `requires` to know what prerequisites are needed
- Check `phase` to understand workflow position
- Check `outputs` to know what this produces

**When planning projects**:
- Sort by `sequence_order` to get correct task ordering
- Filter by `phase` to group workflow stages
- Check `human_interaction` to identify QA checkpoints
- Use `parallelizable` to optimize concurrent execution
- Check `effort` to understand work complexity
- Use `duration` for human timeline estimates (not AI execution time)
- Build dependency graph from `requires` and `outputs`

**Human-in-the-loop enforcement**:
- ALWAYS pause when `human_interaction` is `input-required`, `review-required`, or `collaborative`
- NEVER skip human review steps
- Present work for QA at specified checkpoints
- Wait for approval before proceeding to next phase

### For Humans

**Quick scanning**:
- Read `title` + `phase` + `duration` for instant context
- Check `tags` to understand key concepts
- Check `related_docs` to find connected information

**Project planning**:
- Filter by `audience: human` for client-facing tasks
- Group by `phase` to organize workflow
- Sum durations for time estimates

---

## Maintenance

### When Adding New Documents

1. Copy front matter template from existing doc
2. Fill in all essential fields
3. Add optional fields where relevant
4. Use existing controlled vocabulary values
5. Add appropriate tags (3-7)
6. Link related documents

### When Updating Controlled Vocabulary

If you need to add a new valid value:
1. Add it to this schema document first
2. Document what it means and when to use it
3. Update relevant documents
4. Keep consistency across the framework

---

## Benefits

### For RAG Systems
- Chunks include structured metadata
- Can filter by phase, type, audience
- Relationships preserved in embeddings
- Better context for retrieval

### For AI Agents
- Can sequence tasks properly (`sequence_order`)
- Understands prerequisites (`requires`)
- Estimates computational effort (`effort`)
- Estimates human timelines (`duration`)
- Identifies human checkpoints (`human_interaction`)
- Optimizes parallel execution (`parallelizable`)
- Knows execution vs. reference docs (`ai_role`)
- Enforces human-in-the-loop workflow

### For Humans
- Instant context at top of each doc
- Clear workflow positioning
- Quick cross-reference navigation
- Better scannability

---

## Version History

- **v1.1** (2025-11-06): Added AI workflow optimization fields
- **v1.0** (2025-11-06): Initial metadata schema
