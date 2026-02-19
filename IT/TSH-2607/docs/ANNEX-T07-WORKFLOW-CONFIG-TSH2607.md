# ANNEX-T07-WORKFLOW-CONFIG-TSH2607.md

# ANNEX T7: WORKFLOW CONFIGURATIONS
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T7  
**Version:** 1.0  
**Date:** February 2026  

---

## TABLE OF CONTENTS

1. [Workflow Engine Overview](#1-workflow-engine-overview)
2. [Claims Approval Workflow](#2-claims-approval-workflow)
3. [Payment Approval Workflow](#3-payment-approval-workflow)
4. [Document Approval Workflow](#4-document-approval-workflow)
5. [Exception Handling Workflows](#5-exception-handling-workflows)
6. [Workflow Configuration Parameters](#6-workflow-configuration-parameters)

---

## 1. WORKFLOW ENGINE OVERVIEW

### 1.1 Workflow Engine Architecture

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         WORKFLOW ENGINE ARCHITECTURE                                     │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                         WORKFLOW DEFINITION LAYER                                │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐        │   │
│  │  │  Process     │  │  Task        │  │  Transition  │  │  Gateway     │        │   │
│  │  │  Definition  │  │  Definition  │  │  Definition  │  │  Definition  │        │   │
│  │  │  (BPMN 2.0)  │  │  (User/Svc)  │  │  (Flow)      │  │  (Decision)  │        │   │
│  │  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘        │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                          │                                               │
│                                          ▼                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                         WORKFLOW RUNTIME LAYER                                   │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐        │   │
│  │  │  Process     │  │  Task        │  │  Event       │  │  Timer       │        │   │
│  │  │  Engine      │  │  Manager     │  │  Handler     │  │  Scheduler   │        │   │
│  │  │  (Camunda/   │  │  (Assign/    │  │  (Start/End/ │  │  (SLA/       │        │   │
│  │  │   Oracle)    │  │  Complete)   │  │  Intermediate)│  │  Escalation) │        │   │
│  │  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘        │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                          │                                               │
│                                          ▼                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                         WORKFLOW EXECUTION LAYER                                 │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐        │   │
│  │  │  User Task   │  │  Service     │  │  Script      │  │  Business    │        │   │
│  │  │  (Approval)  │  │  Task        │  │  Task        │  │  Rule Task   │        │   │
│  │  │              │  │  (System)    │  │  (Validation)│  │  (DMN)       │        │   │
│  │  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘        │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Workflow Types

| Workflow ID | Workflow Name | Purpose | Trigger |
|-------------|---------------|---------|---------|
| WF-CLM-001 | Quarterly Claim Approval | Process quarterly claims | Claim submission |
| WF-CLM-002 | Advance Claim Approval | Process advance claims | Claim submission |
| WF-CLM-003 | Yearly Claim Approval | Process yearly claims | Claim submission |
| WF-PAY-001 | Payment Authorization | Authorize payments | Claim approval |
| WF-DOC-001 | Document Verification | Verify submitted docs | Document upload |
| WF-MD-001 | Master Data Change | Approve master data changes | Data change request |
| WF-V0-001 | Variation Order Approval | Process VO requests | VO submission |
| WF-EOT-001 | Extension of Time Approval | Process EOT requests | EOT submission |

---

## 2. CLAIMS APPROVAL WORKFLOW

### 2.1 Three-Level Approval Workflow Configuration

```yaml
workflow:
  id: WF-CLM-001
  name: Quarterly Claim Approval
  version: 1.0
  
  # Process Definition
  process:
    startEvent: ClaimSubmitted
    
    # User Tasks
    userTasks:
      - id: Level1Review
        name: Level 1 Review
        assigneeRole: ROLE_L1_APPROVER
        candidateGroups: 
          - GRP_FINANCE_EXECUTIVE
        sla: 2d
        escalation:
          after: 2d
          action: NOTIFY_SUPERVISOR
          
      - id: Level2Review
        name: Level 2 Review
        assigneeRole: ROLE_L2_APPROVER
        candidateGroups:
          - GRP_FINANCE_MANAGER
        sla: 2d
        escalation:
          after: 2d
          action: NOTIFY_DIRECTOR
          
      - id: Level3Review
        name: Level 3 Review
        assigneeRole: ROLE_L3_APPROVER
        candidateGroups:
          - GRP_FINANCE_DIRECTOR
        sla: 1d
        escalation:
          after: 1d
          action: NOTIFY_CFO
    
    # Service Tasks
    serviceTasks:
      - id: ValidateClaim
        name: Validate Claim Data
        delegate: ${claimValidationService.validate(execution)}
        
      - id: CheckBudget
        name: Check Budget Balance
        delegate: ${budgetService.checkBalance(execution)}
        
      - id: SendNotification
        name: Send Notification
        delegate: ${notificationService.send(execution)}
        
      - id: CreateVoucher
        name: Create Payment Voucher
        delegate: ${uspfsIntegrationService.createVoucher(execution)}
    
    # Gateways
    gateways:
      - id: L1Decision
        type: exclusive
        conditions:
          - id: L1Approved
            expression: ${approved == true && level1Decision == 'APPROVE'}
            target: Level2Review
          - id: L1Returned
            expression: ${level1Decision == 'RETURN'}
            target: NotifyReturn
          - id: L1Rejected
            expression: ${level1Decision == 'REJECT'}
            target: NotifyRejection
            
      - id: L2Decision
        type: exclusive
        conditions:
          - id: L2Approved
            expression: ${level2Decision == 'APPROVE'}
            target: Level3Review
          - id: L2Returned
            expression: ${level2Decision == 'RETURN'}
            target: NotifyReturn
          - id: L2Rejected
            expression: ${level2Decision == 'REJECT'}
            target: NotifyRejection
            
      - id: L3Decision
        type: exclusive
        conditions:
          - id: L3Approved
            expression: ${level3Decision == 'APPROVE'}
            target: CreateVoucher
          - id: L3Returned
            expression: ${level3Decision == 'RETURN'}
            target: NotifyReturn
          - id: L3Rejected
            expression: ${level3Decision == 'REJECT'}
            target: NotifyRejection
    
    # End Events
    endEvents:
      - id: ClaimApproved
        name: Claim Approved
        
      - id: ClaimRejected
        name: Claim Rejected
        
      - id: ClaimReturned
        name: Claim Returned
```

### 2.2 Workflow Process Flow (BPMN)

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    CLAIMS APPROVAL WORKFLOW BPMN                                         │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  [Start] ──► [Validate Claim] ──► [Check Budget] ──► {Valid?}                           │
│                                                       ◇                                  │
│                                                    No │                                  │
│                                                       ▼                                  │
│                                                 [Reject]                                 │
│                                                       │                                  │
│                                                   Yes │                                  │
│                                                       ▼                                  │
│                                               [Level 1 Review] ──► {Decision}           │
│                                              (2 days SLA)         ◇                      │
│                                                         ┌────┬───────────┐               │
│                                                         ▼    ▼           ▼               │
│                                                      [App] [Ret]      [Rej]              │
│                                                         │    │           │               │
│                                                         │    └────┬──────┘               │
│                                                         │         │                      │
│                                                         ▼         ▼                      │
│                                               [Level 2 Review]  [Notify]                 │
│                                              (2 days SLA)         │                      │
│                                                         │         ▼                      │
│                                                         │      [End]                     │
│                                                    {Decision}                            │
│                                                         ◇                                │
│                                                         │                                │
│                                            ┌────────────┼────────────┐                   │
│                                            ▼            ▼            ▼                   │
│                                         [App]         [Ret]       [Rej]                  │
│                                            │            │            │                   │
│                                            │            └────┬───────┘                   │
│                                            │                 │                          │
│                                            ▼                 ▼                          │
│                                 [Level 3 Review]           [Notify]                      │
│                                (1 day SLA)                   │                          │
│                                    │  (Digital Sig)          ▼                          │
│                                    │                       [End]                        │
│                               {Decision}                                                 │
│                                    ◇                                                     │
│                         ┌──────────┼──────────┐                                          │
│                         ▼          ▼          ▼                                          │
│                      [App]       [Ret]      [Rej]                                        │
│                         │          │          │                                          │
│                         │          └────┬─────┘                                          │
│                         │               │                                                │
│                         ▼               ▼                                                │
│               [Create Voucher]      [Notify]                                             │
│                         │             │                                                  │
│                         ▼             ▼                                                  │
│                      [End]         [End]                                                 │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 2.3 Approval Rules Configuration

```javascript
// approvalRules.js
const approvalRules = {
  // Level 1 Approval Rules
  level1: {
    roles: ['FINANCE_EXECUTIVE', 'SENIOR_EXECUTIVE'],
    maxClaimAmount: 100000, // RM 100,000
    allowedClaimTypes: ['QUARTERLY', 'ADVANCE', 'YEARLY'],
    checks: [
      'documentCompleteness',
      'basicValidation',
      'budgetAvailability'
    ],
    sla: {
      duration: 2,
      unit: 'businessDays'
    },
    escalation: {
      afterSla: true,
      notify: 'SUPERVISOR',
      autoReassign: false
    }
  },
  
  // Level 2 Approval Rules
  level2: {
    roles: ['FINANCE_MANAGER', 'ASSISTANT_DIRECTOR'],
    maxClaimAmount: 500000, // RM 500,000
    allowedClaimTypes: ['QUARTERLY', 'ADVANCE', 'YEARLY'],
    checks: [
      'technicalReview',
      'progressVerification',
      'milestoneCheck'
    ],
    sla: {
      duration: 2,
      unit: 'businessDays'
    },
    escalation: {
      afterSla: true,
      notify: 'DIRECTOR',
      autoReassign: false
    }
  },
  
  // Level 3 Approval Rules
  level3: {
    roles: ['FINANCE_DIRECTOR', 'DIRECTOR'],
    maxClaimAmount: null, // No limit
    allowedClaimTypes: ['QUARTERLY', 'ADVANCE', 'YEARLY'],
    checks: [
      'financialReview',
      'complianceCheck',
      'finalAuthorization'
    ],
    requiresDigitalSignature: true,
    sla: {
      duration: 1,
      unit: 'businessDays'
    },
    escalation: {
      afterSla: true,
      notify: 'CFO',
      autoReassign: true,
      backupApprovers: ['DEPUTY_DIRECTOR', 'CFO']
    }
  },
  
  // Dynamic Routing Rules
  routing: {
    // Auto-approve if amount < threshold
    autoApprove: {
      enabled: false,
      threshold: 0
    },
    
    // Skip levels based on amount
    skipLevel1: {
      condition: 'claimAmount < 50000',
      action: 'routeToLevel2'
    },
    
    // Parallel approval for urgent claims
    parallelApproval: {
      enabled: false,
      condition: 'priority == "URGENT"'
    }
  }
};
```

---

## 3. PAYMENT APPROVAL WORKFLOW

### 3.1 Payment Authorization Workflow

```yaml
workflow:
  id: WF-PAY-001
  name: Payment Authorization
  version: 1.0
  
  process:
    startEvent: ClaimApproved
    
    userTasks:
      - id: PrepareMemo
        name: Prepare Payment Memo
        assigneeRole: ROLE_FINANCE_OFFICER
        form: PaymentMemoForm
        
      - id: L1PaymentReview
        name: Level 1 Payment Review
        assigneeRole: ROLE_PAYMENT_APPROVER_L1
        candidateExpression: ${paymentRoutingService.getL1Approver(execution)}
        sla: 1d
        
      - id: L2PaymentReview
        name: Level 2 Payment Review
        assigneeRole: ROLE_PAYMENT_APPROVER_L2
        candidateExpression: ${paymentRoutingService.getL2Approver(execution)}
        sla: 1d
        
      - id: L3PaymentReview
        name: Level 3 Payment Review
        assigneeRole: ROLE_PAYMENT_APPROVER_L3
        requiresDigitalSignature: true
        signatureProvider: MSC_TRUSTSIGN
        sla: 1d
    
    serviceTasks:
      - id: GenerateMemoPDF
        name: Generate Memo PDF
        delegate: ${documentService.generateMemoPDF(execution)}
        
      - id: RequestDigitalSignature
        name: Request Digital Signature
        delegate: ${digitalSignatureService.requestSignature(execution)}
        
      - id: VerifySignature
        name: Verify Digital Signature
        delegate: ${digitalSignatureService.verifySignature(execution)}
        
      - id: CreateUSPFSVoucher
        name: Create USPFS Voucher
        delegate: ${uspfsService.createVoucher(execution)}
        
      - id: SendPaymentNotification
        name: Send Payment Notification
        delegate: ${notificationService.sendPaymentNotification(execution)}
        
      - id: GenerateDUSPLetter
        name: Generate DUSP Letter
        delegate: ${documentService.generateLetter(execution)}
    
    # Multi-instance for parallel signature collection
    parallelTasks:
      - id: CollectSignatures
        name: Collect All Signatures
        collection: ${approvers}
        elementVariable: approver
        completionCondition: ${allSignaturesCollected == true}
    
    endEvents:
      - id: PaymentAuthorized
        name: Payment Authorized
      
      - id: PaymentRejected
        name: Payment Rejected
```

### 3.2 Digital Signature Integration

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    DIGITAL SIGNATURE WORKFLOW INTEGRATION                                │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌──────────────┬──────────────┬──────────────┬──────────────┬──────────────┐            │
│  │     UCMS     │   WORKFLOW   │   DIGITAL    │     DUSP     │     MCMC     │            │
│  │    SYSTEM    │    ENGINE    │  SIGNATURE   │    USER      │   STAFF      │            │
│  ├──────────────┼──────────────┼──────────────┼──────────────┼──────────────┤            │
│  │              │              │   PROVIDER   │              │              │            │
│  │              │              │              │              │              │            │
│  │              │ [Task: L3    │              │              │              │            │
│  │              │  Approval]   │              │              │              │            │
│  │              │       │      │              │              │              │            │
│  │              │       ▼      │              │              │              │            │
│  │              │ [Generate    │              │              │              │            │
│  │              │  Memo PDF]   │              │              │              │            │
│  │              │       │      │              │              │              │            │
│  │              │       └─────►│[Prepare for  │              │              │            │
│  │              │              │ Signature]   │              │              │            │
│  │              │              │       │      │              │              │            │
│  │              │              │       ▼      │              │              │            │
│  │              │              │ [Send Signing│              │              │            │
│  │              │              │  Request]    │              │              │            │
│  │              │              │       │      │              │              │            │
│  │              │              │       └─────►│ [Receive     │              │            │
│  │              │              │              │  Signing     │              │            │
│  │              │              │              │  Request]    │              │            │
│  │              │              │              │       │      │              │            │
│  │              │              │              │       ▼      │              │            │
│  │              │              │              │ [Authenticate│              │            │
│  │              │              │              │  & Review]   │              │            │
│  │              │              │              │       │      │              │            │
│  │              │              │              │       ▼      │              │            │
│  │              │              │              │ [Apply       │              │            │
│  │              │              │◄─────────────│  Digital Sig]│              │            │
│  │              │              │              │       │      │              │            │
│  │              │              │ [Verify      │◄──────┘      │              │            │
│  │              │              │  Signature]  │              │              │            │
│  │              │              │       │      │              │              │            │
│  │              │              │       ▼      │              │              │            │
│  │              │              │    {Valid?}  │              │              │            │
│  │              │              │       ◇      │              │              │            │
│  │              │◄─────────────┼──No          │              │              │            │
│  │ [Notify      │              │              │              │              │            │
│  │  Signature   │              │              │              │              │            │
│  │  Failure]    │              │   Yes        │              │              │            │
│  │       │      │◄─────────────┘              │              │              │            │
│  │       ▼      │ [Proceed to                 │              │              │            │
│  │     [Retry]  │  Next Step]                 │              │              │            │
│  │              │       │                     │              │              │            │
│  │              │       ▼                     │              │              │            │
│  │              │    (Continue)               │              │              │            │
│  └──────────────┴──────────────┴──────────────┴──────────────┴──────────────┘            │
│                                                                                          │
│  Signature Providers Supported:                                                          │
│  • MSC TrustSign (Primary)                                                               │
│  • Docusign (Alternative)                                                                │
│  • Adobe Sign (Alternative)                                                              │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. DOCUMENT APPROVAL WORKFLOW

### 4.1 Document Verification Workflow

```yaml
workflow:
  id: WF-DOC-001
  name: Document Verification
  version: 1.0
  
  process:
    startEvent: DocumentUploaded
    
    serviceTasks:
      - id: VirusScan
        name: Virus Scan
        delegate: ${securityService.scanVirus(execution)}
        retry: 3
        
      - id: OCRProcessing
        name: OCR Processing
        delegate: ${ocrService.extractText(execution)}
        async: true
        
      - id: DocumentClassification
        name: Document Classification
        delegate: ${aiService.classifyDocument(execution)}
        
      - id: FraudDetection
        name: Fraud Detection Check
        delegate: ${aiService.detectFraud(execution)}
        
      - id: DataExtraction
        name: Extract Data Fields
        delegate: ${aiService.extractFields(execution)}
        
      - id: ValidateExtractedData
        name: Validate Extracted Data
        delegate: ${validationService.validateData(execution)}
    
    userTasks:
      - id: ManualReview
        name: Manual Document Review
        assigneeRole: ROLE_DOCUMENT_VERIFIER
        condition: ${confidenceScore < 0.85 || fraudDetected == true}
        sla: 1d
    
    gateways:
      - id: ValidationResult
        type: exclusive
        conditions:
          - id: Valid
            expression: ${validationPassed == true && fraudDetected == false}
            target: DocumentVerified
          - id: NeedsReview
            expression: ${confidenceScore < 0.85}
            target: ManualReview
          - id: FraudDetected
            expression: ${fraudDetected == true}
            target: FraudInvestigation
          - id: Invalid
            expression: ${validationPassed == false}
            target: RequestResubmission
    
    endEvents:
      - id: DocumentVerified
        name: Document Verified
      
      - id: FraudInvestigation
        name: Fraud Investigation Triggered
      
      - id: RequestResubmission
        name: Request Resubmission
```

---

## 5. EXCEPTION HANDLING WORKFLOWS

### 5.1 SLA Breach Escalation Workflow

```yaml
workflow:
  id: WF-EXC-001
  name: SLA Breach Escalation
  version: 1.0
  
  process:
    startEvent: SlaBreachDetected
    
    # Timer-based escalation
    boundaryEvents:
      - id: SlaTimer
        type: timer
        attachedTo: UserTask
        timerDefinition: ${slaDuration}
        
    serviceTasks:
      - id: NotifyCurrentAssignee
        name: Notify Current Assignee
        delegate: ${notificationService.sendSlaWarning(execution)}
        
      - id: EscalateToSupervisor
        name: Escalate to Supervisor
        delegate: ${escalationService.escalateToSupervisor(execution)}
        
      - id: ReassignTask
        name: Reassign to Backup Approver
        delegate: ${taskService.reassign(execution)}
        condition: ${supervisorUnavailable == true}
        
      - id: NotifyManagement
        name: Notify Management
        delegate: ${notificationService.notifyManagement(execution)}
        
      - id: LogBreach
        name: Log SLA Breach
        delegate: ${auditService.logSlaBreach(execution)}
    
    escalationLevels:
      - level: 1
        trigger: 80% of SLA
        action: sendReminder
        
      - level: 2
        trigger: 100% of SLA
        action: 
          - notifySupervisor
          - markOverdue
          
      - level: 3
        trigger: 150% of SLA
        action:
          - reassignToBackup
          - notifyDirector
          
      - level: 4
        trigger: 200% of SLA
        action:
          - escalateToCFO
          - logIncident
```

### 5.2 Error Recovery Workflow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    ERROR RECOVERY WORKFLOW                                               │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  ERROR DETECTED                                                                  │   │
│  │       │                                                                          │   │
│  │       ▼                                                                          │   │
│  │  [Log Error Details]                                                             │   │
│  │       │                                                                          │   │
│  │       ▼                                                                          │   │
│  │  {Error Classification}                                                          │   │
│  │       ◇                                                                          │   │
│  │    ┌──┼──┬────────┬────────┐                                                     │   │
│  │    ▼  ▼  ▼        ▼        ▼                                                     │   │
│  │  Trans Business  Tech    External                                                │   │
│  │  Error  Error   Error    Error                                                   │   │
│  │    │    │       │        │                                                       │   │
│  │    ▼    ▼       ▼        ▼                                                       │   │
│  │  [Auto  [Notify  [Retry  [Check                                                 │   │
│  │   Retry] User]   3x]     External                                                 │   │
│  │    │    │       │        Sys]                                                    │   │
│  │    │    │       │        │                                                       │   │
│  │    ▼    ▼       ▼        ▼                                                       │   │
│  │  {Success?}   {Success?}  {Up?}                                                  │   │
│  │    │    │       │        │                                                       │   │
│  │   Yes   │      Yes       │                                                       │   │
│  │    │    │       │        │                                                       │   │
│  │    ▼    │       ▼        ▼                                                       │   │
│  │  [Resume│    [Resume  [Resume                                                    │   │
│  │   Flow] │     Flow]    Flow]                                                     │   │
│  │    │    │       │        │                                                       │   │
│  │    └────┼───────┴────────┘                                                       │   │
│  │         │                                                                        │   │
│  │        No                                                                        │   │
│  │         │                                                                        │   │
│  │         ▼                                                                        │   │
│  │  [Alert    ┌─────────┬─────────┐                                                 │   │
│  │   Admin]   ▼         ▼         ▼                                                 │   │
│  │         Manual    Compensating  Abort                                             │   │
│  │         Fix       Transaction   Process                                           │   │
│  │           │          │           │                                               │   │
│  │           ▼          ▼           ▼                                               │   │
│  │        (User      (System     (Log &                                            │   │
│  │         Action)   Recovery)    Notify)                                           │   │
│  │           │          │           │                                               │   │
│  │           └──────────┴───────────┘                                               │   │
│  │                      │                                                           │   │
│  │                      ▼                                                           │   │
│  │                    (End)                                                         │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 6. WORKFLOW CONFIGURATION PARAMETERS

### 6.1 Global Workflow Settings

```yaml
workflow:
  engine:
    type: Camunda / Oracle BPM
    asyncExecutor:
      enabled: true
      corePoolSize: 10
      maxPoolSize: 50
      queueSize: 200
    
  history:
    level: full
    cleanup:
      enabled: true
      batchSize: 500
      olderThan: 90d
  
  notifications:
    channels:
      - email
      - inApp
      - sms
    
  escalation:
    enabled: true
    checkInterval: 5m
    
  deadLetterQueue:
    enabled: true
    maxRetries: 3
    retryDelay: 5m
```

### 6.2 Business Calendar Configuration

```yaml
businessCalendar:
  workingDays:
    - MONDAY
    - TUESDAY
    - WEDNESDAY
    - THURSDAY
    - FRIDAY
  
  workingHours:
    start: "08:30"
    end: "17:30"
    timezone: "Asia/Kuala_Lumpur"
  
  holidays:
    source: "MCMC_HOLIDAY_CALENDAR"
    autoUpdate: true
  
  specialDays:
    - date: "2026-01-01"
      name: "New Year's Day"
      type: public_holiday
    - date: "2026-02-01"
      name: "Federal Territory Day"
      type: public_holiday
    - date: "2026-02-09"
      name: "Chinese New Year"
      type: public_holiday
```

### 6.3 Notification Templates

```yaml
notifications:
  taskAssigned:
    email:
      subject: "UCMS: New Task Assigned - {{taskName}}"
      template: task-assigned-email.html
    inApp:
      title: "New Task Assigned"
      body: "You have been assigned to review {{claimId}}"
    sms:
      enabled: true
      body: "UCMS: Task {{taskName}} assigned. Login to review."
  
  slaWarning:
    email:
      subject: "UCMS: Task Due Soon - {{taskName}}"
      template: sla-warning-email.html
    inApp:
      title: "Task Due Soon"
      body: "Task {{taskName}} is due in {{hoursRemaining}} hours"
  
  taskEscalated:
    email:
      subject: "UCMS: Task Escalated - {{taskName}}"
      template: task-escalated-email.html
    inApp:
      title: "Task Escalated"
      body: "Task {{taskName}} has been escalated to {{escalatedTo}}"
```

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 2026 | Workflow Team | Initial configuration |

---

**END OF ANNEX T7**
