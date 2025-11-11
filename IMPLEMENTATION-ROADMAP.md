# R7 Creative Implementation Roadmap
**Philosophy:** Working ClickUp System > Complex Documentation
**Last Updated:** November 11, 2025

---

## 🎯 Core Principle

**This documentation repo serves ONE purpose:**
- Central source of truth for pricing, service definitions, and brand messaging
- Everything else lives in ClickUp as operational systems

**Not for this repo:**
- Detailed process documentation
- Workflow guides
- Checklists that should be in ClickUp
- Meeting agendas
- Email templates (those live in ClickUp marketing list)

---

## 📋 What Stays in Docs (Minimal Source of Truth)

### ✅ Keep & Maintain:
1. **Pricing Structure** (`/docs/01-sales/pricing.md`)
   - Single source of truth for all pricing tiers
   - Founder vs Retail pricing
   - Add-on pricing
   - Website activation fees

2. **Service Offering Definitions** (`/docs/01-sales/service-offering.md`)
   - What each tier includes
   - What add-ons do
   - Deliverables per package

3. **Brand Messaging** (`/docs/02-marketing/brand-messaging/`)
   - Brand positioning
   - Copywriting guidelines
   - Voice & tone
   - Website content master files

4. **Role Definitions** (Simple job descriptions)
   - What the role does
   - Where they work in ClickUp
   - What forms/systems they use

5. **Client Qualification Criteria** (`/docs/01-sales/client-qualification.md`)
   - Who we serve
   - Red flags
   - Ideal client profile

### ❌ Move to ClickUp (Operational Systems):
- CSM Workflow → ClickUp task templates
- Meeting Agendas → ClickUp docs per client
- Email Templates → ClickUp marketing list
- Implementation Checklist → ClickUp onboarding template
- You Capture We Create Workflow → ClickUp automation + task lists
- Workflow Guide → ClickUp SOPs
- ClickUp Structure → Lives in ClickUp itself

---

## 🏗️ DEPENDENCY-BASED ROADMAP

### **PHASE 0: Foundation (Must Complete First)**
**Can't do anything else until this is done**

#### 0.1 Define Pricing Structure (COMPLETE)
- ✅ 5-tier internal structure documented
- ✅ 3-tier external structure documented
- ✅ Add-on pricing defined
- ✅ Website activation pricing defined

#### 0.2 Define Service Deliverables
- **File:** `/docs/01-sales/service-offering.md`
- **Task:** Finalize exactly what each tier includes
- **Why First:** Can't build ClickUp systems without knowing what services you deliver
- **Time:** 1 hour
- **Output:** Clear list of deliverables per tier

#### 0.3 Define Role Responsibilities
- **Files:** Create/update role definitions
  - Salesperson
  - Customer Service Manager (CSM)
  - Copywriter
  - Triage Manager
  - Website Dev (Fiverr freelancer)
  - Video Editor (Fiverr freelancer)
- **Task:** Simple bullet list for each role:
  - What they do
  - Where they work in ClickUp
  - What they hand off to whom
- **Why First:** Can't design ClickUp structure without knowing who does what
- **Time:** 2 hours
- **Output:** 6 simple role definition docs

---

### **PHASE 1: ClickUp Structure Design**
**Dependencies:** Phase 0 complete

#### 1.1 Design Client Folder Structure
- **Task:** Map out how client folders work in ClickUp
- **Key Questions:**
  - What lists does each client need?
  - What statuses do tasks move through?
  - What automations trigger handoffs?
- **Roles Involved:** CSM, Triage Manager, Copywriter
- **Time:** 2 hours
- **Output:** ClickUp hierarchy diagram (can sketch in docs, then build in ClickUp)

```
Client Folder (per client)
├── 📋 Onboarding
├── 📅 Content Calendar (You Capture We Create)
├── ✍️ Brand & Copy
├── 🌐 Website Updates (Two Clocks)
├── 📊 Reporting & Analytics
└── 💬 Client Communication
```

#### 1.2 Design ClickUp Form for Client Content Submission
- **Task:** Build ClickUp form that clients use to submit content
- **Handled By:** Triage Manager receives submissions
- **Action:** Triage Manager prepares content onto calendar/lists
- **Time:** 1 hour
- **Output:** Working ClickUp form

#### 1.3 Design ClickUp Form for Website Change Requests
- **Task:** Build ClickUp form for website update requests
- **Handled By:** Triage Manager receives, creates Two Clocks tasks
- **Assigned To:** Website Dev (Fiverr)
- **Time:** 1 hour
- **Output:** Working ClickUp form

#### 1.4 Create Task Templates
- **Task:** Build ClickUp task templates for:
  - Client onboarding checklist
  - Bi-weekly content cycle (You Capture We Create)
  - Website update request (Two Clocks)
  - Brand Strategy Meeting
  - Content Strategy Meeting
- **Time:** 3 hours
- **Output:** 5 task templates in ClickUp

---

### **PHASE 2: Freelancer Pricing & Agreements**
**Dependencies:** Phase 1.1 complete (know what work freelancers do)

#### 2.1 Define Freelancer Pricing
- **Task:** Determine pricing for:
  - **Video Editor (Fiverr):**
    - Per video edit
    - Bulk packages (if applicable)
    - Turnaround time expectations
  - **Website Dev (Fiverr):**
    - Per credit hour (Two Clocks system)
    - Bulk credit packages
    - Rush pricing (if applicable)
- **Why Now:** Need to ensure your client pricing covers freelancer costs + margin
- **Time:** 1 hour
- **Output:** Freelancer rate sheet

#### 2.2 Calculate Service Margin
- **Task:** Verify that client pricing covers:
  - Freelancer costs
  - Your time (CSM, Copywriter, Triage Manager)
  - Profit margin (target: 40-60%)
- **Why Now:** Ensure pricing is sustainable before signing clients
- **Time:** 1 hour
- **Output:** Margin analysis spreadsheet or doc

#### 2.3 Create Freelancer Onboarding Process
- **Task:** Simple checklist for bringing on Fiverr freelancers:
  - How they access ClickUp
  - How they submit completed work
  - Payment schedule
  - Quality standards
- **Time:** 1 hour
- **Output:** Freelancer onboarding checklist (can live in ClickUp)

---

### **PHASE 3: Service Agreements**
**Dependencies:** Phase 0 complete (pricing finalized)

#### 3.1 Update Service Agreement Template
- **File:** `/docs/04-management/service-agreements.md`
- **Task:** Revise agreement to include:
  - All 5 pricing tiers
  - LaunchPad website activation
  - Authority Builder website activation
  - On-Site Content Capture add-on
  - Local SEO Boost add-on
  - 30-day free trial terms
  - No contract / month-to-month terms
  - Founders pricing lock-in
- **Time:** 2 hours
- **Output:** Current service agreement template

#### 3.2 Review Signature Technology
- **Current:** Webpage + Jotform for signatures
- **Task:** Evaluate if this is working or if simpler option exists
- **Alternatives to Consider:**
  - PandaDoc
  - DocuSign
  - HelloSign
  - Keep current system if it works
- **Time:** 30 minutes (research) + implementation if changing
- **Output:** Decision + updated process

---

### **PHASE 4: Onboarding Processes (LAST)**
**Dependencies:** Everything else complete

#### 4.1 Sales → CSM Handoff
- **Task:** Define what Salesperson inputs for CSM
- **Where:** ClickUp form or client folder creation
- **Info Needed:**
  - Client name, contact info
  - Tier purchased
  - Add-ons purchased
  - Website activation type (if any)
  - Trial start date
  - Any special notes
- **Time:** 30 minutes
- **Output:** Handoff form/process in ClickUp

#### 4.2 CSM Client Onboarding
- **Task:** CSM walks client through:
  - Welcome email (template in ClickUp)
  - Schedule Brand Strategy Meeting
  - Send ClickUp content submission form
  - Set up Frame.io (if applicable)
  - Explain trial period
- **Time:** 1 hour
- **Output:** Onboarding task template in ClickUp (already created in Phase 1.4)

#### 4.3 Copywriter → Client Folder
- **Task:** Simple guide for Copywriter:
  - Where to save Brand Pillars (ClickUp doc in client folder)
  - Where to save Website Copy (ClickUp doc in client folder)
  - How to mark ready for review
- **Time:** 30 minutes
- **Output:** 1-page Copywriter guide (can live in ClickUp)

#### 4.4 Triage Manager Process
- **Task:** Simple checklist:
  - Check ClickUp forms daily (content submissions + website requests)
  - Content submissions → Add to client content calendar
  - Website requests → Create Two Clocks task, assign to Dev
  - Set priority/deadline
  - Notify CSM if urgent
- **Time:** 30 minutes
- **Output:** Daily checklist in ClickUp

---

## 📊 TOTAL TIME ESTIMATE

| Phase | Tasks | Time | Dependencies |
|-------|-------|------|--------------|
| **Phase 0: Foundation** | 3 tasks | ~3 hours | None - START HERE |
| **Phase 1: ClickUp Structure** | 4 tasks | ~7 hours | Phase 0 |
| **Phase 2: Freelancer Pricing** | 3 tasks | ~3 hours | Phase 1.1 |
| **Phase 3: Service Agreements** | 2 tasks | ~2.5 hours | Phase 0 |
| **Phase 4: Onboarding** | 4 tasks | ~2.5 hours | Phases 0-3 |
| **TOTAL** | **16 tasks** | **~18 hours** | Sequential |

---

## 🚀 EXECUTION SEQUENCE (In Order)

1. ✅ Define pricing structure (DONE)
2. Finalize service deliverables (1 hour)
3. Define role responsibilities (2 hours)
4. Design client folder structure (2 hours)
5. Build ClickUp forms (2 hours)
6. Create task templates (3 hours)
7. Define freelancer pricing (1 hour)
8. Calculate service margins (1 hour)
9. Create freelancer onboarding (1 hour)
10. Update service agreement template (2 hours)
11. Review signature technology (30 min)
12. Sales → CSM handoff (30 min)
13. CSM client onboarding (1 hour - leverage Phase 1 templates)
14. Copywriter guide (30 min)
15. Triage Manager checklist (30 min)

---

## 🎯 SUCCESS CRITERIA

You'll know this is working when:

1. **ClickUp is operational** - You can onboard a client entirely in ClickUp without referencing this documentation
2. **Roles are clear** - Each person knows exactly where to work and what to hand off
3. **Pricing is locked** - Service agreements reflect accurate pricing with healthy margins
4. **Freelancers integrate smoothly** - Fiverr devs/editors can pick up tasks from ClickUp and deliver
5. **Minimal documentation** - This repo only contains pricing, services, brand messaging (source of truth)

---

## 📂 REVISED DOCUMENTATION STRUCTURE

**What This Repo Should Contain (Final State):**

```
r7creative-docs/
├── 01-sales/
│   ├── pricing.md (SOURCE OF TRUTH)
│   ├── service-offering.md (WHAT each tier includes)
│   ├── client-qualification.md (WHO we serve)
│   └── media-capture-overview.md (WHAT it is, simplified)
│
├── 02-marketing/
│   └── brand-messaging/ (SOURCE OF TRUTH for voice/tone/copy)
│       ├── 01-brand-positioning.md
│       ├── 02-aeo-copywriting.md
│       └── website-content/ (master website copy files)
│
├── 03-production/
│   └── [Simple deliverable checklists per service]
│       ├── gbp-deliverables.md (WHAT we deliver)
│       ├── social-media-deliverables.md
│       ├── website-deliverables.md
│       └── review-acquisition-deliverables.md
│
├── 04-management/
│   ├── service-agreements.md (LEGAL templates)
│   └── role-definitions/ (WHO does WHAT)
│       ├── salesperson.md
│       ├── csm.md
│       ├── copywriter.md
│       ├── triage-manager.md
│       ├── website-dev.md
│       └── video-editor.md
│
└── 05-finance/
    └── pricing-strategy.md (WHY we price this way)
```

**What Moves to ClickUp:**
- All workflows
- All checklists
- All process documentation
- All meeting agendas
- All email templates
- All task management

---

## ✅ IMMEDIATE NEXT STEPS

**RIGHT NOW - You need to:**

1. **Review Phase 0.2** (Service Deliverables) - Make sure we have crystal clear list of what each tier delivers
2. **Complete Phase 0.3** (Role Definitions) - Who does what, where do they work
3. **Then proceed to Phase 1** - Design ClickUp structure based on roles and services

**Want me to:**
- Start with Phase 0.2 and help you finalize service deliverables?
- Draft the 6 role definitions (Phase 0.3)?
- Both?

This is the foundation - everything else depends on getting these right.

---

**Last Updated:** November 11, 2025
**Status:** Roadmap defined, awaiting Phase 0 completion
