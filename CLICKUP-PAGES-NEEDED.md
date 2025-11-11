# ClickUp Pages & Documents Needed

**Purpose:** Comprehensive list of all pages/documents to create in ClickUp
**Philosophy:** ClickUp = Operational System | Docs Repo = Source of Truth (pricing, services, brand messaging)
**Created:** November 11, 2025

---

## 📂 STRUCTURE OVERVIEW

```
ClickUp Workspace
├── 🏢 Company Templates & SOPs
├── 👥 Role-Specific Guides
├── 📋 Forms (Client-Facing)
└── 👤 Per-Client Folders (Template to duplicate)
```

---

## 1️⃣ PER-CLIENT PAGES (Created for Each Client)

**Location:** Inside each client's folder
**Action:** Create a master "CLIENT TEMPLATE" folder with these pages, then duplicate for each new client

### 📁 Client Folder Structure
```
[CLIENT NAME] Folder
├── 📋 Onboarding Checklist (Task Template)
├── 📅 Content Calendar (List)
├── ✍️ Brand Assets (Doc)
├── 🌐 Website Updates - Two Clocks (List)
├── 📊 Reporting & Analytics (Doc)
└── 💬 Client Communication Log (Doc)
```

### Pages/Docs Per Client:

#### A. **Brand Assets** (ClickUp Doc)
- **Purpose:** Store client-specific brand pillars, messaging, copy
- **Sections:**
  - Brand Pillars (delivered after Brand Strategy Meeting)
  - Brand Positioning Statement
  - Target Audience Profile
  - Key Messages
  - Website Copy (if applicable)
  - Social Media Guidelines
- **Owned By:** Copywriter creates, CSM reviews with client

#### B. **Content Calendar** (ClickUp List with Calendar View)
- **Purpose:** Track all content pieces from submission → approval → scheduling → publishing
- **Statuses:**
  - Client Submitted (via form)
  - Triage Review
  - Ready to Schedule
  - Scheduled
  - Published
- **Assigned To:** Triage Manager → Video Editor/Social Media Manager

#### C. **Website Updates - Two Clocks** (ClickUp List)
- **Purpose:** Track website change requests and credit usage
- **Custom Fields:**
  - Credits Requested
  - Credits Approved
  - Credits Used
  - Remaining Balance
- **Statuses:**
  - Requested
  - Scoped
  - In Progress
  - Client Review
  - Completed
- **Assigned To:** Triage Manager → Website Dev (Fiverr)

#### D. **Onboarding Checklist** (Task Template)
- **Purpose:** Ensure systematic client onboarding with TTV milestones
- **Subtasks:**
  - [ ] Contract signed
  - [ ] Payment received
  - [ ] CRM account updated
  - [ ] Welcome email sent
  - [ ] ClickUp folder created
  - [ ] JotForm configured
  - [ ] Frame.io folder created (if applicable)
  - [ ] Brand Strategy Meeting scheduled
  - [ ] Brand Strategy Meeting completed
  - [ ] Brand Pillars delivered (TTV #1)
  - [ ] Content Strategy Meeting scheduled
  - [ ] Content Strategy Meeting completed
  - [ ] First 9-12 content pieces assigned
  - [ ] First content scheduled
  - [ ] First content published (TTV #2)
  - [ ] First Success Review scheduled (2 weeks post-publish)
- **Owned By:** CSM

#### E. **Meeting Notes** (ClickUp Docs - created as needed)
- Discovery Call - [DATE]
- Brand Strategy Meeting - [DATE]
- Content Strategy Meeting - [DATE]
- First Success Review - [DATE]
- Bi-Weekly Sync - [DATE]

#### F. **Client Communication Log** (ClickUp Doc)
- **Purpose:** Track all client communications in one place
- **Format:** Simple dated log
  - Date
  - Channel (email, phone, ClickUp comment, etc.)
  - Summary
  - Action items
  - Follow-up needed

#### G. **Reporting & Analytics** (ClickUp Doc - updated monthly)
- **Purpose:** Track client results and performance metrics
- **Sections:**
  - Content Published This Month
  - Engagement Metrics
  - GBP Performance (if applicable)
  - Website Traffic (if applicable)
  - Review Acquisition Results (if applicable)
  - Next Month Goals

---

## 2️⃣ COMPANY TEMPLATES & SOPs

**Location:** Company-wide "R7 Creative Operations" Space
**Action:** Create these once, reference across all clients

### A. Task Templates

#### **Template 1: Client Onboarding Checklist**
- (See Per-Client section above - this is the master template)

#### **Template 2: Bi-Weekly Content Cycle (You Capture We Create)**
- **Purpose:** Recurring task for clients on content packages
- **Frequency:** Every 2 weeks
- **Subtasks:**
  - [ ] Check for new client content submissions (ClickUp form)
  - [ ] Triage Manager reviews submissions
  - [ ] Assign to Content Calendar
  - [ ] Video Editor: Edit and prepare content
  - [ ] CSM: Review and approve
  - [ ] Schedule for publication
  - [ ] Publish content
  - [ ] Track engagement/results

#### **Template 3: Website Update Request (Two Clocks)**
- **Purpose:** Individual task for each website change request
- **Custom Fields:**
  - Credits Requested: [Number]
  - Credits Approved: [Number]
  - Credits Used: [Number]
- **Subtasks:**
  - [ ] Triage Manager reviews request
  - [ ] Estimate credits needed
  - [ ] Check client's credit balance
  - [ ] Get client approval (if over estimate)
  - [ ] Assign to Website Dev (Fiverr)
  - [ ] Dev completes work
  - [ ] CSM reviews with client
  - [ ] Update credit balance
  - [ ] Mark complete

#### **Template 4: Brand Strategy Meeting Prep**
- **Purpose:** Ensure CSM/Copywriter is ready for Brand Strategy call
- **Subtasks:**
  - [ ] Review client intake form responses
  - [ ] Research client's industry and competitors
  - [ ] Review client's current website/social media
  - [ ] Prepare Brand Strategy Meeting agenda
  - [ ] Send meeting link and prep email to client
  - [ ] Conduct Brand Strategy Meeting
  - [ ] Copywriter: Draft Brand Pillars within 2 days

#### **Template 5: Content Strategy Meeting Prep**
- **Purpose:** Plan first 9-12 content pieces with client
- **Subtasks:**
  - [ ] Review Brand Pillars with client
  - [ ] Identify content themes/topics
  - [ ] Determine content format preferences
  - [ ] Assign first 9-12 content pieces
  - [ ] Add to client's Content Calendar
  - [ ] Send client ClickUp content submission form

#### **Template 6: Monthly Client Success Review**
- **Purpose:** Recurring monthly check-in with client
- **Frequency:** Monthly (after first success review at 2 weeks)
- **Subtasks:**
  - [ ] Pull performance metrics
  - [ ] Update Client Reporting & Analytics doc
  - [ ] Schedule meeting with client
  - [ ] Review results and plan next month
  - [ ] Document action items

### B. Standard Operating Procedures (SOPs)

#### **SOP 1: CSM Workflow**
- **File to migrate:** `content/docs/04-management/csm-workflow.md`
- **Purpose:** Day-to-day responsibilities and processes
- **Sections:**
  - Daily tasks
  - Weekly tasks
  - Monthly tasks
  - Client communication best practices
  - Escalation procedures

#### **SOP 2: Triage Manager Daily Checklist**
- **Purpose:** Ensure all client submissions are processed
- **Daily Tasks:**
  - [ ] Check ClickUp content submission forms
  - [ ] Check ClickUp website update request forms
  - [ ] Triage content submissions → Add to client Content Calendar
  - [ ] Triage website requests → Create Two Clocks task, assign to Dev
  - [ ] Set priority/deadlines
  - [ ] Notify CSM if urgent requests
  - [ ] Update client credit balances (Two Clocks)
  - [ ] Respond to any client questions in ClickUp comments

#### **SOP 3: Copywriter Workflow**
- **Purpose:** How to create and deliver Brand Pillars and website copy
- **Process:**
  - Receive Brand Strategy Meeting notes from CSM
  - Draft Brand Pillars (within 2 days of meeting)
  - Save in client's "Brand Assets" ClickUp doc
  - Mark task complete, notify CSM
  - CSM reviews with client, gathers feedback
  - Copywriter revises if needed
  - Final version locked in Brand Assets doc

#### **SOP 4: Video Editor Workflow (Fiverr Freelancer)**
- **Purpose:** How to access, edit, and deliver client content
- **Process:**
  - Receive task assignment in ClickUp (from Triage Manager)
  - Access client's raw content (Frame.io or ClickUp uploads)
  - Edit according to R7 Creative standards
  - Upload final video to ClickUp task
  - Mark task complete
  - CSM reviews and approves

#### **SOP 5: Website Dev Workflow (Fiverr Freelancer - Two Clocks)**
- **Purpose:** How to handle website update requests
- **Process:**
  - Receive Two Clocks task in ClickUp
  - Review request and estimated credits
  - Complete work on client's website
  - Document actual credits used
  - Add before/after screenshots to task
  - Mark task complete
  - Triage Manager updates client's credit balance

#### **SOP 6: Sales → CSM Handoff**
- **Purpose:** What info Salesperson provides to CSM for new clients
- **Process:**
  - Salesperson fills out "New Client Handoff" form in ClickUp
  - Form creates task assigned to CSM
  - CSM receives:
    - Client name, contact info
    - Tier purchased
    - Add-ons purchased
    - Website activation type (if any)
    - Trial start date
    - Special notes/requests
  - CSM creates client folder from template
  - CSM starts onboarding checklist

#### **SOP 7: You Capture We Create - Bi-Weekly Process**
- **File to migrate:** `content/docs/04-management/you-capture-we-create-workflow.md`
- **Purpose:** Step-by-step process for content submission → publication
- **Phases:**
  1. Client submits content via ClickUp form
  2. Triage Manager reviews and adds to Content Calendar
  3. Video Editor/Social Media Manager edits/prepares
  4. CSM reviews and approves
  5. Content scheduled for publication
  6. Content published
  7. Engagement tracked

#### **SOP 8: Two Clocks Workflow**
- **File to migrate:** `content/docs/03-production/website-services/website/website-maintenance/two-clocks-workflow.md`
- **Purpose:** How to manage website update credits
- **Process:**
  - Client submits website update request via form
  - Triage Manager creates Two Clocks task
  - Estimate credits needed
  - Check client's credit balance
  - Get approval if estimate exceeds balance
  - Assign to Website Dev
  - Track actual credits used
  - Update client's remaining balance
  - Invoice for additional credits if needed

#### **SOP 9: GBP Optimization Process**
- **Files to migrate:** All from `content/docs/03-production/google-business-profile/`
- **Purpose:** Step-by-step checklist for optimizing client's Google Business Profile
- **Checklist:**
  - [ ] Complete business information
  - [ ] Write optimized business description
  - [ ] Add services with keywords
  - [ ] Upload photos (per guidelines)
  - [ ] Select attributes
  - [ ] Set up weekly posts schedule
  - [ ] Implement review request system
  - [ ] Monitor and respond to Q&A

#### **SOP 10: Media Capture Process**
- **Files to migrate:**
  - `content/docs/03-production/media-capture/pre-capture-planning.md`
  - `content/docs/03-production/media-capture/capture-day-procedures.md`
  - `content/docs/03-production/media-capture/post-capture-pipeline.md`
- **Purpose:** End-to-end process for On-Site Content Capture add-on
- **Phases:**
  1. Pre-Capture Planning
  2. Capture Day Procedures
  3. Post-Capture Pipeline

#### **SOP 11: Review Acquisition Implementation**
- **Files to migrate:**
  - `content/docs/03-production/review-acquisition/Review-Acquisition-Framework.md`
  - `content/docs/03-production/review-acquisition/Client-Implementation-Guide.md`
  - `content/docs/03-production/review-acquisition/Training-Video-Scripts.md`
- **Purpose:** How to implement review acquisition system for clients
- **Process:**
  - Setup and configuration
  - Client training
  - Ongoing management

#### **SOP 12: Operations Guide**
- **File to migrate:** `content/docs/04-management/operations-guide.md`
- **Purpose:** Overall company operations overview
- **Sections:**
  - Team structure
  - Communication channels
  - Tool stack
  - Standard workflows

### C. Email Templates

**Location:** ClickUp "Email Templates" List

**File to migrate:** `content/docs/04-management/email-templates.md`

#### Email Template 1: Welcome Email (Post-Contract)
- **Subject:** Welcome to R7 Creative! Your Journey Starts Now
- **Purpose:** First touchpoint after contract signed
- **Includes:**
  - Thank you for choosing R7
  - What happens next
  - Trial period details (30 days)
  - Link to schedule Brand Strategy Meeting
  - Contact info for CSM

#### Email Template 2: Brand Strategy Meeting Confirmation
- **Subject:** Brand Strategy Meeting Scheduled - [DATE/TIME]
- **Purpose:** Confirm meeting and set expectations
- **Includes:**
  - Meeting link
  - What to prepare
  - How long it will take
  - What to expect

#### Email Template 3: Brand Pillars Delivery (TTV #1)
- **Subject:** Your Brand Pillars Are Ready! 🎯
- **Purpose:** Deliver first major value milestone
- **Includes:**
  - Link to Brand Pillars doc in ClickUp
  - Explanation of what they mean
  - Request for feedback
  - Schedule Content Strategy Meeting

#### Email Template 4: Content Strategy Meeting Confirmation
- **Subject:** Content Strategy Meeting Scheduled - [DATE/TIME]
- **Purpose:** Confirm meeting and explain content submission process
- **Includes:**
  - Meeting link
  - What to bring (content ideas, past content)
  - Content submission form link
  - How "You Capture We Create" works

#### Email Template 5: First Content Published (TTV #2)
- **Subject:** Your Content is LIVE! 🚀
- **Purpose:** Celebrate first published content
- **Includes:**
  - Link to published content
  - What's coming next
  - How to submit more content
  - Schedule First Success Review (in 2 weeks)

#### Email Template 6: First Success Review Invitation
- **Subject:** Let's Celebrate Your First Wins! 📊
- **Purpose:** Schedule review 2 weeks after first publish
- **Includes:**
  - Meeting link
  - Preview of results/metrics
  - What to expect in the review

#### Email Template 7: Bi-Weekly Sync Reminder
- **Subject:** Bi-Weekly Sync - [DATE/TIME]
- **Purpose:** Recurring check-in reminder
- **Includes:**
  - Meeting link
  - Agenda
  - Recent wins/metrics
  - Questions to discuss

#### Email Template 8: Trial Ending Soon (21-day mark)
- **Subject:** Your 30-Day Trial Ends Soon - Let's Talk!
- **Purpose:** Prepare client for trial end, confirm continuation
- **Includes:**
  - Trial end date
  - Results achieved so far
  - What happens next (billing starts)
  - Option to adjust tier or cancel

#### Email Template 9: Trial End - Welcome to Full Service
- **Subject:** Welcome to [TIER NAME]! Here's What's Next
- **Purpose:** Transition from trial to paid service
- **Includes:**
  - Billing details
  - Founders pricing confirmation (if applicable)
  - Full service access
  - Next steps

#### Email Template 10: Website Update Request Received
- **Subject:** Website Update Request Received - Estimated [X] Credits
- **Purpose:** Confirm receipt of website change request
- **Includes:**
  - Summary of request
  - Estimated credits needed
  - Current credit balance
  - Estimated completion date
  - Approval request (if credits needed)

#### Email Template 11: Two Clocks Credit Balance Low
- **Subject:** Website Credits Running Low - Time to Refill?
- **Purpose:** Proactively notify when credits below threshold
- **Includes:**
  - Current balance
  - Average monthly usage
  - Link to purchase more credits
  - Bulk credit packages available

#### Email Template 12: Monthly Success Review
- **Subject:** Your Monthly Results Are In! 📈
- **Purpose:** Share monthly performance report
- **Includes:**
  - Link to Reporting & Analytics doc
  - Key wins
  - Areas for improvement
  - Next month strategy
  - Meeting link (if applicable)

### D. Meeting Agenda Templates

**Location:** ClickUp "Meeting Agendas" Folder

**File to migrate:** `content/docs/04-management/meeting-agendas.md`

#### Meeting Agenda 1: Discovery Call (Sales → CSM Pass-off)
- **Purpose:** Initial call with prospective client
- **Duration:** 30-45 minutes
- **Agenda:**
  1. Introduction and rapport building
  2. Current marketing challenges
  3. Business goals and objectives
  4. Ideal client/customer profile
  5. Current marketing efforts
  6. R7 Creative service overview
  7. Pricing and tier recommendation
  8. Questions and next steps

#### Meeting Agenda 2: Brand Strategy Meeting
- **Purpose:** Deep dive into client's brand and positioning
- **Duration:** 60-90 minutes
- **Agenda:**
  1. Business background and story
  2. Target audience deep dive
  3. Unique value proposition
  4. Brand personality and voice
  5. Competitive positioning
  6. Brand pillars definition
  7. Next steps (Content Strategy Meeting)

#### Meeting Agenda 3: Content Strategy Meeting
- **Purpose:** Plan first 9-12 content pieces
- **Duration:** 60 minutes
- **Agenda:**
  1. Review Brand Pillars
  2. Content themes and topics brainstorm
  3. Content format preferences (video, photo, text)
  4. Content submission process walkthrough
  5. Assign first 9-12 content pieces
  6. Set expectations for publishing timeline
  7. Next steps

#### Meeting Agenda 4: First Success Review (2 weeks post-publish)
- **Purpose:** Celebrate early wins, gather feedback
- **Duration:** 30 minutes
- **Agenda:**
  1. Review first published content
  2. Engagement metrics review
  3. Client feedback and satisfaction
  4. Adjustments needed
  5. Plan next content batch
  6. Questions and next steps

#### Meeting Agenda 5: Bi-Weekly Sync
- **Purpose:** Ongoing check-in and alignment
- **Duration:** 30 minutes
- **Agenda:**
  1. Recent content review
  2. Performance metrics update
  3. Upcoming content plan
  4. Questions or requests
  5. Action items and next steps

#### Meeting Agenda 6: Monthly Success Review
- **Purpose:** Comprehensive monthly performance review
- **Duration:** 45-60 minutes
- **Agenda:**
  1. Month-over-month performance review
  2. Key wins and highlights
  3. Challenges and opportunities
  4. Strategy adjustments for next month
  5. New initiatives or add-on services
  6. Client feedback and satisfaction
  7. Action items

---

## 3️⃣ ROLE-SPECIFIC GUIDES

**Location:** ClickUp "Team Resources" Space

**Purpose:** Simple 1-page guide for each role defining what they do, where they work, what they hand off

### Guide 1: Salesperson
- **What they do:**
  - Conduct Discovery Calls
  - Qualify leads
  - Present pricing and service tiers
  - Close deals
  - Hand off to CSM
- **Where they work in ClickUp:**
  - Sales Pipeline list
  - New Client Handoff form
- **What they hand off:**
  - Completed "New Client Handoff" form to CSM
  - Contract and payment confirmation
  - Any special client notes or requests

### Guide 2: Customer Service Manager (CSM)
- **What they do:**
  - Client onboarding
  - Facilitate Brand Strategy and Content Strategy meetings
  - Ongoing client communication
  - Review and approve content before publishing
  - Monthly success reviews
  - Client retention and satisfaction
- **Where they work in ClickUp:**
  - Client folders (all sections)
  - Email templates
  - Meeting agendas
- **What they hand off:**
  - Brand Strategy notes to Copywriter
  - Content approval to Triage Manager (for scheduling/publishing)
  - Client issues to appropriate team member

### Guide 3: Copywriter
- **What they do:**
  - Attend Brand Strategy meetings (or review notes)
  - Create Brand Pillars (within 2 days)
  - Write website copy (if client has website activation)
  - Write social media captions (if requested)
  - Maintain brand voice consistency
- **Where they work in ClickUp:**
  - Client "Brand Assets" docs
  - Website copy tasks
- **What they hand off:**
  - Brand Pillars to CSM for client review
  - Website copy to Website Dev (via CSM)
  - Social media copy to Triage Manager (for scheduling)

### Guide 4: Triage Manager
- **What they do:**
  - Monitor ClickUp forms daily
  - Process client content submissions
  - Process website update requests
  - Add content to client Content Calendars
  - Create Two Clocks tasks for website updates
  - Assign tasks to freelancers
  - Track Two Clocks credit balances
  - Notify CSM of urgent requests
- **Where they work in ClickUp:**
  - ClickUp Forms inbox
  - Client Content Calendars (all clients)
  - Client Website Updates lists (all clients)
  - Freelancer task assignments
- **What they hand off:**
  - Content tasks to Video Editor
  - Website tasks to Website Dev
  - Urgent requests to CSM

### Guide 5: Website Dev (Fiverr Freelancer)
- **What they do:**
  - Receive website update tasks from Triage Manager
  - Review request and credit estimate
  - Complete website changes/updates
  - Document actual credits used
  - Upload screenshots or proof of work
  - Mark tasks complete
- **Where they work in ClickUp:**
  - Client "Website Updates - Two Clocks" lists (assigned tasks only)
- **What they hand off:**
  - Completed work back to Triage Manager (task completion)
  - Actual credits used (for billing)

### Guide 6: Video Editor (Fiverr Freelancer)
- **What they do:**
  - Receive content editing tasks from Triage Manager
  - Access client raw content (Frame.io or ClickUp)
  - Edit video/photos per R7 Creative standards
  - Upload final content to ClickUp task
  - Mark tasks complete
- **Where they work in ClickUp:**
  - Client Content Calendar lists (assigned tasks only)
  - Frame.io (for raw content access)
- **What they hand off:**
  - Edited content back to CSM (via task completion)

---

## 4️⃣ FORMS (Client-Facing)

**Location:** ClickUp Forms (public links sent to clients)

### Form 1: New Client Intake Form
- **Purpose:** Gather initial client information (completed during/after Discovery Call)
- **Filled By:** Client (with Salesperson's help)
- **Creates:** Task in Sales Pipeline
- **Fields:**
  - Business name
  - Contact information (name, email, phone)
  - Website URL (if exists)
  - Business description
  - Target audience
  - Current marketing efforts
  - Biggest marketing challenge
  - Goals and objectives
  - Tier interest
  - How did you hear about us?

### Form 2: Client Content Submission Form
- **Purpose:** Clients submit content for "You Capture We Create" service
- **Filled By:** Client
- **Creates:** Task in client's Content Calendar
- **Assigned To:** Triage Manager
- **Fields:**
  - Content type (video, photo, testimonial, etc.)
  - Upload files or provide links
  - Caption/description (if any)
  - Hashtags/keywords (optional)
  - Publishing preference (ASAP, specific date, no preference)
  - Additional notes

### Form 3: Website Update Request Form
- **Purpose:** Clients request website changes via Two Clocks system
- **Filled By:** Client
- **Creates:** Task in client's "Website Updates - Two Clocks" list
- **Assigned To:** Triage Manager (who then assigns to Website Dev)
- **Fields:**
  - Type of update (text change, image update, new page, functionality change, etc.)
  - Page/location on website
  - Detailed description of request
  - Urgency (normal, rush)
  - Attach files (if applicable)
  - Additional notes

### Form 4: New Client Handoff (Sales → CSM)
- **Purpose:** Salesperson hands off new client to CSM
- **Filled By:** Salesperson
- **Creates:** Task assigned to CSM
- **Fields:**
  - Client name
  - Contact information
  - Tier purchased
  - Add-ons purchased (checkboxes):
    - [ ] On-Site Content Capture
    - [ ] Local SEO Boost
  - Website activation type:
    - [ ] None
    - [ ] LaunchPad (2-page)
    - [ ] Authority Builder (5-page)
  - Pricing type:
    - [ ] Founders Pricing (locked in)
    - [ ] Retail Pricing
  - Trial start date
  - Contract signed date
  - Payment received date
  - Special notes or requests
  - Next steps/action items

### Form 5: Client Feedback Form
- **Purpose:** Gather client satisfaction feedback (sent periodically)
- **Filled By:** Client
- **Creates:** Task assigned to CSM
- **Fields:**
  - Overall satisfaction (1-10 scale)
  - Content quality (1-10 scale)
  - Communication responsiveness (1-10 scale)
  - Results/ROI satisfaction (1-10 scale)
  - What's working well?
  - What could be improved?
  - Additional services interested in?
  - Likelihood to refer R7 Creative (1-10 scale)
  - Additional comments

---

## 5️⃣ DASHBOARDS & VIEWS

**Location:** ClickUp custom dashboards

### Dashboard 1: CSM Daily Dashboard
- **Purpose:** CSM sees all active clients and pending tasks at a glance
- **Widgets:**
  - My Tasks (due today, overdue)
  - Client Onboarding Status (all active onboardings)
  - Content Pending Approval
  - Upcoming Meetings This Week
  - New Form Submissions (content + website requests)
  - Client Satisfaction Scores (recent feedback)

### Dashboard 2: Triage Manager Dashboard
- **Purpose:** Triage Manager sees all incoming submissions and assignments
- **Widgets:**
  - New Content Submissions (from forms)
  - New Website Update Requests (from forms)
  - Content Calendar - All Clients (needs triage status)
  - Tasks Assigned to Freelancers (in progress)
  - Two Clocks Credit Balances (all clients, sorted low to high)

### Dashboard 3: Company Overview Dashboard
- **Purpose:** Leadership view of all clients and performance
- **Widgets:**
  - Active Clients Count
  - Clients by Tier (breakdown)
  - Monthly Recurring Revenue (MRR)
  - New Clients This Month
  - Churn This Month
  - Content Published This Month (all clients)
  - Average Client Satisfaction Score
  - Tasks by Status (company-wide)

### Dashboard 4: Sales Pipeline Dashboard
- **Purpose:** Track prospective clients through sales process
- **Widgets:**
  - Sales Pipeline (board view)
  - Discovery Calls This Week
  - Proposals Sent (awaiting decision)
  - Deals Won This Month
  - Deals Lost This Month
  - Revenue Forecast

---

## 6️⃣ AUTOMATIONS

**Purpose:** Reduce manual work and ensure consistency

### Automation 1: New Client Handoff → Create Client Folder
- **Trigger:** New Client Handoff form submitted
- **Action:**
  - Create new folder from "CLIENT TEMPLATE"
  - Rename folder to client name
  - Create onboarding checklist task assigned to CSM
  - Send welcome email to client (from template)

### Automation 2: Brand Pillars Delivered → Schedule Content Strategy
- **Trigger:** "Brand Pillars delivered" subtask marked complete in Onboarding Checklist
- **Action:**
  - Create task "Schedule Content Strategy Meeting" assigned to CSM
  - Send email to client (Brand Pillars delivery template)

### Automation 3: Content Submission → Notify Triage Manager
- **Trigger:** Client Content Submission form received
- **Action:**
  - Create task in client's Content Calendar
  - Assign to Triage Manager
  - Set status to "Client Submitted"
  - Send notification to Triage Manager

### Automation 4: Website Update Request → Notify Triage Manager
- **Trigger:** Website Update Request form received
- **Action:**
  - Create task in client's "Website Updates - Two Clocks" list
  - Assign to Triage Manager
  - Set status to "Requested"
  - Send notification to Triage Manager

### Automation 5: Two Clocks Credits Low → Notify CSM
- **Trigger:** Client's Two Clocks credit balance drops below 5 credits
- **Action:**
  - Create task for CSM to notify client
  - Send email to client (credit balance low template)

### Automation 6: Trial Ending Soon → Notify CSM
- **Trigger:** 21 days after trial start date
- **Action:**
  - Create task for CSM to contact client
  - Send email to client (trial ending soon template)

### Automation 7: First Content Published → Schedule Success Review
- **Trigger:** First content task marked "Published" in client's Content Calendar
- **Action:**
  - Create task "Schedule First Success Review" (due in 2 weeks)
  - Assign to CSM
  - Send email to client (first content published template)

### Automation 8: Monthly Recurring Task → Bi-Weekly Sync
- **Trigger:** Every 2 weeks (per client schedule)
- **Action:**
  - Create "Bi-Weekly Sync" task assigned to CSM
  - Send reminder email to client
  - Update Reporting & Analytics doc prompt

---

## 7️⃣ FREELANCER ONBOARDING RESOURCES

**Location:** ClickUp "Freelancer Resources" Space

### Resource 1: Freelancer Onboarding Checklist
- **Purpose:** Ensure smooth onboarding of Fiverr freelancers
- **Checklist:**
  - [ ] Add freelancer as ClickUp guest user
  - [ ] Assign to appropriate lists only (limited access)
  - [ ] Send welcome email with ClickUp login
  - [ ] Share role-specific guide (Video Editor or Website Dev)
  - [ ] Review quality standards and expectations
  - [ ] Explain payment schedule and invoicing
  - [ ] Provide access to Frame.io (Video Editors only)
  - [ ] Assign first test task
  - [ ] Review completed test task
  - [ ] Provide feedback
  - [ ] Approve for ongoing work

### Resource 2: Video Editor Quality Standards
- **Purpose:** Define R7 Creative video editing standards
- **Sections:**
  - Video specs (resolution, format, length)
  - Branding guidelines (intro/outro, logos)
  - Caption/text overlay standards
  - Music/audio guidelines
  - Export settings
  - Naming conventions
  - File delivery process

### Resource 3: Website Dev Quality Standards
- **Purpose:** Define R7 Creative website development standards
- **Sections:**
  - Coding standards (clean, commented)
  - Browser compatibility requirements
  - Mobile responsiveness standards
  - SEO best practices
  - Site speed expectations
  - Testing checklist
  - Documentation requirements (what was changed)
  - Screenshot/proof of work requirements

### Resource 4: Freelancer Payment Schedule
- **Purpose:** Clear payment terms for freelancers
- **Details:**
  - Payment frequency (weekly, bi-weekly, per task)
  - Invoice submission process
  - Payment method (Fiverr, PayPal, etc.)
  - Rate sheet (per video, per credit hour, etc.)
  - Bulk pricing (if applicable)
  - Rush pricing (if applicable)

---

## 📊 SUMMARY: TOTAL PAGES NEEDED

| Category | Count | Notes |
|----------|-------|-------|
| **Per-Client Pages** | 7 per client | Brand Assets, Content Calendar, Website Updates, Onboarding, Meeting Notes, Comm Log, Reporting |
| **Task Templates** | 6 | Onboarding, Bi-Weekly Cycle, Website Update, Brand Strategy Prep, Content Strategy Prep, Monthly Review |
| **SOPs** | 12 | CSM, Triage, Copywriter, Video Editor, Website Dev, Sales Handoff, YCWC, Two Clocks, GBP, Media Capture, Review Acquisition, Operations |
| **Email Templates** | 12 | Welcome, meetings, deliverables, reviews, billing, updates |
| **Meeting Agendas** | 6 | Discovery, Brand Strategy, Content Strategy, First Success, Bi-Weekly, Monthly |
| **Role Guides** | 6 | Salesperson, CSM, Copywriter, Triage Manager, Website Dev, Video Editor |
| **Forms** | 5 | Client Intake, Content Submission, Website Update, CSM Handoff, Feedback |
| **Dashboards** | 4 | CSM, Triage, Company Overview, Sales Pipeline |
| **Automations** | 8 | Handoff, deliverables, notifications, recurring tasks |
| **Freelancer Resources** | 4 | Onboarding, Video Quality, Website Quality, Payment Schedule |

**TOTAL:** ~70 pages/components to create in ClickUp

---

## ✅ MIGRATION CHECKLIST

**Files to Move from Docs Repo → ClickUp:**

- [ ] `/docs/04-management/csm-workflow.md` → SOP
- [ ] `/docs/04-management/email-templates.md` → Email Templates List
- [ ] `/docs/04-management/implementation-checklist.md` → Onboarding Task Template
- [ ] `/docs/04-management/meeting-agendas.md` → Meeting Agenda Templates
- [ ] `/docs/04-management/workflow-guide.md` → SOPs
- [ ] `/docs/04-management/you-capture-we-create-workflow.md` → SOP
- [ ] `/docs/04-management/operations-guide.md` → SOP
- [ ] `/docs/04-management/clickup-structure.md` → (Lives in ClickUp itself, delete from docs)
- [ ] `/docs/03-production/google-business-profile/*` → GBP SOP
- [ ] `/docs/03-production/media-capture/*` → Media Capture SOP
- [ ] `/docs/03-production/review-acquisition/*` → Review Acquisition SOP
- [ ] `/docs/03-production/website-services/website/website-maintenance/two-clocks-workflow.md` → Two Clocks SOP

**Total Files to Migrate:** 12+ files

---

## 🎯 RECOMMENDED BUILD SEQUENCE

**Phase 1: Core Infrastructure** (Build these first)
1. Create CLIENT TEMPLATE folder structure
2. Build 5 ClickUp Forms
3. Create 6 Task Templates
4. Set up 4 Dashboards

**Phase 2: Content & Documentation**
5. Create 12 Email Templates
6. Create 6 Meeting Agendas
7. Write 6 Role Guides
8. Migrate 12 SOPs from docs repo

**Phase 3: Automation & Optimization**
9. Set up 8 Automations
10. Create Freelancer Resources
11. Test entire system with dummy client

**Phase 4: Launch**
12. Train team on ClickUp system
13. Migrate first real client
14. Iterate based on feedback

---

**Last Updated:** November 11, 2025
**Status:** Ready for implementation
