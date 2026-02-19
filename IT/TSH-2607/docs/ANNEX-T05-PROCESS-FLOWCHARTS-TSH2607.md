# ANNEX-T05-PROCESS-FLOWCHARTS-TSH2607.md

# ANNEX T5: SAMPLE PROCESS FLOWCHARTS
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T5  
**Version:** 1.0  
**Date:** February 2026  

---

## TABLE OF CONTENTS

1. [Flowchart Notation](#1-flowchart-notation)
2. [Master Data Management Flows](#2-master-data-management-flows)
3. [Claims Processing Flows](#3-claims-processing-flows)
4. [Payment Processing Flows](#4-payment-processing-flows)
5. [Approval Workflow Flows](#5-approval-workflow-flows)
6. [Integration Flows](#6-integration-flows)

---

## 1. FLOWCHART NOTATION

### 1.1 BPMN 2.0 Symbols Used

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                              BPMN 2.0 NOTATION LEGEND                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  FLOW OBJECTS                                                                            │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐                   │
│  │     [Start]       │  │   [Activity]      │  │    {Gateway}      │                   │
│  │       ●           │  │   ┌─────────┐     │  │      ◇            │                   │
│  │   Event (Circle)  │  │   │  Task   │     │  │  Decision (Diamond)│                   │
│  └───────────────────┘  │   └─────────┘     │  └───────────────────┘                   │
│                         └───────────────────┘                                            │
│                                                                                          │
│  CONNECTING OBJECTS                                                                      │
│  ┌───────────────────┐  ┌───────────────────┐                                            │
│  │  ─────────────►   │  │  - - - - - - - ►  │                                            │
│  │  Sequence Flow    │  │  Message Flow     │                                            │
│  │  (Solid line)     │  │  (Dashed line)    │                                            │
│  └───────────────────┘  └───────────────────┘                                            │
│                                                                                          │
│  SWIMLANES                                                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │ DUSP / CONTRACTOR                                                                │   │
│  ├─────────────────────────────────────────────────────────────────────────────────┤   │
│  │ MCMC STAFF                                                                       │   │
│  ├─────────────────────────────────────────────────────────────────────────────────┤   │
│  │ UCMS SYSTEM                                                                      │   │
│  ├─────────────────────────────────────────────────────────────────────────────────┤   │
│  │ EXTERNAL SYSTEMS                                                                 │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. MASTER DATA MANAGEMENT FLOWS

### 2.1 Project ID Creation Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    PROJECT ID CREATION PROCESS                                           │
│                    (BPMN Swimlane Diagram)                                               │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────┬─────────────────┬─────────────────┬─────────────────┐              │
│  │   MCMC STAFF    │  UCMS SYSTEM    │   APPROVAL      │   NOTIFICATION  │              │
│  │                 │                 │   WORKFLOW      │   SERVICE       │              │
│  ├─────────────────┼─────────────────┼─────────────────┼─────────────────┤              │
│  │                 │                 │                 │                 │              │
│  │  ●──────────┐   │                 │                 │                 │              │
│  │  START      │   │                 │                 │                 │              │
│  │  (Project   │   │                 │                 │                 │              │
│  │  Officer)   │   │                 │                 │                 │              │
│  │             │   │                 │                 │                 │              │
│  │  [Enter     │   │                 │                 │                 │              │
│  │   Project   │   │                 │                 │                 │              │
│  │   Details]  │   │                 │                 │                 │              │
│  │             ├───┼────────────────►│                 │                 │              │
│  │             │   │                 │                 │                 │              │
│  │             │   │  [Validate      │                 │                 │              │
│  │             │   │   Project Data] │                 │                 │              │
│  │             │   │        │        │                 │                 │              │
│  │             │   │        ▼        │                 │                 │              │
│  │             │   │    {Valid?}     │                 │                 │              │
│  │             │   │       ◇         │                 │                 │              │
│  │◄────────────┼───┼──No─────────────┤                 │                 │              │
│  │ [Show Error │   │                 │                 │                 │              │
│  │  Messages]  │   │                 │                 │                 │              │
│  │       │     │   │                 │                 │                 │              │
│  │       └─────┼───┼─────────────────┤                 │                 │              │
│  │             │   │                 │                 │                 │              │
│  │             │   │────Yes─────────►│                 │                 │              │
│  │             │   │                 │  [Submit for   │                 │              │
│  │             │   │                 │   Approval]     │                 │              │
│  │             │   │                 │        │        │                 │              │
│  │             │   │                 │        ▼        │                 │              │
│  │             │   │                 │  {Approver     │                 │              │
│  │             │   │                 │   Decision}     │                 │              │
│  │             │   │                 │       ◇         │                 │              │
│  │◄────────────┼───┼◄──────────────Rejected────────────┤                 │              │
│  │ [Notify     │   │                 │                 │                 │              │
│  │  Rejection] │   │                 │                 │                 │              │
│  │             │   │                 │                 │                 │              │
│  │             │   │◄─────────────Approved─────────────►│                 │              │
│  │             │   │  [Generate    │                 │                 │              │
│  │             │   │   Project ID] │                 │                 │              │
│  │             │   │        │        │                 │                 │              │
│  │             │   │        ▼        │                 │                 │              │
│  │             │   │  [Sync to       │                 │                 │              │
│  │             │   │   USPFS]        │                 │                 │              │
│  │             │   │        │        │                 │                 │              │
│  │             │   │        └───────►│                 │  [Send Email    │              │
│  │             │   │                 │─────────────────┼───to DUSP]      │              │
│  │             │   │                 │                 │        │        │              │
│  │             │   │                 │                 │        ▼        │              │
│  │             │   │                 │                 │      [END]      │              │
│  │             │   │        ●        │                 │                 │              │
│  │             │   │      (END)      │                 │                 │              │
│  │             │   │                 │                 │                 │              │
│  └─────────────┴─────────────────────┴─────────────────┴─────────────────┘              │
│                                                                                          │
│  Process Details:                                                                        │
│  • Trigger: New USP project approval                                                     │
│  • Duration: 2-3 business days (including approval)                                     │
│  • Output: Unique Project ID (Format: USP-YYYY-NNN)                                     │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 NOA Recording and Contract Linkage Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    NOA/CONTRACT MANAGEMENT PROCESS                                       │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  START ──► [Receive NOA from DUSP] ──► {Validate NOA} ──► {Complete?}           │   │
│  │                                              ◇               ◇                  │   │
│  │                                              │               │                  │   │
│  │                                           No │            No │                  │   │
│  │                                              ▼               ▼                  │   │
│  │                                         [Request           [Request            │   │
│  │                                          Missing            Clarification]      │   │
│  │                                          Documents]              │              │   │
│  │                                              │                   │              │   │
│  │                                              └────────┬──────────┘              │   │
│  │                                                       │                         │   │
│  │                                                    Yes │                         │   │
│  │                                                       ▼                         │   │
│  │                                              [Create NOA                        │   │
│  │                                               Record]                           │   │
│  │                                                       │                         │   │
│  │                                                       ▼                         │   │
│  │                                              {Contract                         │   │
│  │                                               Available?}                       │   │
│  │                                                       ◇                         │   │
│  │                                                  Yes  │  No                     │   │
│  │                                                       ▼                         │   │
│  │                                              [Link to      [Await Contract     │   │
│  │                                               Contract      Signing]            │   │
│  │                                               Record]            │              │   │
│  │                                                       │        │                │   │
│  │                                                       ▼        ▼                │   │
│  │                                              [Generate Sub-Project IDs]         │   │
│  │                                                       │                         │   │
│  │                                                       ▼                         │   │
│  │                                              [Update USPFS]                     │   │
│  │                                                       │                         │   │
│  │                                                       ▼                         │   │
│  │                                              [Notify Stakeholders]              │   │
│  │                                                       │                         │   │
│  │                                                       ▼                         │   │
│  │                                                     (END)                       │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  Key Activities:                                                                         │
│  1. NOA validation against USPFS records                                                │
│  2. Contract terms extraction and storage                                               │
│  3. Performance bond recording                                                          │
│  4. Sub-Project ID auto-generation                                                      │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. CLAIMS PROCESSING FLOWS

### 3.1 Quarterly Claim Submission Flow (Swimlane)

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    QUARTERLY CLAIM SUBMISSION PROCESS                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐                     │
│  │  DUSP    │   UCMS   │  BUDGET  │  OCR/AI  │  WORKFLOW│ APPROVER │                     │
│  │  USER    │  PORTAL  │  CHECK   │  ENGINE  │  ENGINE  │  LEVEL 1 │                     │
│  ├──────────┼──────────┼──────────┼──────────┼──────────┼──────────┤                     │
│  │    ●     │          │          │          │          │          │                     │
│  │  START   │          │          │          │          │          │                     │
│  │    │     │          │          │          │          │          │                     │
│  │    ▼     │          │          │          │          │          │                     │
│  │ [Login   │          │          │          │          │          │                     │
│  │  to UCMS]│          │          │          │          │          │                     │
│  │    │     │          │          │          │          │          │                     │
│  │    ▼     │          │          │          │          │          │                     │
│  │ [Select  │          │          │          │          │          │                     │
│  │  "New    │          │          │          │          │          │                     │
│  │  Claim"] │          │          │          │          │          │                     │
│  │    │     │          │          │          │          │          │                     │
│  │    ▼     │          │          │          │          │          │                     │
│  │ [Enter   │          │          │          │          │          │                     │
│  │  Claim   │          │          │          │          │          │                     │
│  │  Details]│          │          │          │          │          │                     │
│  │    │────►│          │          │          │          │          │                     │
│  │         ││[Validate]│          │          │          │          │                     │
│  │         ││    │     │          │          │          │          │                     │
│  │         ││    ▼     │          │          │          │          │                     │
│  │         ││{Valid?}  │          │          │          │          │                     │
│  │◄────────┼┼──No      │          │          │          │          │                     │
│  │[Show     │          │          │          │          │          │                     │
│  │ Errors]  │          │          │          │          │          │                     │
│  │    │     │          │          │          │          │          │                     │
│  │    └────►│          │          │          │          │          │                     │
│  │         ││   Yes    │          │          │          │          │                     │
│  │         ││    │     │          │          │          │          │                     │
│  │         ││    └────►│[Check    │          │          │          │                     │
│  │         ││          │ Budget   │          │          │          │                     │
│  │         ││          │ Balance] │          │          │          │                     │
│  │         ││          │    │     │          │          │          │                     │
│  │         ││          │    ▼     │          │          │          │                     │
│  │         ││          │{Sufficient│         │          │          │                     │
│  │◄────────┼┼◄─────────┼──No      │          │          │          │                     │
│  │[Show     │          │          │          │          │          │                     │
│  │ Budget   │          │          │          │          │          │                     │
│  │ Error]   │          │          │          │          │          │                     │
│  │    │     │          │          │          │          │          │                     │
│  │    └────►│          │          │          │          │          │                     │
│  │         ││          │   Yes    │          │          │          │                     │
│  │         ││◄─────────┼──────────┘          │          │          │                     │
│  │         ││[Proceed  │                     │          │          │                     │
│  │         ││ to Upload│                     │          │          │                     │
│  │         ││ Documents│                     │          │          │                     │
│  │    ◄────┼┼──────────┘                     │          │          │                    │
│  │ [Upload  │                                │          │          │                    │
│  │  Required│                                │          │          │                    │
│  │  Docs]   │                                │          │          │                    │
│  │    │────►│                                │          │          │                    │
│  │         ││[Store &    ───────────────────►│[OCR/     │          │                    │
│  │         ││ Process   │                     │ AI       │          │                    │
│  │         ││ Documents]│                     │ Analysis]│          │                    │
│  │         ││          │◄────────────────────│          │          │                    │
│  │         ││[Validate  │                     │          │          │                    │
│  │         ││ Results]  │                     │          │          │                    │
│  │         ││    │     │                     │          │          │                    │
│  │         ││    ▼     │                     │          │          │                    │
│  │         ││{Valid?}  │                     │          │          │                    │
│  │◄────────┼┼──No      │                     │          │          │                    │
│  │[Request  │          │                     │          │          │                    │
│  │ Resubmit]│          │                     │          │          │                    │
│  │    │     │          │                     │          │          │                    │
│  │    └────►│          │                     │          │          │                    │
│  │         ││   Yes    │                     │          │          │                    │
│  │         ││    │     │                     │          │          │                    │
│  │         ││    └────►│                     │─────────►│[Create   │                    │
│  │         ││          │                     │          │ Workflow │                    │
│  │         ││          │                     │          │ Tasks]   │                    │
│  │         ││          │                     │          │    │     │                    │
│  │         ││          │                     │          │    └────►│[Receive            │
│  │         ││          │                     │          │          │ Notification]      │
│  │         ││◄────────────────────────────────────────◄┼◄─────────┼────────┐           │
│  │    ◄────┼┼──────────┘                     │          │          │        │           │
│  │ [Confirm │                                │          │          │        ▼           │
│  │  Submit] │                                │          │          │    [Review &      │
│  │    │     │                                │          │          │     Approve]       │
│  │    └────►│                                │          │          │        │           │
│  │         ││                                │          │          │        ▼           │
│  │         ││                                │          │          │    {Decision}      │
│  │         ││                                │          │          │       ◇            │
│  │◄────────┼┼◄───────────────────────────────┼◄─────────┼◄─────────┼────Reject          │
│  │[Notify   │                                │          │          │                    │
│  │  Return] │                                │          │          │        │           │
│  │         ││                                │          │          │     Approve        │
│  │         ││                                │          │          │        │           │
│  │         ││◄───────────────────────────────┼◄─────────┼◄─────────┼────────┘           │
│  │         ││[Forward to Level 2]           │          │          │                    │
│  │         ││    │                           │          │          │                    │
│  │         ││    ▼                           │          │          │                    │
│  │         ││ (Continue to Multi-Level       │          │          │                    │
│  │         ││  Approval Process...)          │          │          │                    │
│  └──────────┴──────────┴──────────┴──────────┴──────────┴──────────┘                     │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Advance Claim Processing Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    ADVANCE CLAIM PROCESSING FLOW                                         │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  START (Advance Claim Request)                                                   │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  [DUSP Submits Advance Claim Application]                                        │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  {System Checks:}                                                                │   │
│  │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│  │  │ 1. Valid Performance Bond?                                              │   │   │
│  │  │ 2. Project Active Status?                                               │   │   │
│  │  │ 3. No Outstanding Claims Issues?                                        │   │   │
│  │  │ 4. Advance Amount ≤ % of Capped Cost?                                   │   │   │
│  │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│  │        │                                                                         │   │
│  │    No ─┼─► [Reject with Reason] ──► [Notify DUSP] ──► (END - Rejected)          │   │
│  │        │                                                                         │   │
│  │       Yes                                                                        │   │
│  │        ▼                                                                         │   │
│  │  [Calculate Recovery Schedule]                                                   │   │
│  │  • Quarterly recovery amount                                                     │   │
│  │  • Recovery start date                                                           │   │
│  │  • Full recovery timeline                                                        │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  [Create Advance Claim Record]                                                   │   │
│  │  Status: PENDING APPROVAL                                                        │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  [Submit to 3-Level Approval Workflow]                                           │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  {All 3 Levels Approved?}                                                        │   │
│  │        │                                                                         │   │
│  │    No ─┼─► [Return to DUSP] ──► (END - Returned)                                 │   │
│  │        │                                                                         │   │
│  │       Yes                                                                        │   │
│  │        ▼                                                                         │   │
│  │  [Generate Payment Voucher in USPFS]                                             │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  [Record Advance in UCMS]                                                        │   │
│  │  Status: DISBURSED                                                               │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  [Activate Recovery Tracking]                                                    │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  [Send Disbursement Notification]                                                │   │
│  │        │                                                                         │   │
│  │        ▼                                                                         │   │
│  │  (END - Completed)                                                               │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  Note: Advance recovery is automatic - deducted from subsequent quarterly claims        │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. PAYMENT PROCESSING FLOWS

### 4.1 Payment Voucher Generation Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    PAYMENT VOUCHER GENERATION FLOW                                       │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌──────────────┬──────────────┬──────────────┬──────────────┬──────────────┐            │
│  │    UCMS      │    DIGITAL   │   APPROVER   │    USPFS     │     BANK     │            │
│  │   SYSTEM     │   SIGNATURE  │   (Level 3)  │  (Oracle)    │   GATEWAY    │            │
│  ├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤            │
│  │              │              │              │              │              │            │
│  │    ●         │              │              │              │              │            │
│  │  START       │              │              │              │              │            │
│  │  (Claim      │              │              │              │              │            │
│  │  Approved)   │              │              │              │              │            │
│  │    │         │              │              │              │              │            │
│  │    ▼         │              │              │              │              │            │
│  │ [Generate    │              │              │              │              │            │
│  │  Memo PDF]   │              │              │              │              │            │
│  │    │         │              │              │              │              │            │
│  │    └────►    │              │              │              │              │            │
│  │              │              │              │              │              │            │
│  │              │ [Prepare for │              │              │              │            │
│  │              │  Digital Sig]│              │              │              │            │
│  │              │    │         │              │              │              │            │
│  │              │    ▼         │              │              │              │            │
│  │              │ [Send to     │              │              │              │            │
│  │              │  Level 1     │              │              │              │            │
│  │              │  Approver]   │              │              │              │            │
│  │              │              │    ●         │              │              │            │
│  │              │              │ [Review &    │              │              │            │
│  │              │              │  Sign]       │              │              │            │
│  │              │              │    │         │              │              │            │
│  │              │◄─────────────┘    │         │              │              │            │
│  │              │ [Level 1 Sig      │          │              │              │            │
│  │              │  Complete]        │          │              │              │            │
│  │              │    │              │          │              │              │            │
│  │              │    ▼              │          │              │              │            │
│  │              │ [Send to Level 2] │          │              │              │            │
│  │              │    ... (Repeat    │          │              │              │            │
│  │              │    for Level 2)   │          │              │              │            │
│  │              │                   │          │              │              │            │
│  │              │ [Send to Level 3] │          │              │              │            │
│  │              │         │         │          │              │              │            │
│  │              │         │    ●    │          │              │              │            │
│  │              │         └────►[Final Review │              │              │            │
│  │              │              & Sign]         │              │              │            │
│  │              │                   │         │              │              │            │
│  │              │◄──────────────────┘         │              │              │            │
│  │              │ [All Signatures             │              │              │            │
│  │              │  Complete]                  │              │              │            │
│  │    ◄─────────┼─────────────────────────────┘              │              │            │
│  │ [Verify      │                                            │              │            │
│  │  Signatures] │                                            │              │            │
│  │    │         │                                            │              │            │
│  │    ▼         │                                            │              │            │
│  │ {Valid?}     │                                            │              │            │
│  │    ◇         │                                            │              │            │
│  │ No │         │                                            │              │            │
│  │    ▼         │                                            │              │            │
│  │ [Escalate    │                                            │              │            │
│  │  to Admin]   │                                            │              │            │
│  │    │         │                                            │              │            │
│  │   Yes        │                                            │              │            │
│  │    │         │                                            │              │            │
│  │    └────►    │                                            │              │            │
│  │ [Prepare     │                                            │              │            │
│  │  Voucher     │                                            │              │            │
│  │  Data]       │                                            │              │            │
│  │    │         │                                            │              │            │
│  │    └─────────┼────────────►                               │              │            │
│  │              │              [Create Voucher in USPFS]      │              │            │
│  │              │                   │                        │              │            │
│  │              │                   ▼                        │              │            │
│  │              │              {Success?}                    │              │            │
│  │              │                   ◇                        │              │            │
│  │              │              No  │  Yes                    │              │            │
│  │              │                  ▼                        │              │            │
│  │              │             [Retry/                       │              │            │
│  │              │              Alert]                       │              │            │
│  │              │                  │                        │              │            │
│  │              │                  └────►[Post to GL]       │              │            │
│  │              │                       │                   │              │              │
│  │              │                       ▼                   │              │              │
│  │              │                  [Generate               │              │              │
│  │              │                   Voucher No]            │              │              │
│  │              │                       │                   │              │              │
│  │    ◄─────────┼───────────────────────┘                   │              │              │
│  │ [Record      │                                           │              │              │
│  │  Voucher Ref]│                                           │              │              │
│  │    │         │                                           │              │              │
│  │    ▼         │                                           │              │              │
│  │ [Update      │                                           │              │              │
│  │  Claim Status│                                           │              │              │
│  │  to PAID]    │                                           │              │              │
│  │    │         │                                           │              │              │
│  │    └─────────┼──────────────────────────────────────────►│[Process      │              │
│  │              │                                           │ Payment]     │              │
│  │              │                                           │    │         │              │
│  │              │                                           │    └───────► │[Execute      │
│  │              │                                           │              │ Transfer]    │
│  │              │                                           │              │    │         │
│  │              │                                           │    ◄─────────┼────┘         │
│  │              │                                           │ [Confirm     │              │
│  │              │                                           │  Payment]    │              │
│  │              │                                           │    │         │              │
│  │    ◄─────────┼───────────────────────────────────────────┼────┘         │              │
│  │ [Generate    │                                           │              │              │
│  │  Letter to   │                                           │              │              │
│  │  DUSP]       │                                           │              │              │
│  │    │         │                                           │              │              │
│  │    ▼         │                                           │              │              │
│  │  (END)       │                                           │              │              │
│  └──────────────┴──────────────┴──────────────┴──────────────┴──────────────┘            │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. APPROVAL WORKFLOW FLOWS

### 5.1 Three-Level Approval Workflow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    THREE-LEVEL APPROVAL WORKFLOW                                         │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │                          APPROVAL WORKFLOW ENGINE                                │   │
│  │                                                                                  │   │
│  │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│  │  │ CLAIM SUBMITTED                                                          │   │   │
│  │  │ (Status: PENDING LEVEL 1)                                               │   │   │
│  │  └──────────────────────────┬──────────────────────────────────────────────┘   │   │
│  │                             │                                                    │   │
│  │                             ▼                                                    │   │
│  │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│  │  │ LEVEL 1 APPROVAL                                                         │   │   │
│  │  │ ┌─────────────────────────────────────────────────────────────────────┐ │   │   │
│  │  │ │ Role: Senior Executive / Ketua Penolong Pengarah                   │ │   │   │
│  │  │ │ Scope: Initial review, completeness check                           │ │   │   │
│  │  │ │ SLA: 2 working days                                                  │ │   │   │
│  │  │ └─────────────────────────────────────────────────────────────────────┘ │   │   │
│  │  │        │                                                                      │   │
│  │  │   ┌────┴────┬───────────┐                                                    │   │
│  │  │   ▼         ▼           ▼                                                    │   │
│  │  │ [Approve] [Return]    [Reject]                                               │   │
│  │  │    │         │           │                                                    │   │
│  │  │    │    ┌────┘           │                                                    │   │
│  │  │    │    │                └─────────────────────────────┐                     │   │
│  │  │    │    ▼                                              │                     │   │
│  │  │    │ [Notify DUSP]                               [Notify DUSP]                │   │
│  │  │    │    │                                              │                     │   │
│  │  │    │    ▼                                              ▼                     │   │
│  │  │    │ [Status: RETURNED]                          [Status: REJECTED]          │   │
│  │  │    │                                                         │               │   │
│  │  │    │    ┌────────────────────────────────────────────────────┘               │   │
│  │  │    │    │                                                                     │   │
│  │  │    ▼    ▼                                                                     │   │
│  │  │ [Status: PENDING LEVEL 2]                                                     │   │
│  │  │        │                                                                      │   │
│  │  │        ▼                                                                      │   │
│  │  │ ┌─────────────────────────────────────────────────────────────────────────┐ │   │
│  │  │ │ LEVEL 2 APPROVAL                                                         │ │   │
│  │  │ │ Role: Assistant Director / Penolong Pengarah                           │ │   │
│  │  │ │ Scope: Technical review, budget verification                           │ │   │
│  │  │ │ SLA: 2 working days                                                      │ │   │
│  │  │ └─────────────────────────────────────────────────────────────────────────┘ │   │
│  │  │        │                                                                      │   │
│  │  │   ┌────┴────┬───────────┐                                                    │   │
│  │  │   ▼         ▼           ▼                                                    │   │
│  │  │ [Approve] [Return]    [Reject]                                               │   │
│  │  │    │         │           │                                                    │   │
│  │  │    │    ┌────┘           │                                                    │   │
│  │  │    │    │                └─────────────────────────────────────┐             │   │
│  │  │    │    ▼                                                    │             │   │
│  │  │    │ [Notify DUSP & Level 1]                             [Notify All]       │   │
│  │  │    │    │                                                    │             │   │
│  │  │    │    ▼                                                    ▼             │   │
│  │  │    │ [Status: RETURNED]                              [Status: REJECTED]     │   │
│  │  │    │                                                         │             │   │
│  │  │    │    ┌────────────────────────────────────────────────────┘             │   │
│  │  │    │    │                                                                   │   │
│  │  │    ▼    ▼                                                                   │   │
│  │  │ [Status: PENDING LEVEL 3]                                                   │   │
│  │  │        │                                                                    │   │
│  │  │        ▼                                                                    │   │
│  │  │ ┌─────────────────────────────────────────────────────────────────────────┐ │   │
│  │  │ │ LEVEL 3 APPROVAL (FINAL)                                                 │ │   │
│  │  │ │ Role: Director / Pengarah                                              │ │   │
│  │  │ │ Scope: Final authorization, financial approval                         │ │   │
│  │  │ │ SLA: 1 working day                                                       │ │   │
│  │  │ │ Special: Digital Signature Required                                    │ │   │
│  │  │ └─────────────────────────────────────────────────────────────────────────┘ │   │
│  │  │        │                                                                      │   │
│  │  │   ┌────┴────┬───────────┐                                                    │   │
│  │  │   ▼         ▼           ▼                                                    │   │
│  │  │ [Approve] [Return]    [Reject]                                               │   │
│  │  │    │         │           │                                                    │   │
│  │  │    │    ┌────┘           │                                                    │   │
│  │  │    │    │                └─────────────────────────────────────┐             │   │
│  │  │    │    ▼                                                    │             │   │
│  │  │    │ [Notify All Levels]                                 [Notify All]       │   │
│  │  │    │    │                                                    │             │   │
│  │  │    │    ▼                                                    ▼             │   │
│  │  │    │ [Status: RETURNED]                              [Status: REJECTED]     │   │
│  │  │    │                                                         │             │   │
│  │  │    │    ┌────────────────────────────────────────────────────┘             │   │
│  │  │    │    │                                                                   │   │
│  │  │    ▼    ▼                                                                   │   │
│  │  │ [Status: APPROVED]                                                          │   │
│  │  │        │                                                                    │   │
│  │  │        ▼                                                                    │   │
│  │  │ [Trigger Payment Workflow]                                                  │   │
│  │  │        │                                                                    │   │
│  │  │        ▼                                                                    │   │
│  │  │      (END)                                                                  │   │
│  │  │                                                                             │   │
│  │  └─────────────────────────────────────────────────────────────────────────────┘   │
│  │                                                                                      │   │
│  │  ESCALATION RULES:                                                                 │   │
│  │  • Auto-escalate if SLA exceeded                                                   │   │
│  │  • Notify supervisor if approver unavailable                                       │   │
│  │  • Emergency approval path for urgent claims                                       │   │
│  │                                                                                      │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 6. INTEGRATION FLOWS

### 6.1 USPFS Real-Time Integration Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    USPFS REAL-TIME INTEGRATION FLOW                                      │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌──────────────┬──────────────┬──────────────┬──────────────┬──────────────┐            │
│  │     UCMS     │  API GATEWAY │  OIC/Orche-  │    USPFS     │   RESPONSE   │            │
│  │   SERVICE    │              │  stration    │  (Oracle)    │   HANDLING   │            │
│  ├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤            │
│  │              │              │              │              │              │            │
│  │    ●         │              │              │              │              │            │
│  │  (Trigger)   │              │              │              │              │            │
│  │    │         │              │              │              │              │            │
│  │    ▼         │              │              │              │              │            │
│  │ [Prepare     │              │              │              │              │            │
│  │  API Request]│              │              │              │              │            │
│  │    │         │              │              │              │              │            │
│  │    └────►    │              │              │              │              │            │
│  │              │ [Validate    │              │              │              │            │
│  │              │  Auth Token] │              │              │              │            │
│  │              │    │         │              │              │              │            │
│  │              │    ▼         │              │              │              │            │
│  │              │ {Valid?}     │              │              │              │            │
│  │              │    ◇         │              │              │              │            │
│  │◄─────────────┼──No          │              │              │              │            │
│  │ [Auth Error] │              │              │              │              │            │
│  │              │   Yes        │              │              │              │            │
│  │              │    │         │              │              │              │            │
│  │              │    └────►    │              │              │              │            │
│  │              │              │ [Transform   │              │              │            │
│  │              │              │  & Route]    │              │              │            │
│  │              │              │    │         │              │              │            │
│  │              │              │    ▼         │              │              │            │
│  │              │              │ [Apply       │              │              │            │
│  │              │              │  Protocol    │              │              │            │
│  │              │              │  Conversion] │              │              │            │
│  │              │              │    │         │              │              │            │
│  │              │              │    └────►    │              │              │            │
│  │              │              │              │ [Receive     │              │            │
│  │              │              │              │  Request]    │              │            │
│  │              │              │              │    │         │              │            │
│  │              │              │              │    ▼         │              │            │
│  │              │              │              │ [Execute     │              │            │
│  │              │              │              │  Business    │              │            │
│  │              │              │              │  Logic]      │              │            │
│  │              │              │              │    │         │              │            │
│  │              │              │              │    ▼         │              │            │
│  │              │              │              │ {Success?}   │              │            │
│  │              │              │              │    ◇         │              │            │
│  │              │              │◄─────────────┼──Error       │              │            │
│  │              │              │              │              │              │            │
│  │              │              │              │   Success    │              │            │
│  │              │              │              │    │         │              │            │
│  │              │              │◄─────────────┘    │         │              │            │
│  │              │              │ [Transform        │         │              │            │
│  │              │              │  Response]        │         │              │            │
│  │              │              │    │              │         │              │            │
│  │              │◄─────────────┼───────────────────┘         │              │            │
│  │              │ [Return      │                             │              │            │
│  │              │  Response]   │                             │              │            │
│  │    ◄─────────┼──────────────┘                             │              │            │
│  │ [Process     │                                            │              │            │
│  │  Response]   │                                            │              │            │
│  │    │         │                                            │              │            │
│  │    ▼         │                                            │              │            │
│  │ {Success?}   │                                            │              │            │
│  │    ◇         │                                            │              │            │
│  │ Yes│    No   │                                            │              │            │
│  │    │    │    │                                            │              │            │
│  │    ▼    ▼    │                                            │              │            │
│  │ [Continue]   │                                            │              │            │
│  │ [Process]    │                                            │              │            │
│  │    │         │                                            │              │            │
│  │    ▼         │                                            │              │            │
│  │ [Retry/      │                                            │              │            │
│  │  Alert]      │                                            │              │            │
│  │    │         │                                            │              │            │
│  │    ▼         │                                            │              │            │
│  │  (END)       │                                            │              │            │
│  └──────────────┴──────────────┴──────────────┴──────────────┴──────────────┘            │
│                                                                                          │
│  Error Handling:                                                                         │
│  • Retry 3 times with exponential backoff                                               │
│  • Circuit breaker for repeated failures                                                │
│  • Fallback to offline queue if USPFS unavailable                                       │
│  • Alert operations team after all retries exhausted                                    │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 2026 | Business Analysis Team | Initial flowcharts |

---

**END OF ANNEX T5**
