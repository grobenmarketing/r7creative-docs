---
title: "You Capture We Create Workflow"
description: "Complete operational workflow for bi-weekly content management system with client captures, editing, review, and publishing"
weight: 15
tags: ["operations", "workflow", "content", "process", "client-management"]
status: "complete"
---
INPUT NEEDED: better to have it in clickup
# You Capture We Create Workflow

## Overview

This document outlines a content management system for clients, operating on a bi-weekly meeting cadence with Monday meetings to plan content for the following 3 weeks. Key deadlines include Friday 7 PM for client uploads, Tuesday noon for editor completion, Wednesday 5 PM for client feedback, and Friday afternoon for scheduling.

## Quick Reference Timeline

| Day | Action | Deadline | Status |
|-----|--------|----------|--------|
| **Bi-weekly Meeting** | Plan content, assign owners, set capture dates | Monday | IDEA → ASSIGNED |
| **Friday** | Client uploads via JotForm | 7 PM | ASSIGNED |
| **Monday** | PM merges uploads, assigns editors | Before noon | UPLOADED → EDITOR ASSIGNED |
| **Monday-Tuesday** | Editor works on content | N/A | EDITING |
| **Tuesday** | Editor completes, uploads to Frame.io | Noon | REVIEW READY |
| **Tuesday** | Internal review, send client notice | End of day | CLIENT REVIEW |
| **Wednesday** | Client reviews and provides feedback | 5 PM | CLIENT REVIEW |
| **Thursday-Friday** | Editor completes revisions | Friday noon | CLIENT REVIEW |
| **Friday** | PM schedules posts in Metricool + OneUP | Afternoon | SCHEDULED |
| **Post-Publication** | Archive completed content | As needed | ARCHIVED |

## Email Templates

### 1. Content Assignment Confirmation

**Subject:** "Content Capture Schedule for [Client Name] - [Date Range]"

Communicates assigned content owners, capture dates/times, locations, and upload deadlines. Emphasizes the Friday 7 PM deadline and notes that late submissions cannot be included in the following week's editing cycle.

### 2. Content Ready for Review

**Subject:** "Your Content is Ready for Review - Feedback Needed by Wednesday 5 PM"

Notifies clients that edited content is available on Frame.io with accompanying captions. Instructs clients to review and add comments directly to Frame.io. Specifies that clients may request one minor video/photo revision and one caption revision or complete rewrite. Notes that content not receiving feedback by Wednesday 5 PM will be approved automatically.

### 3. Revisions Complete

**Subject:** "Revised Content Ready - Scheduled for Publication"

Confirms completion of requested revisions and lists scheduled publication dates. Indicates this is the final version that will be published.

### 4. No Revisions - Content Approved

**Subject:** "Content Approved - Scheduled for Publication"

Notifies clients that content is approved and provides scheduled publication dates. Confirms content has been uploaded to Metricool (primary) and OneUP ($12/mo for GBP) for automatic scheduling.

### 5. Upload Reminder (Off-Week)

**Subject:** "Content Capture Reminder for [Client Name] - Due Friday 7 PM"

Provides midweek reminder of pending captures, includes assigned employee names, content titles, and locations, with JotForm upload link.

## ClickUp Structure

Each client maintains a dedicated folder containing:

**Content List** – Manages all content ideas and tasks
**Uploads List** – Houses JotForm submissions initially

**Custom Fields:**
- Content Owner
- Content Capture (Date & Time)
- Location
- Content Uploader (auto-populated from JotForm)
- Editor (dropdown)
- Revision Requested (Yes/No dropdown)

## Process Stages & Statuses

### Stage 1: IDEA

**Status:** IDEA (Active)

During client meetings, brainstorm content concepts including behind-the-scenes footage, employee candid photos, customer interactions, product/service discussions, and other relevant opportunities.

**Actions:**
1. Create new tasks in the client's Content list
2. Add content title
3. Include relevant details in task description
4. Assign a publication due date (populates calendar view)

### Stage 2: ASSIGNED

**Status:** ASSIGNED (Active)

**Actions:**
1. Assign content to specific employee (Content Owner)
2. Set Content Capture Date & Time – when content will be shot
3. Add Location – where content will be captured
4. Screenshot assignments and send to all meeting participants for accountability

The assigned employee must capture content at the specified date, time, and location, then upload through JotForm before Friday 7 PM. When submitting, employees enter their name in the "Your Name" field, which populates the Content Uploader field in ClickUp.

### Stage 3: UPLOADED

**Status:** UPLOADED (Active)
**Timeline:** Review between Friday 7 PM and Monday before noon

#### Merging Uploads with Content Items

Once a client submits files through JotForm:

1. Open the upload item in the Uploads list
2. Click the three-dot menu icon
3. Select "Merge"
4. Search for and select the corresponding Content list item
5. Complete the merge

This transfers all information and attachments from the Uploads list to the associated Content list item in ClickUp.

**Additional Actions After Merging:**
- Assign an Editor from dropdown menu
- Change status to EDITOR ASSIGNED

### Stage 4: EDITOR ASSIGNED → EDITING

**Status:** EDITOR ASSIGNED → EDITING (Active)
**Deadline:** Tuesday at noon

**Actions:**
1. Editor changes status to EDITING when beginning work
2. Editor completes edit by Tuesday noon
3. Editor uploads edited video to Frame.io and sets status to "New"
4. Editor copies Frame.io link and pastes as comment in ClickUp task
5. Editor changes ClickUp status to REVIEW READY

### Stage 5: REVIEW READY (Internal Review)

**Status:** REVIEW READY (Active)
**Timeline:** Tuesday at noon (after editor completion)

**Actions:**
1. Internal team reviews edited content via Frame.io link in ClickUp
2. Ensure content quality and finalize captions
3. Create caption text file
4. Upload both content and caption text file to client's Frame.io shared link
5. Complete this for all edited content ready for that week's review
6. By end of day Tuesday: Send client review email using ClickUp email template
7. Change ClickUp status to CLIENT REVIEW

**Important:** Clients can review content and captions on their Frame.io shared link. They have all day Wednesday to review and must provide feedback by Wednesday 5 PM. If no feedback is received by this deadline, content will be approved as-is.

### Stage 6: CLIENT REVIEW

**Status:** CLIENT REVIEW (Active)
**Client Review Window:** All day Wednesday
**Client Deadline:** Wednesday by 5 PM

**Client Rights:**
- One minor revision to video/photo content
- One revision to caption OR complete rewrite
- All feedback submitted via Frame.io comments by Wednesday 5 PM

**If No Feedback by Wednesday 5 PM:**
- Content is automatically approved
- Set Revision Requested dropdown to "No"
- Update Frame.io status to "Good to Go"
- Proceed directly to scheduling on Friday

**If Revisions Requested (by Wednesday 5 PM):**
1. Client adds Frame.io comments and changes status to "Revision Requested"
2. In ClickUp, set Revision Requested dropdown to "Yes"
3. @mention the editor in a ClickUp comment about the revision
4. Direct them to check the client's Frame.io link for specific feedback
5. Editor completes revisions by Friday at noon
6. Editor uploads revised version to Frame.io and changes status to "Revision Complete"
7. Editor copies Frame.io link and pastes as ClickUp comment
8. Remove old version from client's shared link

**Important Note:** Per client agreement, clients receive one revision round only. Edits follow discussions from meetings to avoid surprises. If unsatisfied, remind clients they can create another post. The content value lies in showing authentic moments that build trust with future customers.

### Stage 7: SCHEDULED

**Status:** SCHEDULED (Done)
**Timeline:** Friday afternoon (after noon revision deadline)

**Actions:**
1. Project Manager uploads all approved content and captions to Metricool (primary) and OneUP ($12/mo for GBP)
2. Schedule all posts to publish on their planned dates (per calendar view)
3. Change ClickUp status to SCHEDULED

## Frame.io Status Management

Frame.io uses the following statuses:
- **New** – Content just uploaded by editor
- **Good to Go** – Approved, no changes needed
- **Revision Requested** – Client has requested changes
- **Revision Complete** – Revisions completed by editor

**Editor Workflow:** Every time an editor uploads or updates content in Frame.io, they must copy the Frame.io link and paste it as a comment in the corresponding ClickUp task.

## Calendar & Accountability Tools

**During Meetings:**
- Share screen showing both Content list and calendar view
- Review scheduled content and pending captures

**After Meetings:**
- Screenshot spreadsheet view showing content title, assigned Content Owner, capture location, capture date/time, and upload deadline
- Send to all meeting participants

**JotForm Submission:**
- Employee enters name in "Your Name" field (becomes Content Uploader in ClickUp)
- Uploads content files
- Thank you page displays Friday 7 PM deadline
- Reminds users that late submissions cannot be included in next week's workflow

**Analogy:** The process operates like a newspaper's classified ad deadline—advertisements must be submitted by deadline to appear in Wednesday's edition. Similarly, late content submissions get pushed to the next available workflow cycle.

---

## Notes

This workflow represents a major service delivery operation that ensures consistent content production and client satisfaction through clear deadlines, structured review processes, and accountability at every stage.
