---
title: "AEO Copywriting Guide"
aliases:
  - /docs/03-production/website-services/website/hugo-framework/01-aeo-copywriting
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

**Translating client copy with the "One Page, One Question" framework.**

---

## What is Answer Engine Optimization (AEO)?

**Answer Engine Optimization (AEO)** is the strategy of optimizing web content to be directly understood, trusted, and used by AI-powered search tools and chatbots.

These **"Answer Engines"** (like Google's Search Generative Experience, Perplexity, ChatGPT search, and others) are different from traditional search engines:

**Traditional SEO (Search Engine Optimization)**:
- Goal: Rank a link at the top of search results for a human to click
- Success = Click-through to your site

**AEO (Answer Engine Optimization)**:
- Goal: Have your content selected and presented as the definitive answer itself
- Success = AI uses your content as the authoritative source

**Our "One Page, One Question" framework is a core AEO strategy.**

---

## When This Phase Happens

**Before**: You've completed [Design & Discovery](/docs/03-production/website-services/website/hugo-framework/00-design-discovery.md) and have approved page designs.

**During**: You need actual copy to populate those designed pages.

**After**: You'll implement the copy in Hugo using the [Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md).

---

## Overview: The Content Creation Process

Your copywriting workflow:

1. **Interview client** (recorded conversation)
2. **Transcribe interview** (speech-to-text)
3. **Run transcript through Claude project** (your custom prompt/process)
4. **Apply AEO optimization** (this guide)
5. **Review and refine** (quality check)
6. **Hand off to Hugo implementation** (ready for development)

**This guide focuses on Step 4** - how to take the AI-generated draft and optimize it for AEO using the One Page, One Question framework.

---

## Our Guiding Philosophy

**We are "Answer Experts," not content describers.**

**Traditional web copy**:
- Company-centric ("We offer...", "Our services include...")
- Descriptive (tells what they do)
- Assumes the visitor will read everything

**AEO-optimized copy**:
- User-centric ("Here's how to solve your problem...")
- Prescriptive (answers specific questions)
- Structured for both humans and AI to extract the answer

**Goal**: An Answer Engine should be so confident in our content's clarity that it uses our page as the definitive answer source.

---

## The Core Translation Process

Use this for **all pages** (except Homepage and Contact - see special cases below).

### Step 1: Discover the "One Question"

Read the client's draft copy and ask:

**"What specific question would a perfect customer type into a search engine to find this page?"**

#### Example 1: Service Page Problem

**Client Copy**: A page titled "Our Services" that lists 10 different services.

**Problem**: This is actually 10 questions, not one.

**Solution**: Split into 10 separate pages, each answering one question.

**For "Vehicle Wraps" service**:
- ❌ Bad question: "What are your services?"
- ✅ Good question: "What are the benefits of a commercial vehicle wrap?"
- ✅ Good question: "How much does a vehicle wrap cost?"

#### Example 2: About Page Problem

**Client Copy**: "About Us" page covering company history, team, values, process, and awards.

**Problem**: This tries to answer 5 different questions.

**Solution**: Determine the PRIMARY question, then link to other pages for the rest.

**Options**:
- "Who is [Company Name]?" (focus on company story)
- "Why should I choose [Company Name]?" (focus on differentiation)
- "How does [Company Name] work?" (focus on process)

#### Red Flags That You Need to Split Pages

- Page title is generic ("Services", "About", "What We Do")
- Copy covers multiple unrelated topics
- You have 5+ H2 headings that could each be their own page
- The page feels like it's trying to be everything

**Rule**: If you can ask 2-3 completely different questions about a page, it needs to be split.

---

### Step 2: Write the "Core Answer Phrase" (CAP)

This is **the most important sentence you will write** for each page.

#### Specifications

**Length**: 18-25 words (150-160 characters with spaces)

**Purpose**: Directly answer the "One Question" in a single, complete sentence.

**Placement**:
1. The meta description (front matter)
2. The first paragraph of the page content

#### Example: Vehicle Wrap Benefits Page

**One Question**: "What are the benefits of a commercial vehicle wrap?"

**Core Answer Phrase**:
> "A commercial vehicle wrap is a high-impact, cost-effective mobile billboard that generates thousands of local impressions daily, protecting your paint and boosting brand recognition."

**Character count**: 174 characters (slightly long - could trim to hit 160)

**Refined**:
> "A vehicle wrap is a cost-effective mobile billboard generating thousands of daily impressions, protecting your paint while boosting brand recognition."

**Character count**: 154 characters ✅

#### Core Answer Phrase Template

Fill in the blanks:

> "[Topic] is [definition/benefit] that [primary value] by [mechanism/how it works], [additional benefit]."

**Examples**:

**For "What is AEO?"**:
> "AEO is a content strategy that optimizes pages to be selected as definitive answers by AI search engines, increasing visibility without requiring click-throughs."

**For "How does vehicle wrap installation work?"**:
> "Vehicle wrap installation is a 3-5 day process where certified technicians apply precision-cut vinyl graphics to your vehicle using heat and specialized tools for a seamless, paint-like finish."

#### Why This Matters for AEO

Answer Engines scan pages looking for:
1. **The question being answered** (page title, H1)
2. **The direct answer** (first paragraph, meta description)
3. **Supporting evidence** (H2 sections, structured content)

Your Core Answer Phrase is what AI will extract and present as THE ANSWER.

---

### Step 3: Build the "Answer-First" Structure

Use the client's copy as raw material, but reorganize it into a logical flow that supports your Core Answer.

#### The Structure

##### `<h1>` - The Page Title

**Purpose**: Clear label for the question being answered.

**Format Options**:
- Question format: "What Are the Benefits of a Vehicle Wrap?"
- Statement format: "Commercial Vehicle Wrap Benefits"
- How-to format: "How Vehicle Wraps Increase Brand Visibility"

**Choose based on**:
- How users actually search (check Google autocomplete)
- What feels natural for the content

**Example**: `<h1>Commercial Vehicle Wrap Benefits</h1>`

##### First Paragraph - The Core Answer

**Purpose**: Immediately answer the H1 question.

**Structure**:
```markdown
# Commercial Vehicle Wrap Benefits

A vehicle wrap is a cost-effective mobile billboard generating thousands of daily impressions, protecting your paint while boosting brand recognition.

[Rest of content follows...]
```

**Why this works**:
- Human visitors get immediate answer (no scrolling)
- Answer Engines find clear, extractable answer
- Sets context for everything that follows

##### `<h2>` Headings - Supporting/Follow-up Questions

**Purpose**: Break down the topic into logical sub-questions that support or expand the main answer.

**For the Vehicle Wrap page**, the H2s might be:

```markdown
## How Many Impressions Will My Wrap Get?

[Supporting data and explanation...]

## Does a Wrap Protect My Vehicle's Paint?

[Technical details about protection...]

## What Is the Vehicle Wrap Design Process?

[Step-by-step process...]

## How Long Does a Vehicle Wrap Last?

[Lifespan information...]

## What Does a Vehicle Wrap Cost?

[Pricing information or CTA to contact...]
```

**H2 Structure Rules**:
1. Each H2 should be a follow-up question a reader would naturally ask
2. Order them logically (most important or most common questions first)
3. Each section should be complete enough to stand alone
4. 3-5 H2 sections per page (if you have 10, you need multiple pages)

##### `<h3>` Headings - Sub-points (Optional)

Only use if you need to break down an H2 section further.

**Example**:

```markdown
## What Is the Vehicle Wrap Design Process?

### 1. Initial Consultation

We discuss your brand, goals, and vehicle specifications...

### 2. Design Mockups

Our designers create 2-3 concepts for your review...

### 3. Approval and Production

Once approved, we print and prepare your wrap...
```

---

### Step 4: Translate the Body Copy

Take the client's paragraphs and rewrite them to be **direct and answer-focused**.

#### Translation Examples

##### Example 1: Remove Fluff

**Client Copy**:
> "We use high-quality 3M vinyl in our wraps, and our team has over 20 years of experience in design and installation for all kinds of businesses."

**Problem**: Vague, company-centric, buries the benefit.

**Translated** (under H2: "Why Choose Us?"):
> "We guarantee a flawless, lasting wrap by using only premium 3M vinyl. Our installation team brings over 20 years of experience, ensuring your brand is represented perfectly."

**Improved because**:
- Starts with benefit ("flawless, lasting")
- Factual specifics (3M vinyl, 20 years)
- User-focused outcome ("your brand represented perfectly")

##### Example 2: Make It Prescriptive

**Client Copy**:
> "Our design team is creative and works with you to understand your vision and goals."

**Problem**: Generic, no specifics, no value statement.

**Translated** (under H2: "What Is the Design Process?"):
> "Your dedicated designer creates 2-3 custom mockups based on your brand guidelines. You'll see exactly how your wrap will look on your vehicle before production begins, with unlimited revisions included."

**Improved because**:
- Specific deliverables (2-3 mockups)
- Clear process (mockups → review → revisions)
- Removes uncertainty ("see exactly how it will look")

##### Example 3: Answer the Objection

**Client Copy**:
> "Wraps are a great way to advertise your business."

**Problem**: Obvious statement, no depth, doesn't address concerns.

**Translated** (under H2: "How Many Impressions Will My Wrap Get?"):
> "A single wrapped vehicle generates 30,000-70,000 impressions per day, according to the Outdoor Advertising Association. Unlike digital ads that disappear after your budget runs out, your wrap works 24/7 for 5-7 years with no recurring costs."

**Improved because**:
- Cites authoritative source
- Provides specific numbers
- Addresses the "ROI" objection
- Compares to alternative (digital ads)

#### Translation Principles

✅ **Do**:
- Use specific numbers and data
- Compare to alternatives ("Unlike X, our solution...")
- Address common objections directly
- Focus on outcomes, not features
- Use active voice

❌ **Don't**:
- Use vague qualifiers ("very", "really", "quite")
- Make unsubstantiated claims ("the best", "industry-leading")
- Bury the point in corporate speak
- Assume visitors understand industry jargon
- Write long paragraphs (break into 2-3 sentences max)

---

## Special Page Translations

Two pages break the "One Page, One Question" rule by design.

### The Homepage Translation

#### The "One Question" (Actually Three)

The homepage doesn't answer one specific question. It answers the **three most important broad questions** about the business:

1. **"Who are you?"**
2. **"What do you do?"**
3. **"Why should I care?"**

#### Core Answer Phrase = Unique Value Proposition (UVP)

**Purpose**: The homepage meta description is the company's UVP - the "Core Answer" for the entire business.

**Example**:
> "We help local service businesses generate more leads with AEO-optimized websites and direct-response copywriting that converts."

**Character count**: 149 characters ✅

#### `<h1>` - The Hero Headline

**Purpose**: The UVP distilled into a powerful, clear promise.

**Format**: Not a question - a statement of value.

**Examples**:
- "Stop Guessing. Start Converting. Get Websites That Work."
- "Turn Your Vehicle Into a 24/7 Billboard"
- "Custom Websites That Show Up and Convert"

**Hero Headline Formula**:
> "[Solve problem]. [Achieve outcome]. [How we do it]."

#### Body Copy's Job: Triage Center

The homepage is **not** where answers live. It's where visitors **find the page that has their answer**.

**Sections**:

1. **Hero** - UVP headline + 1-2 sentences + CTA
2. **Services/Solutions** - 1 sentence per service + link to full page
3. **Social Proof** - Client logos, testimonial, stat
4. **Process/How It Works** - 3-5 steps (high-level overview)
5. **About** - 2-3 sentences + link to full About page
6. **Final CTA** - Clear next action

**Example: Services Section Copy**

**Bad (too much detail)**:
> "Our web design services include custom WordPress development, mobile-responsive layouts, SEO optimization, performance tuning, and ongoing maintenance. We work with businesses of all sizes..."

**Good (summary + link)**:
> "Custom websites built for speed, conversions, and AEO from day one. [Learn about our web design process →]"

**Why**: The homepage's job is to get them to click to the **1P1Q page** that fully answers their specific question.

---

### The Contact Page Translation

#### The "One Question"

**"How do I get in touch?"** (or variations like "How do I get a quote?")

#### Core Answer Phrase = Frictionless CTA

**Purpose**: Remove all barriers to contact.

**Example**:
> "Contact our team today for a free, no-obligation consultation on your next web design or marketing project. We respond within 24 hours."

**Character count**: 156 characters ✅

**Key elements**:
- Clear action ("Contact our team")
- Benefit ("free, no-obligation consultation")
- Speed expectation ("within 24 hours")

#### `<h1>` - Simple, Clear CTA

**Examples**:
- "Contact Us"
- "Let's Talk"
- "Get Your Free Quote"
- "Ready to Get Started?"

**No need to be clever** - clarity wins here.

#### Body Copy's Job: Remove Friction

The form is the hero. Copy should be **minimal**.

**Bad Copy** (creates friction):
> "We are passionate about helping our clients and believe in a synergistic partnership that leverages our collective strengths to achieve transformational outcomes for forward-thinking businesses..."

**Why it's bad**: Visitor has decided to contact you. Don't make them read a mission statement.

**Good Copy**:
> "Use the form below or call us at (555) 123-4567. We'll review your project and get back to you within one business day."

**Why it's good**:
- Options (form or phone)
- Clear expectation (one business day)
- No fluff

**Optional additions**:
- Office address (if you have a physical location clients visit)
- Hours of operation
- Email address (as alternative to form)

---

## Translation Quick-Reference Checklist

Use this for **every page** you optimize:

| Check | Task |
|-------|------|
| [ ] | **Discover**: Have I identified the single question this page must answer? |
| [ ] | **Answer**: Have I written the "Core Answer Phrase" (150-160 chars) that answers it? |
| [ ] | **Position**: Is that "Core Answer Phrase" the meta description AND the first paragraph? |
| [ ] | **Structure**: Is the `<h1>` a clear label for the question? |
| [ ] | **Structure**: Do my `<h2>` headings ask logical follow-up questions? |
| [ ] | **Translate**: Have I rewritten the client's copy to be direct, removing all fluff? |
| [ ] | **Connect**: Does this page link to other pages that answer the next logical question? |
| [ ] | **Length**: Is the page complete enough to answer the question fully? (No arbitrary word counts) |
| [ ] | **Scan**: Can someone scan the headings and understand the full answer? |

---

## Quality Checks Before Hugo Implementation

Before handing copy off to Hugo development:

### Content Quality

- [ ] Every page answers exactly one clear question
- [ ] Core Answer Phrase is under 160 characters
- [ ] First paragraph matches the meta description
- [ ] Heading hierarchy is logical (one H1, multiple H2s, optional H3s)
- [ ] No marketing fluff or vague statements
- [ ] Specific data and examples included
- [ ] Active voice used throughout
- [ ] Paragraphs are short (2-4 sentences max)

### AEO Optimization

- [ ] Answer comes first (no "In this article..." intros)
- [ ] Headings are questions or clear topic labels
- [ ] Content is structured (not walls of text)
- [ ] Supporting evidence follows the main answer
- [ ] Links to related "next question" pages included

### Technical Readiness

- [ ] All copy is in Markdown format (or ready to be)
- [ ] Front matter fields identified (title, seo_title, description)
- [ ] Image placeholders noted (with alt text)
- [ ] Internal links mapped out
- [ ] CTAs clearly marked

---

## Example: Complete Page Translation

### Before (Client Draft)

**Page**: "Vehicle Wraps"

**Copy**:
```
Vehicle Wraps

We offer vehicle wrap services for all types of vehicles. Our team has been doing wraps for over 20 years and we use the best materials available. Vehicle wraps are a great way to advertise your business because they get a lot of attention. We can design custom graphics for your brand. The process is easy and we work with your schedule. Contact us for a quote.
```

**Problems**:
- Generic title
- No clear question being answered
- All company-focused ("We offer...", "We can...")
- No structure (one paragraph)
- No specific benefits or data
- Vague claims ("best materials", "a lot of attention")

---

### After (AEO-Optimized)

**File**: `content/services/vehicle-wrap-benefits.md`

**Front Matter**:
```yaml
title: "Commercial Vehicle Wrap Benefits"
seo_title: "Vehicle Wrap Benefits: ROI & Brand Impact | [Company]"
description: "A vehicle wrap is a cost-effective mobile billboard generating thousands of daily impressions, protecting your paint while boosting brand recognition."
```

**Content**:
```markdown
# Commercial Vehicle Wrap Benefits

A vehicle wrap is a cost-effective mobile billboard generating thousands of daily impressions, protecting your paint while boosting brand recognition.

## How Many Impressions Will My Wrap Get?

A single wrapped vehicle generates 30,000-70,000 impressions per day, according to the Outdoor Advertising Association. Unlike digital ads that stop when your budget runs out, your wrap works 24/7 for 5-7 years with zero recurring costs.

For a typical commercial van driving 15,000 miles per year in urban and suburban areas, that's over 15 million impressions annually—at a cost per impression far below any other advertising medium.

## Does a Wrap Protect My Vehicle's Paint?

Yes. The vinyl wrap acts as a protective layer against minor scratches, stone chips, and UV damage. When it's time to remove or replace your wrap (typically after 5-7 years), the original paint underneath is preserved.

This protection can increase your vehicle's resale value, especially for leased vehicles that must be returned in good condition.

## What Is the Design & Installation Process?

### 1. Brand Consultation (30-60 minutes)

We review your brand guidelines, target audience, and goals to create a design brief.

### 2. Custom Design (3-5 business days)

Your dedicated designer creates 2-3 mockup concepts showing exactly how your wrap will look on your specific vehicle make and model. Unlimited revisions included.

### 3. Production & Installation (3-5 days)

We print your approved design on premium 3M vinyl and schedule installation at our facility. Our certified technicians apply your wrap using precision techniques for a seamless, paint-like finish.

Your vehicle is ready for pickup with a full care guide and warranty documentation.

## What Types of Vehicles Can Be Wrapped?

We wrap all commercial vehicles:

- Cargo vans and box trucks
- Pickup trucks
- Trailers
- Service vehicles (plumbing, HVAC, electrical)
- Food trucks
- Delivery vehicles
- Company cars and SUVs

Partial wraps and spot graphics also available for budget-conscious projects.

## Ready to Turn Your Vehicle Into a Billboard?

[Contact us for a free quote and design consultation →](/contact/)
```

---

### What Changed (Analysis)

✅ **Clear question**: "What are the benefits of a vehicle wrap?"

✅ **Core Answer Phrase**: First paragraph + meta description

✅ **H2 as follow-up questions**: Each section answers a logical next question

✅ **Specific data**: "30,000-70,000 impressions", "15 million annually", "5-7 years"

✅ **User-focused**: "Your wrap", "Your vehicle" instead of "We offer"

✅ **Structured for AEO**: Answer first, supporting evidence, scannable headings

✅ **Clear CTA**: Links to next logical step (contact page)

---

## Integration with Hugo Framework

Once copy is optimized, it flows directly into:

1. **[Pattern Playbook](/docs/03-production/website-services/website/hugo-framework/03-pattern-playbook.md)** - Determines which Hugo pattern to use
2. **[Front Matter Reference](/docs/03-production/website-services/website/hugo-framework/05-front-matter-reference.md)** - Populates required fields
3. **[Workflow Guide](/docs/03-production/website-services/website/hugo-framework/06-workflow-guide.md)** Phase 7 - Content creation in Hugo

**The copy you create here becomes the content in Hugo's Markdown files.**

---

## Summary: The AEO Copywriting Philosophy

**Every page is an answer, not a description.**

- Traditional sites describe what a company does
- AEO-optimized sites answer what a customer needs to know

**When your content is structured as clear, direct answers:**
- Humans find what they need immediately
- Answer Engines select your content as authoritative
- You rank for questions, not just keywords
- Visitors convert because they trust you solved their problem

**This is the bridge between client interviews and Hugo implementation.**
