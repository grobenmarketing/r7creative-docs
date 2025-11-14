---
title: "CLICKUP: ClickUp Structure & System Relationships"
description: "Complete guide to R7 Creative's dual ClickUp systems: You Capture We Create and Two Clocks"
weight: 30
tags: ["clickup", "workflow", "systems", "operations"]
status: "complete"
---
INPUT NEEDED: Lets work this out in clickup instead of here. seems like a waste
# ClickUp Structure & System Relationships

**Last Updated:** November 10, 2025

---

## Overview

R7 Creative operates **two separate but related ClickUp systems** to manage client work:

1. **You Capture We Create** - Content creation workflow (social media, GBP posts)
2. **Two Clocks** - Website update requests (for clients with website services)

**Critical Relationship:** If a client has **Two Clocks** (website), they **ALWAYS** have **You Capture We Create** (content). But **You Capture We Create** can exist without Two Clocks.

---

## System Comparison

| Feature | You Capture We Create | Two Clocks |
|---------|----------------------|------------|
| **Purpose** | Content creation (social + GBP) | Website maintenance/updates |
| **Clients** | All R7 Creative clients (Tiers 1-5) | Only clients with LaunchPad or Authority Builder |
| **Workflow** | Weekly/bi-weekly content batches | Monthly update batches |
| **Deliverables** | Social posts, GBP posts, videos | Text changes, image swaps, new pages |
| **Tools** | ClickUp + Frame IO | ClickUp + GitHub + Netlify |
| **Credit System** | No credits (package-based) | Monthly credits (30 or 60) |
| **Can Exist Standalone?** | ✅ YES | ❌ NO (always paired with content) |

---

## You Capture We Create System

### Who Has This

**Everyone.** All R7 Creative clients have You Capture We Create as their foundation service.

**Service Tiers:**
- Tier 1: GBP Foundation ($245/mo)
- Tier 2: Social Starter ($395/mo)
- Tier 3: 4-Minute Winner ($550/mo)
- Tier 4: 4-Minute Dominator ($950/mo)
- Tier 5: Local Market Leader ($1,895/mo)

→ See [Complete Pricing Structure](/docs/01-sales/pricing) for all tiers

### ClickUp Structure

**Location:** One ClickUp Space per client

**Lists:**
1. **Content** - Main list for all content pieces
2. **Uploads** - Where client uploads raw media (via JotForm)
3. **Archive** - Completed content (optional)

**Custom Statuses:**
1. **ASSIGNED** - Content piece assigned to Content Owner (CO)
2. **UPLOADED** - CO uploaded raw media to Frame IO
3. **REVIEW READY** - Editor completed, ready for internal QA
4. **CLIENT REVIEW** - Sent to client for approval
5. **SCHEDULED** - Approved and scheduled in Metricool/OneUP
6. **ARCHIVED** - Published and archived

**Custom Fields:**
- **Content Owner** (Person) - Who's capturing the content
- **Platform** (Dropdown) - GBP, FB, IG, TikTok, LinkedIn, etc.
- **Content Type** (Dropdown) - Video, Photo, Text post, Story
- **Capture Date** (Date)
- **Upload Deadline** (Date)
- **Publish Date** (Date)
- **Frame IO Link** (URL)

**Workflow Cycle:**
- Bi-weekly content planning meetings
- Weekly content captures by client
- Weekly uploads to Frame IO
- 3-5 day editing turnaround
- Client review (24-48 hours)
- Scheduled publishing

→ See [You Capture We Create Workflow](/docs/04-management/you-capture-we-create-workflow) for complete process

---

## Two Clocks System

### Who Has This

**Only clients with website services:** LaunchPad or Authority Builder

**Activation Fees:**
- LaunchPad: $1,450 (Founder) / $1,950 (Retail) - 30 credits/month
- Authority Builder: $2,750 (Founder) / $3,950 (Retail) - 60 credits/month

### ClickUp Structure

**Location:** One ClickUp Space per client OR filtered view in shared list

**Lists:**
1. **Client Website Updates** - Main list for all update requests

**Custom Statuses:**
1. **NEW REQUEST** - Form submission inbox
2. **PENDING: CLIENT INFO** - Awaiting info from client
3. **APPROVED** - Groomed and ready for developer
4. **ON HOLD (Overage)** - Out of credits this month
5. **IN PROGRESS** - Developer actively working
6. **READY FOR REVIEW** - Deploy Preview ready
7. **COMPLETE (Live)** - Merged and published

**Custom Fields:**
- **Client Name** (Dropdown) - For filtering
- **Credits Cost** (Number) - Client-facing cost
- **Internal Time** (Number) - Actual dev time
- **URL** (Text) - Page to update
- **Deploy Preview** (URL) - Netlify preview link
- **Month** (Date) - Billing month

**Workflow Cycle:**
- Client submits ClickUp form (anytime)
- Triage Manager grooms daily
- Developer batches monthly
- Client reviews Deploy Preview
- Approved changes merge to production

→ See [Two Clocks Workflow](/docs/03-production/website-services/website/website-maintenance/two-clocks-workflow) for complete process

---

## System Relationships

### How They Work Together

**Scenario 1: Content-Only Client (No Website)**
- Client has: You Capture We Create (Tier 2: Social Starter at $395/mo)
- ClickUp Setup: ONE Space with Content + Uploads lists
- Services: Social media content, GBP posts, review engagement
- Result: Simple, focused content workflow

**Scenario 2: Content + Website Client**
- Client has: You Capture We Create (Tier 4: 4-Minute Dominator at $950/mo) + LaunchPad Website ($1,450 activation)
- ClickUp Setup: ONE Space with BOTH systems:
  - **Content list** (for social/GBP workflow)
  - **Uploads list** (for client media uploads)
  - **Website Updates list** (for Two Clocks requests)
- Services: All content services + 30 website update credits/month
- Result: Dual workflow - content team + web dev team both working with same client

**Scenario 3: Upgrade Path (Content → Content + Website)**
- Client starts: Tier 3 ($550/mo, You Capture We Create only)
- Client upgrades: Adds Authority Builder ($2,750 activation, 60 credits/month)
- ClickUp Changes:
  - Existing Content + Uploads lists remain unchanged
  - ADD Website Updates list to same Space
  - Client can now submit website requests via form
- Result: Seamless integration, existing content workflow continues

---

## Client Workspace Naming Conventions

### Standard Naming

**Format:** `[Client Business Name]`

**Example:**
- "Joe's Plumbing"
- "ABC Electric"
- "Smith & Sons Remodeling"

### Lists Within Space

**For Content-Only Clients:**
```
📁 Joe's Plumbing
  ├── 📋 Content
  └── 📋 Uploads
```

**For Content + Website Clients:**
```
📁 Joe's Plumbing
  ├── 📋 Content
  ├── 📋 Uploads
  └── 📋 Website Updates
```

### Folder Organization (If Using Shared Lists)

**Alternative Structure:** Some teams prefer one shared "All Clients" Space with filtered views

```
📁 R7 Creative - All Clients
  ├── 📋 Content (All Clients)
  │   └── [Filter by Client Name custom field]
  ├── 📋 Uploads (All Clients)
  │   └── [Filter by Client Name custom field]
  └── 📋 Website Updates (All Clients)
      └── [Filter by Client Name custom field]
```

**Recommendation:** Individual Spaces per client for clarity, especially when granting client view access.

---

## Setting Up Both Systems for a New Client

### Step 1: Determine Services

**Questions to ask during sales/onboarding:**
1. Which content tier? (Tiers 1-5)
2. Do they need a website? (No / LaunchPad / Authority Builder)

**Example Decision Matrix:**

| Client | Content Tier | Website | Activation Fee | Monthly Recurring | Systems Needed |
|--------|--------------|---------|----------------|------------------|----------------|
| Joe's Plumbing | Tier 2 ($395) | No | $300 | $395 | You Capture We Create only |
| ABC Electric | Tier 4 ($950) | LaunchPad | $300 + $1,450 | $950 | You Capture We Create + Two Clocks (30 credits) |
| Smith Remodeling | Tier 5 ($1,895) | Authority Builder | $300 + $2,750 | $1,895 | You Capture We Create + Two Clocks (60 credits) |

---

### Step 2: Create ClickUp Space

**For Content-Only Client:**

1. **Create Space:** "[Client Business Name]"
2. **Add Lists:**
   - Content (use You Capture We Create template)
   - Uploads (use Uploads template)
3. **Set Up Custom Fields** (Content list):
   - Content Owner
   - Platform
   - Content Type
   - Capture Date
   - Upload Deadline
   - Publish Date
   - Frame IO Link
4. **Grant Client Access:** View-only or comment-only
5. **Create Calendar View:** For content planning meetings

---

### Step 3: Set Up Automations

**You Capture We Create Automations:**

**Automation 1: New Upload Notification**
- **Trigger:** Status changes to "UPLOADED"
- **Action:** Notify Editor via email
- **Template:** "New content uploaded for [Client Name] - Task: [Task Name]"

**Automation 2: Client Review Reminder**
- **Trigger:** Status changes to "CLIENT REVIEW"
- **Action:** Wait 24 hours → Send reminder email to client
- **Template:** "Reminder: Please review your content for [Task Name]"

**Automation 3: Scheduled Confirmation**
- **Trigger:** Status changes to "SCHEDULED"
- **Action:** Send confirmation email to client
- **Template:** "Your content has been scheduled! Publish date: [Publish Date]"

**Two Clocks Automations:**

**Automation 1: New Request Assignment**
- **Trigger:** New task created (via form)
- **Action:** Assign to Triage Manager
- **Template:** "New website update request from [Client Name]"

**Automation 2: Pending Info Reminder**
- **Trigger:** Status changes to "PENDING: CLIENT INFO"
- **Action:** Wait 48 hours → Send reminder
- **Template:** "We still need info for your website update request"

**Automation 3: Deploy Preview Ready**
- **Trigger:** Status changes to "READY FOR REVIEW"
- **Action:** Send email to client with Deploy Preview link
- **Template:** "Your website updates are ready for review: [Deploy Preview URL]"

---

### Step 4: Set Up Forms

**You Capture We Create:** JotForm for Upload Submissions

**Form:** "Weekly Content Upload - [Client Name]"

**Fields:**
- Your Name
- This Week's Content Theme (dropdown from calendar)
- Upload Files (file upload, max 10 files)
- Notes/Context (text area)

**Integration:** JotForm → ClickUp (creates task in Uploads list)

---

**Two Clocks:** ClickUp Native Form for Update Requests

**Form:** "Submit a Website Update Request"

**Fields:**
- What page needs updating? (URL)
- What type of update? (Dropdown)
- Describe the change (Long text)
- Attach files (File upload)
- Priority (Dropdown: Normal / Urgent)

**Integration:** Automatic (ClickUp native form creates task in Website Updates list with "NEW REQUEST" status)

---

## Managing Client Upgrades

### Upgrade Scenario 1: Content Tier Increase

**Example:** Client upgrades from Tier 2 ($395) to Tier 4 ($950)

**ClickUp Changes Needed:**
- ✅ No structural changes to Space or Lists
- ✅ Update content calendar to reflect increased frequency
- ✅ Add/remove platforms based on new tier (e.g., add TikTok)
- ✅ Update meeting frequency (monthly → bi-weekly)

**Process:**
1. Notify content team of upgrade
2. Schedule updated Brand Strategy Meeting if needed
3. Adjust content calendar template
4. Update client's ClickUp permissions if needed (e.g., grant calendar view)

---

### Upgrade Scenario 2: Add Website Services

**Example:** Client on Tier 3 ($550) adds LaunchPad website ($1,450 activation + 30 credits/month)

**ClickUp Changes Needed:**
- ✅ ADD "Website Updates" list to existing Space
- ✅ Apply Two Clocks list template
- ✅ Set up website form and automations
- ✅ Update Space description to note dual services

**Process:**
1. **Create Website Updates List:**
   - Use Two Clocks template
   - Configure custom fields
   - Set up statuses

2. **Set Up Form:**
   - Create ClickUp form: "Submit Website Update - [Client Name]"
   - Share form link with client
   - Add to client onboarding email

3. **Notify Teams:**
   - Alert web dev team of new client
   - Add client to monthly batch schedule
   - Update credit tracking spreadsheet

4. **Client Communication:**
   ```
   Hi [Client], great news! Now that your website is live, you have access
   to 30 monthly update credits via our Two Clocks system.

   To submit update requests, use this form: [ClickUp Form Link]

   Updates are processed in monthly batches (first week of each month).
   Your credits refresh on the 1st of each month and do not roll over.

   Questions? Just reply to this email!
   ```

---

### Upgrade Scenario 3: LaunchPad → Authority Builder

**Example:** Client on LaunchPad (30 credits) upgrades to Authority Builder (60 credits)

**ClickUp Changes Needed:**
- ✅ No structural changes
- ✅ Update credit tracking (30 → 60 credits/month)
- ✅ Update Internal Service Catalog if needed

**Process:**
1. Update client record in credit tracking spreadsheet
2. Notify Triage Manager of increased credit allowance
3. Notify client:
   ```
   Hi [Client], you've been upgraded to Authority Builder!

   Your monthly credits have increased from 30 to 60. This means you can
   now request more frequent updates, add new pages, and keep your site
   fresh with weekly changes if needed.

   Submit requests anytime via your form: [Link]
   ```

---

## Handling Client Downgrades or Cancellations

### Downgrade: Remove Website Services

**Example:** Client cancels website maintenance but keeps content

**ClickUp Changes:**
- Archive "Website Updates" list
- Maintain Content + Uploads lists
- Update Space description

**Process:**
1. Complete any pending website updates
2. Archive Website Updates list (don't delete - historical data)
3. Remove client from web dev batch schedule
4. Update credit tracking spreadsheet (mark as inactive)
5. Notify teams

---

### Downgrade: Reduce Content Tier

**Example:** Client downgrades from Tier 4 ($950) to Tier 2 ($395)

**ClickUp Changes:**
- No structural changes
- Reduce content calendar frequency
- Remove platforms (e.g., remove TikTok, keep GBP + FB + IG)

**Process:**
1. Adjust content calendar template
2. Update platform settings
3. Reduce meeting frequency (bi-weekly → monthly)
4. Complete all in-flight content before downgrade takes effect

---

### Full Cancellation

**Example:** Client cancels all services

**ClickUp Changes:**
- Archive entire Space (don't delete)
- Remove client access
- Export all tasks/data for records

**Process:**
1. Complete all in-flight work
2. Final delivery of all content
3. Archive Space
4. Update all tracking spreadsheets
5. Store archived data per data retention policy

---

## Credits Do NOT Overlap

**IMPORTANT:** Two Clocks credits are separate from content services. They do NOT overlap or substitute for each other.

**Example:**
- Client has Tier 4 ($950/mo) + LaunchPad (30 credits/mo)
- **Content Services:** 3 social posts/week, 1 GBP post/week (unlimited within package)
- **Website Updates:** 30 credits/month (limited, tracked)

**What This Means:**
- ✅ Client can request unlimited content pieces within their Tier 4 scope
- ❌ Client CANNOT use website credits to request extra social posts
- ❌ Client CANNOT use content allowance to request extra website updates
- ✅ Each system is independent and has its own rules

---

## Monthly Workflow Integration

### Week 1: Planning & Batch Processing

**You Capture We Create:**
- Bi-weekly strategy calls
- Content planning for next 2 weeks
- Review performance metrics

**Two Clocks:**
- Developer processes all "APPROVED" website updates
- Create Deploy Previews
- Send to clients for review

---

### Week 2-3: Execution & Review

**You Capture We Create:**
- Clients capture content
- Clients upload to Frame IO
- Editors produce content
- Internal QA review

**Two Clocks:**
- Clients review Deploy Previews
- Approve or request revisions
- Deploy to production
- Mark tasks complete

---

### Week 4: Wrap-Up & Reporting

**You Capture We Create:**
- Client review of edited content
- Revisions (if needed)
- Scheduling all approved content

**Two Clocks:**
- Triage Manager reviews credit usage
- Identifies overages
- Prepares upsell conversations
- Updates credit tracking

---

## Reporting & Metrics

### Separate Reporting

**You Capture We Create Metrics:**
- Number of content pieces produced
- Engagement rates by platform
- Client approval rate (first-time approval %)
- Average turnaround time

**Two Clocks Metrics:**
- Credits used per client per month
- % of clients hitting credit limit
- Average task turnaround time
- Upsell conversion rate (Priority Updates, package upgrades)

**Combined Metrics:**
- Overall client satisfaction score
- Client retention rate
- Upgrade rate (tier increases, adding website services)
- Average revenue per client (content + website)

---

## Troubleshooting Common Issues

### Issue: Client confused about which system to use

**Symptoms:**
- Client submits website update request via JotForm (content system)
- Client asks for social post via website update form

**Solution:**
- Politely redirect to correct system:
  ```
  Thanks for reaching out! This request is for [website/content], so please
  submit it via your [correct form link]. This ensures we route it to the
  right team and don't miss anything. Thanks!
  ```
- Update client onboarding documentation to be clearer
- Consider color-coding forms or system names

---

### Issue: Duplicate tasks across systems

**Symptoms:**
- Same request submitted to both Content list and Website Updates list

**Solution:**
- Mark one as duplicate
- Comment on both tasks explaining which system handles it:
  ```
  This request has been moved to [Content / Website Updates] as that's
  the appropriate system for this type of work. We'll handle it there!
  ```
- Update form help text to clarify scope differences

---

### Issue: Client requests overlap in scope

**Example:** "Add a new blog post to website" could be content OR website update

**Solution:**
- **If client has ongoing content package:** Handle via You Capture We Create (no credits used)
- **If client only has website (no content package):** Handle via Two Clocks (uses credits)
- Document decision in task comments
- Create internal SOP for edge cases

---

## Training New Team Members

### Onboarding Checklist for Content Team

- [ ] Review You Capture We Create Workflow documentation
- [ ] Review Brand Pillars framework
- [ ] Shadow 2-3 client strategy meetings
- [ ] Practice editing workflow in Frame IO
- [ ] Learn Metricool/OneUP scheduling
- [ ] Understand all 5 content tiers and what they include

### Onboarding Checklist for Web Dev Team

- [ ] Review Two Clocks Workflow documentation
- [ ] Learn Hugo framework and component library
- [ ] Practice Git branching workflow
- [ ] Understand Netlify Deploy Previews
- [ ] Review Internal Service Catalog (credit costs)
- [ ] Shadow Triage Manager for 1 week

### Onboarding Checklist for Triage Managers

- [ ] Learn BOTH systems (You Capture We Create + Two Clocks)
- [ ] Understand all service tiers and packages
- [ ] Practice grooming tasks
- [ ] Learn when to upsell Wayfinder Digital
- [ ] Review client communication templates
- [ ] Understand credit tracking and overage handling

---

## Related Documentation

**You Capture We Create:**
- [You Capture We Create Workflow](/docs/04-management/you-capture-we-create-workflow) - Complete content workflow
- [Content Templates](/docs/02-marketing/templates/) - Content ideas and formats

**Two Clocks:**
- [Two Clocks Workflow](/docs/03-production/website-services/website/website-maintenance/two-clocks-workflow) - Complete website update workflow
- [Website Activation Types](/docs/01-sales/pricing) - LaunchPad and Authority Builder details

**Service Packages:**
- [Service Offering](/docs/01-sales/service-offering) - Complete service descriptions
- [Pricing Structure](/docs/01-sales/pricing) - All tiers and pricing

**Operations:**
- [CSM Workflow](/docs/04-management/csm-workflow) - Customer Success Manager responsibilities
- [Implementation Checklist](/docs/04-management/implementation-checklist) - Client onboarding steps

---

## Change Log

**v1.0.0 - November 10, 2025**
- Initial ClickUp Structure documentation created
- Complete breakdown of both systems
- Upgrade/downgrade scenarios documented
- Integration workflows defined

---

**Questions or updates needed?** Contact the Operations Director or Project Management Lead.
