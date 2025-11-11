---
title: "Design & Discovery Phase"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/00-design-discovery
phase: design
audience: human
duration: "1-2 weeks"
type: process-guide
effort: high
human_interaction: collaborative
sequence_order: 1
parallelizable: false
ai_role: understand
requires:
  - client-availability
  - brand-assets
deliverables:
  - approved-designs
  - component-gallery
  - design-tokens
tags:
  - client-facing
  - pre-development
  - design-system
  - component-based
  - homepage-first
---

# Design & Discovery Phase

**The client-facing design process that happens BEFORE Hugo implementation.**

---

## Overview

This phase focuses on gathering requirements, creating design direction, and building a component-based design system with the client. **This is all done before any Hugo code is written.**

**Key Principle**: Design the homepage first, establish the visual system, then systematize into reusable components.

**Goal**: Walk away with client-approved designs and a complete component library that can be translated into Hugo templates.

**Duration**: 1-2 weeks (depending on client responsiveness)

---

## The Component-Based Approach

We build websites using a **"kit of parts"** methodology:

1. **Gather** brand assets and requirements
2. **Design** the homepage (establishes visual language)
3. **Systematize** by extracting components into a gallery
4. **Assemble** remaining pages from the component library
5. **Review** and get final approval

**Why this works**:
- Homepage design gives clients something tangible to approve
- Component extraction ensures consistency
- Assembly from components is fast and predictable
- Changes to components propagate everywhere

---

## Final Deliverables

By the end of this phase, you will have:

**✅ Design Assets**:
- Approved homepage design
- Complete component gallery
- 7 page templates (designs, not code)

**✅ Page Templates**:
1. Component Gallery (reference document)
2. Home Page
3. Inner Page 1 (About Us / Services)
4. Inner Page 2 (Our Process / Methodology)
5. Contact Page
6. Feed/Card Page (Blog / Portfolio)
7. Single Post Page (Blog Article / Portfolio Detail)

**✅ Specifications Ready for Hugo**:
- Color palette
- Typography scale
- Component inventory
- Content structure

---

## Step 1: Discovery & Brand Gathering

**Goal**: Collect all assets and direction needed to design effectively.

### Client Communication

*"Before we design anything, we need to establish the foundational elements that will define your site's look and feel. This ensures we're building on your existing brand identity."*

### Deliverables Checklist

Request these from the client:

#### ✅ Brand Assets
- [ ] Logo files (SVG preferred, PNG at high resolution)
- [ ] Logo variations (full logo, icon mark, horizontal/vertical)
- [ ] Official brand color hex codes (primary, secondary, accent)
- [ ] Brand fonts (or font preferences)
- [ ] Brand guidelines document (if exists)

#### ✅ Visual Direction & Inspiration
- [ ] 3-5 websites they like (and what specifically they like about each)
- [ ] Adjectives describing desired feel (e.g., "professional," "playful," "minimal")
- [ ] Competitive sites (what to avoid, what to match)
- [ ] Any existing brand imagery or photography library

#### ✅ Content & Strategy
- [ ] Key headline for homepage
- [ ] Value proposition (what makes them unique)
- [ ] Primary call-to-action (what should visitors do?)
- [ ] Target audience description
- [ ] Site goals (lead generation, e-commerce, information, etc.)

#### ✅ Technical Requirements
- [ ] Required pages/sections
- [ ] Forms needed (contact, quote request, etc.)
- [ ] Third-party integrations (CRM, email marketing, etc.)
- [ ] Special functionality (calculators, booking, etc.)

### Discovery Call Questions

Use these to extract critical information:

**Brand & Identity**:
- "If your brand were a person, how would you describe their personality?"
- "What should visitors feel when they land on your site?"
- "What are the 3 words you want associated with your brand?"

**Audience & Goals**:
- "Who is your ideal visitor?"
- "What's the #1 action you want visitors to take?"
- "How do visitors currently find you?"

**Content & Structure**:
- "What's the one thing visitors must understand about your business?"
- "What questions do your customers always ask?"
- "What pages are absolutely essential?"

**Design Preferences**:
- "Show me 3 sites you love. What specifically do you like?"
- "Show me 3 sites you hate. What turns you off?"
- "Are there any design elements from competitors you want to match or avoid?"

### Organize Assets

Create a project folder structure:

```
[client-name]-discovery/
├── brand/
│   ├── logos/
│   ├── colors.txt
│   └── fonts/
├── inspiration/
│   ├── screenshots/
│   └── notes.md
├── content/
│   ├── homepage-copy.md
│   └── about-copy.md
└── requirements.md
```

### Output Document

Create a **Creative Brief** documenting:
- Brand overview
- Target audience
- Site goals
- Visual direction (with inspiration references)
- Required pages and features
- Content outline

**⏱ Phase Duration**: 3-5 days (including client response time)

---

## Step 2: Create the Home Page Design

**Goal**: Design the homepage as a "living prototype" that establishes the entire visual system.

### Why Homepage First?

The homepage is:
- The most important page (first impression)
- The most component-rich (hero, CTA, cards, features)
- The perfect design prototype
- What clients can most easily evaluate

**By designing the homepage, you're actually designing the entire component library in context.**

### Client Communication

*"Using the assets and direction you provided, I will now design the Home Page. This page establishes the overall look and feel and contains the first versions of our most critical components (navigation, buttons, hero sections, content grids). Once you approve this, we'll use it to build out the rest of the system efficiently."*

### Homepage Structure

Use this proven structure:

1. **Navigation** (Desktop + Mobile versions)
2. **Hero Section** (Headline, subheadline, CTA, image/video)
3. **Value Proposition Section** (3-4 key benefits with icons)
4. **Social Proof** (Client logos, testimonial, or stats)
5. **Feature/Service Highlight** (Detailed look at offerings)
6. **How It Works / Process** (3-5 steps)
7. **Final CTA Block** (Strong call-to-action before footer)
8. **Footer** (Links, contact, social, copyright)

### Design Deliverables

Create in your preferred tool (Figma, Adobe XD, etc.):

- [ ] Desktop version (1440px width)
- [ ] Tablet version (768px width)
- [ ] Mobile version (375px width)
- [ ] Component states (button hover, menu open, etc.)

### Elements to Define

As you design the homepage, explicitly define:

#### Typography System
- H1, H2, H3, H4, H5, H6 (sizes, weights, line-heights)
- Body text (size, line-height, weight)
- Lead paragraph (larger intro text)
- Button text
- Navigation links

#### Color Palette
- Primary color (main brand color)
- Secondary color (supporting brand color)
- Accent color (calls-to-action, highlights)
- Success (form success, positive indicators)
- Warning (caution messages)
- Error (form errors, alerts)
- Neutrals (5-7 shades of gray for text, borders, backgrounds)
- Background colors (white, light gray, dark sections)

#### Spacing Scale
Define consistent spacing units:
- Extra small: 8px
- Small: 16px
- Medium: 24px
- Large: 32px
- Extra large: 48px
- 2X large: 64px
- 3X large: 96px

(Adjust values to your design, but keep them consistent)

#### Interactive States
For all clickable elements:
- Default state
- Hover state
- Active/pressed state
- Disabled state
- Focus state (for accessibility)

### Client Review

Present with this structure:

1. **Show in context**: Full homepage scrolled through
2. **Explain the strategy**: Why each section exists
3. **Highlight key components**: "This button style will be used throughout"
4. **Request specific feedback**: "Does this hero section capture your value proposition?"
5. **Set expectations**: "Once approved, we'll extract these components and build the rest of the site"

### Revision Process

Expect 1-2 revision rounds. Common feedback areas:
- Color adjustments
- Font size tweaks
- Image/photo changes
- Copy refinements
- Layout spacing

**⏱ Phase Duration**: 3-5 days (design) + 3-5 days (client review/revisions)

---

## Step 3: Build the Component Gallery

**Goal**: Extract every reusable element from the homepage into a documented component library.

### Why This Matters

The component gallery is your **single source of truth**. Every page you build will use these components. If you need to change a button color, you change it here first, then propagate the change.

### Client Communication

*"The Home Page is approved! Now I will create our official Component Gallery. This is our library of all pre-approved, reusable building blocks. This ensures every page we build will be perfectly consistent and can be assembled much faster."*

### Component Extraction Process

Go through the homepage and identify every distinct element:

#### 1. Brand Foundations (Global Styles)

Document as design tokens:

**Color Palette**:
```
Primary: #0066CC
Secondary: #FF6B35
Accent: #00D4AA
Success: #22C55E
Warning: #F59E0B
Error: #EF4444
Text Primary: #1A1A1A
Text Secondary: #6B7280
Text Muted: #9CA3AF
Background: #FFFFFF
Background Alt: #F9FAFB
Border: #E5E7EB
```

**Typography**:
```
Font Primary: "Inter", sans-serif
Font Secondary: "Merriweather", serif (headings)

H1: 48px / 600 / 1.2
H2: 36px / 600 / 1.3
H3: 28px / 600 / 1.4
H4: 24px / 600 / 1.4
H5: 20px / 600 / 1.5
H6: 18px / 600 / 1.5
Body: 16px / 400 / 1.6
Lead: 20px / 400 / 1.6
```

**Spacing Scale**: 8, 16, 24, 32, 48, 64, 96

#### 2. Global Layout Components

**Navigation**:
- Desktop navigation bar
- Mobile navigation (hamburger menu)
- Dropdown/mega menu (if applicable)
- States: default, hover, active

**Footer**:
- Multi-column layout
- Logo placement
- Link groups
- Social icons
- Copyright notice

#### 3. Interactive Elements (Atoms)

**Buttons**:
- Primary button (solid, brand color)
- Secondary button (outline or muted)
- Text button (link-style)
- Ghost button (transparent)
- Large, medium, small sizes
- All states: default, hover, active, disabled, focus

**Form Elements**:
- Text input
- Text area
- Select dropdown
- Checkbox
- Radio button
- Label styling
- Error state
- Success state
- Disabled state

#### 4. Reusable Content Sections (Molecules & Organisms)

**Hero Sections**:
- **Home Page Hero**: Full-width, image background, large headline, CTA
- **Inner Page Hero**: Centered, simple, smaller headline

**Call-to-Action Blocks**:
- **Light CTA**: Light background, dark text
- **Dark CTA**: Dark background, light text
- Include: headline, body text, button

**Card Components**:
- **Blog/Post Card**: Image, title, excerpt, date, link
- **Team Member Card**: Photo, name, title, bio, social links
- **Service Card**: Icon, title, description, link
- **Feature Card**: Icon, title, description

**Content Grids**:
- **Feature Grid**: 3-column, icon + title + description
- **Stats Grid**: 2-4 items, large number + label
- **Logo Grid**: Client/partner logos in rows

**Content Blocks**:
- **Testimonial**: Quote, author, photo, company
- **Testimonial Slider**: Multiple testimonials with navigation
- **FAQ Accordion**: Question/answer pairs, expandable
- **Team Member Bio**: Full section with photo and details
- **Logo/Client Bar**: Horizontal row of logos
- **Sidebar Widget**: For blog posts (categories, tags, recent posts)
- **Prose Block**: Rich text styling (paragraphs, lists, blockquotes)

### Documentation Format

For each component, document:

**Component Name**: Primary Button

**Purpose**: Main call-to-action button for high-priority actions

**Usage**: "Get Started", "Contact Us", "Download Now"

**Visual Specs**:
- Background: Primary color (#0066CC)
- Text: White (#FFFFFF)
- Font: 16px / 600
- Padding: 12px 24px
- Border radius: 6px
- Hover: Darken by 10%

**Variations**:
- Default size
- Large size (18px font, 16px 32px padding)
- Small size (14px font, 8px 16px padding)

**Code Notes**: (for Hugo implementation later)
- Class: `.button .button--primary`
- Use `<button>` for actions, `<a>` for navigation

### Create Component Gallery Document

Options for format:
1. **Figma/Design Tool**: Create dedicated component page showing all elements
2. **HTML Prototype**: Build `component-gallery.html` with all components
3. **Documentation**: Markdown file with screenshots and specs
4. **Combination**: Figma + documented specs

**Best Practice**: Use your design tool to create the gallery, then export specs to a documentation file for the development team.

### Deliverable

**Component Gallery Document** containing:
- All design tokens (colors, fonts, spacing)
- Every component with visual example
- Specifications for each component
- Usage guidelines
- States and variations

**⏱ Phase Duration**: 2-3 days

---

## Step 4: Assemble the Inner Pages

**Goal**: Create remaining page designs by assembling pre-built components.

### Why This Is Fast

You're not designing from scratch—you're arranging LEGO blocks. Every component is already designed and approved.

### Client Communication

*"With our Component Gallery complete, I will now rapidly build out the remaining page templates. I will assemble these pages using the pre-built components, guaranteeing a consistent experience across the entire site."*

### Assembly Process

For each page:

1. **Copy** the Navigation and Footer from the gallery
2. **Choose** the appropriate hero component
3. **Arrange** content components based on page purpose
4. **Add** final CTA block before footer
5. **Review** for visual consistency

### Page-by-Page Assembly Guide

#### Inner Page 1: About Us / Services

**Purpose**: Introduce the company, team, or services

**Component Stack**:
- Navigation
- Inner Page Hero ("About Us")
- Prose Block (company story, 2-3 paragraphs)
- Team Member Cards (grid of 3-6 team members)
- Stats Grid (years in business, clients served, etc.)
- Final CTA Block ("Ready to work together?")
- Footer

**Design Notes**:
- Keep text blocks narrow (max 800px width)
- Use team cards in 3-column grid
- Stats should be bold and prominent

---

#### Inner Page 2: Our Process / Methodology

**Purpose**: Explain how you work, your methodology, or approach

**Component Stack**:
- Navigation
- Inner Page Hero ("How We Work")
- Prose Block (intro paragraph)
- Feature Grid (3-5 numbered steps with icons)
- Testimonial Slider (social proof of process)
- FAQ Accordion (common questions about process)
- Final CTA Block ("Ready to get started?")
- Footer

**Design Notes**:
- Number the process steps clearly (1, 2, 3...)
- Use icons that represent each phase
- Keep steps concise (title + 2-3 sentences each)

---

#### Contact Page

**Purpose**: Make it easy for visitors to reach you

**Component Stack**:
- Navigation
- Inner Page Hero ("Get in Touch")
- Two-column layout:
- Optional: Map embed
- Final CTA Block (or skip—form is the CTA)
- Footer

**Design Notes**:
- Form should be prominent and easy to use
- Include all contact methods (not just form)
- Consider adding office photo or map

---

#### Feed/Card Page: Blog / Portfolio Listing

**Purpose**: Display collection of posts or portfolio items

**Component Stack**:
- Navigation
- Inner Page Hero ("Blog" or "Our Work")
- Prose Block (optional intro paragraph)
- Card Grid (3 columns of blog/portfolio cards)
- Sidebar Widget (optional: categories, tags, search)
- Pagination controls (if needed)
- Final CTA Block ("Subscribe to our newsletter")
- Footer

**Design Notes**:
- Cards should be in responsive grid (3 cols desktop, 2 tablet, 1 mobile)
- Consistent card heights
- Clear visual hierarchy (image → title → excerpt → date)

---

#### Single Post Page: Blog Article / Portfolio Detail

**Purpose**: Full article or portfolio case study

**Component Stack**:
- Navigation
- Inner Page Hero (post title, author, date)
- Two-column layout:
- About the Author Card (below content)
- Related Posts (3 cards)
- Final CTA Block ("Join our newsletter")
- Footer

**Design Notes**:
- Main content should be readable width (650-750px)
- Sidebar should be ~25-30% of layout width
- On mobile, sidebar moves below content
- Use rich prose styling (blockquotes, code blocks, image captions)

---

### Design Review Checklist

For each assembled page, verify:

- [ ] Navigation and Footer are identical across all pages
- [ ] Hero components are used consistently
- [ ] All buttons match the defined styles
- [ ] Colors are from the approved palette
- [ ] Typography follows the scale
- [ ] Spacing is consistent (using the defined scale)
- [ ] Mobile layouts work properly
- [ ] Page has clear visual hierarchy

**⏱ Phase Duration**: 3-5 days (all 5 pages)

---

## Step 5: Final Review & Client Sign-Off

**Goal**: Get approval on all designs before moving to development.

### Client Communication

*"All 7 page templates are complete. Let's do a final review to ensure everything is perfect and consistent before we move into development."*

### Presentation Format

Present as a walkthrough:

1. **Overview**: "Here's the complete system we've built"
2. **Component Gallery**: "This is our library of reusable pieces"
3. **Each Page**: Show and explain each template
4. **Consistency**: "Notice how [button/card/etc] is the same everywhere"
5. **Flexibility**: "We can easily add new pages using these components"

### Final Review Checklist

Go through with client:

- [ ] Navigation and Footer are identical on all pages
- [ ] All buttons and interactive elements behave consistently
- [ ] All pages are fully responsive (show mobile versions)
- [ ] Typography and color are consistent throughout
- [ ] Each page serves its intended purpose
- [ ] Content hierarchy is clear
- [ ] Calls-to-action are prominent
- [ ] Brand identity is consistent

### Gather Feedback

Ask specific questions:
- "Does each page clearly communicate its purpose?"
- "Are the calls-to-action clear and compelling?"
- "Does this feel like your brand?"
- "Is there anything that feels inconsistent?"
- "Is anything missing that you expected to see?"

### Handle Revisions

If changes are needed:
1. **Small tweaks** (color, spacing): Update component gallery, then propagate
2. **Content changes**: Update specific pages
3. **Structural changes**: May require component redesign

**Key Rule**: Always update the component gallery first, then update pages.

### Sign-Off Document

Get written approval with:
- [ ] All page designs approved
- [ ] Component library approved
- [ ] Responsive behavior approved
- [ ] Ready to proceed to development

**⏱ Phase Duration**: 2-3 days (including revision time)

---

## Handoff to Development (Hugo Phase)

### What You're Handing Off

**Design Assets**:
- Component gallery (with full specifications)
- All page designs (desktop, tablet, mobile)
- Design tokens documented (colors, fonts, spacing)

**Documentation**:
- Component inventory and specifications
- Page structure breakdowns
- Interaction notes (hover states, animations)

**Client Approvals**:
- Signed-off designs
- Content requirements
- Technical specifications

### Bridge to Hugo Framework

This design phase maps directly to the Hugo Framework:

**Design Phase** → **Hugo Implementation**:
- **Component Gallery** → Component Design System (03-component-system.md)
- **Brand Foundations** → CSS Variables and Typography System
- **Page Templates** → Pattern Playbook (02-pattern-playbook.md)
- **Content Structure** → Front Matter Schema (04-front-matter-reference.md)

### Next Step

Move to **[Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md)** Phase 1 (Foundation Setup) to begin Hugo implementation.

---

## Tips for Success

### Do's ✅

- **Start with the homepage** - It's the most important and component-rich
- **Design mobile versions** - Don't leave responsive as an afterthought
- **Document everything** - Future you (and AI assistants) will thank you
- **Get client feedback early** - Don't design in a vacuum
- **Be consistent** - Use the component gallery religiously

### Don'ts ❌

- **Don't skip discovery** - Assumptions lead to revisions
- **Don't design all pages first** - Homepage → Gallery → Rest
- **Don't reinvent components** - If you have a button style, use it everywhere
- **Don't hide the design system** - Share the component gallery with clients
- **Don't start coding too early** - Get design approval first

---

## Tools & Resources

### Design Tools
- **Figma** (recommended for component systems)
- Adobe XD
- Sketch
- Canva (for simpler sites)

### Inspiration
- Dribbble (web design inspiration)
- Awwwards (award-winning sites)
- SiteInspire (categorized website gallery)
- Behance (full case studies)

### Color & Typography
- Coolors (palette generator)
- Adobe Color (color schemes)
- Google Fonts (free web fonts)
- Type Scale (typography scale calculator)

### Component Systems
- Atomic Design (methodology by Brad Frost)
- Material Design (Google's design system)
- Tailwind UI (component examples)

---

## Outcome

At the end of this phase, you have:

✅ **Client-approved designs** for all key page templates
✅ **Complete component library** documented and organized
✅ **Design specifications** ready for development
✅ **Clear path forward** to Hugo implementation

**You are now ready to move to the [Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md) to begin building the Hugo site.**
