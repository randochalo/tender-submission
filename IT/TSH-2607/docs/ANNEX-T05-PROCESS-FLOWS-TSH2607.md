# ANNEX T5: SAMPLE PROCESS FLOWCHARTS (BPMN)
## TSH-2607: Universal Service Provision (USP) Claims Management System (UCMS)
**Document Reference:** ANNEX-T05-PROCESS-FLOWS-TSH2607.md  
**Version:** 1.0  
**Date:** January 2025  
**Classification:** Technical Annexure

---

## 1. INTRODUCTION

This annexure presents the Business Process Model and Notation (BPMN 2.0) flowcharts for key processes within the USP Claims Management System (UCMS). These diagrams illustrate the end-to-end workflows for claims management, user management, and system administration.

**Cross-References:**
- URS Section 6: Process Requirements
- BRS Section 5: Business Process Specifications
- SRS Section 9: Workflow Specifications
- SDS Section 7: Process Implementation

---

## 2. BPMN NOTATION LEGEND

```mermaid
graph TB
    subgraph "BPMN 2.0 Notation"
        direction TB
        A((Start/End<br/>Event))
        B[Activity/Task]
        C{XOR Gateway<br/>Decision}
        D{{Parallel Gateway<br/>Fork/Join}}
        E[/Data Object/]
        F[(Data Store)]
        G>Gateway]
    end
```

| Symbol | Element | Description |
|--------|---------|-------------|
| Circle | Event | Start, intermediate, or end event |
| Rectangle | Activity | Task or subprocess |
| Diamond | Gateway | Decision or parallel processing |
| Document | Data Object | Information required/produced |
| Cylinder | Data Store | Database or persistent storage |
| Dashed Line | Message Flow | Communication between pools |
| Solid Line | Sequence Flow | Process flow direction |

---

## 3. CORE PROCESS FLOWS

### 3.1 Claim Submission Process (BPMN)

```mermaid
flowchart TB
    Start((Start)) --> Login{User<br/>Logged In?}
    Login -->|No| Authenticate[Authenticate User]
    Login -->|Yes| SelectType[Select Claim Type]
    Authenticate --> SelectType
    
    SelectType --> FillForm[Fill Claim Form]
    FillForm --> Validate{Validation<br/>Passed?}
    
    Validate -->|No| ShowErrors[Display Errors]
    ShowErrors --> FillForm
    
    Validate -->|Yes| UploadDocs[Upload Supporting<br/>Documents]
    UploadDocs --> OCR[OCR Processing]
    OCR --> DocCheck{Documents<br/>Valid?}
    
    DocCheck -->|No| RequestDocs[Request Additional<br/>Documents]
    RequestDocs --> UploadDocs
    
    DocCheck -->|Yes| Review[Review Submission]
    Review --> Confirm{Submit?}
    
    Confirm -->|No| SaveDraft[Save as Draft]
    SaveDraft --> EndDraft((End - Draft Saved))
    
    Confirm -->|Yes| Submit[Submit Claim]
    Submit --> GenerateID[Generate Claim ID]
    GenerateID --> Notify[Notify Claimant &<br/>MCMC Officers]
    Notify --> Log[(Log in Audit<br/>Trail)]
    Log --> EndSubmit((End - Submitted))
```

**Process Details:**

| Step | Actor | System Activity | Output |
|------|-------|-----------------|--------|
| 1 | Claimant | Access portal | Login screen |
| 2 | UCMS | Authenticate user | Session token |
| 3 | Claimant | Select claim category | Form loaded |
| 4 | UCMS | Validate form inputs | Validation results |
| 5 | Claimant | Upload documents | Document metadata |
| 6 | UCMS | OCR processing | Extracted text |
| 7 | UCMS | Validate documents | Validation report |
| 8 | Claimant | Confirm submission | Claim ID generated |
| 9 | UCMS | Send notifications | Email/SMS sent |

---

### 3.2 Claim Assessment & Approval Process

```mermaid
flowchart TB
    Start((New Claim<br/>Submitted)) --> Assign[Auto-Assign to<br/>Claims Officer]
    Assign --> Screen[Screening &<br/>Completeness Check]
    
    Screen --> Complete{Complete?}
    Complete -->|No| RequestInfo[Request<br/>Information]
    RequestInfo --> AwaitResponse[Await Claimant<br/>Response]
    AwaitResponse -->|30 days| Timeout{Response<br/>Received?}
    Timeout -->|No| AutoReject[Auto-Reject Claim]
    AutoReject --> NotifyReject[Notify Rejection]
    NotifyReject --> EndReject((End))
    Timeout -->|Yes| Screen
    Complete -->|Yes| Validate[Validate against<br/>USP Guidelines]
    
    Validate --> Valid{Valid<br/>Claim?}
    Valid -->|No| Reject[Reject Claim]
    Reject --> Document[Document Rejection<br/>Reason]
    Document --> NotifyReject2[Notify Claimant]
    NotifyReject2 --> EndReject2((End))
    
    Valid -->|Yes| Eligibility[Check Eligibility<br/>& Budget]
    Eligibility --> Budget{Budget<br/>Available?}
    Budget -->|No| Hold[Place on Hold]
    Hold --> NotifyHold[Notify Claimant]
    NotifyHold --> EndHold((End - On Hold))
    
    Budget -->|Yes| Assess[Technical Assessment]
    Assess --> Recommend{Recommendation}
    
    Recommend -->|Approve| PrepareApproval[Prepare Approval<br/>Package]
    Recommend -->|Reduce| Calculate[Calculate Revised<br/>Amount]
    Calculate --> PrepareApproval
    Recommend -->|Reject| Reject2[Prepare Rejection]
    Reject2 --> EndReject3((End))
    
    PrepareApproval --> Route{Amount >r/>Threshold?}
    Route -->|No| Approve[Section Head<br/>Approval]
    Route -->|Yes| Escalate[Director<br/>Approval]
    
    Approve --> Decision{Approved?}
    Escalate --> Decision
    
    Decision -->|No| Reject3[Reject]
    Reject3 --> EndReject4((End))
    Decision -->|Yes| GenerateNOA[Generate NOA]
    GenerateNOA --> SendNOA[Send NOA to<br/>Claimant]
    SendNOA --> UpdateBudget[Update Budget<br/>Allocation]
    UpdateBudget --> Log[(Audit Log)]
    Log --> EndApprove((End - Approved))
```

**Approval Matrix:**

| Claim Amount | First Approver | Second Approver | Final Authority |
|--------------|----------------|-----------------|-----------------|
| ≤ RM 50,000 | Claims Officer | Section Head | - |
| RM 50,001 - 200,000 | Section Head | Director | - |
| > RM 200,000 | Director | Deputy Chairman | Chairman |

---

### 3.3 Document Management Process

```mermaid
flowchart TB
    Upload[Document Uploaded] --> VirusScan[Virus Scan]
    VirusScan --> Clean{Clean?}
    
    Clean -->|No| Quarantine[Move to<br/>Quarantine]
    Quarantine --> Alert[Alert Security<br/>Team]
    Alert --> EndVirus((End - Blocked))
    
    Clean -->|Yes| Classify[Auto-Classification]
    Classify --> Extract[Metadata Extraction]
    Extract --> OCR[OCR Processing]
    
    OCR --> Index[Index Document]
    Index --> Store[Store in Document<br/>Management System]
    Store --> Encrypt[Apply Encryption]
    Encrypt --> Backup[Replicate to<br/>Backup Storage]
    
    Backup --> Retention[Apply Retention<br/>Policy]
    Retention --> Link[Link to Parent<br/>Record]
    Link --> Notify[Notify Upload<br/>Complete]
    Notify --> Log[(Audit Log)]
    Log --> EndSuccess((End - Stored))
```

**Document Lifecycle:**

| Stage | Duration | Action |
|-------|----------|--------|
| Active | 7 years | Full access, regular backup |
| Archive | 3 years | Read-only, offline storage |
| Disposal | - | Secure deletion per policy |

---

### 3.4 Payment Processing Workflow

```mermaid
flowchart TB
    Start((NOA<br/>Accepted)) --> Verify[Verify Bank<br/>Account Details]
    Verify --> BankValid{Valid<br/>Account?}
    
    BankValid -->|No| RequestBank[Request Correct<br/>Bank Details]
    RequestBank --> Verify
    
    BankValid -->|Yes| Calculate[Calculate Payment<br/>Schedule]
    Calculate --> Milestone{Milestone-<br/>Based?}
    
    Milestone -->|Yes| Split[Split by<br/>Milestones]
    Split --> Schedule[Create Payment<br/>Schedule]
    Milestone -->|No| LumpSum[Single Payment]
    LumpSum --> Schedule
    
    Schedule --> Approve[Finance Approval]
    Approve --> FinanceOk{Approved?}
    
    FinanceOk -->|No| Revise[Revise Payment<br/>Terms]
    Revise --> Schedule
    
    FinanceOk -->|Yes| Process[Process Payment]
    Process --> BankAPI[Call Banking<br/>API]
    BankAPI --> Success{Payment<br/>Success?}
    
    Success -->|No| Retry{Retry<br/>Count < 3?}
    Retry -->|Yes| Requeue[Requeue for<br/>Retry]
    Requeue --> Process
    Retry -->|No| Escalate[Escalate to<br/>Finance Team]
    Escalate --> EndFail((End - Failed))
    
    Success -->|Yes| Confirm[Confirm Payment]
    Confirm --> GenerateRef[Generate Payment<br/>Reference]
    GenerateRef --> Receipt[Generate Receipt]
    Receipt --> SendReceipt[Send Receipt to<br/>Claimant]
    SendReceipt --> UpdateClaim[Update Claim<br/>Status]
    UpdateClaim --> BudgetUpdate[Update Budget<br/>Actuals]
    BudgetUpdate --> Log[(Audit Log)]
    Log --> EndSuccess((End - Paid))
```

---

### 3.5 User Registration & Onboarding

```mermaid
flowchart TB
    Start((Start)) --> SelectType[Select User Type]
    SelectType --> Type{User Type}
    
    Type -->|Internal| IntForm[Fill Internal<br/>User Form]
    Type -->|External| ExtForm[Fill External<br/>User Form]
    Type -->|Company| CompForm[Fill Company<br/>Registration]
    
    IntForm --> ValidateInt[Validate Employee<br/>ID against HR]
    ExtForm --> ValidateExt[Verify Identity<br/>Documents]
    CompForm --> ValidateComp[Validate against<br/>CIMS/SSM]
    
    ValidateInt --> Valid{Valid?}
    ValidateExt --> Valid
    ValidateComp --> Valid
    
    Valid -->|No| RejectReg[Reject Registration]
    RejectReg --> NotifyReject[Notify with<br/>Reason]
    NotifyReject --> EndReject((End))
    
    Valid -->|Yes| CreateAccount[Create User<br/>Account]
    CreateAccount --> AssignRole[Assign Default<br/>Role]
    AssignRole --> SetPerm[Set Permissions]
    SetPerm --> SendCreds[Send Credentials<br/>Securely]
    
    SendCreds --> MFA{MFA<br/>Required?}
    MFA -->|Yes| SetupMFA[Setup MFA]
    MFA -->|No| SkipMFA[Skip MFA Setup]
    
    SetupMFA --> CompleteProfile[Complete Profile]
    SkipMFA --> CompleteProfile
    
    CompleteProfile --> Training[Assign Training<br/>Modules]
    Training --> NotifySuccess[Notify Registration<br/>Complete]
    NotifySuccess --> Log[(Audit Log)]
    Log --> EndSuccess((End - Active))
```

**User Types & Roles:**

| User Type | Registration Flow | Approval Required | Default Role |
|-----------|-------------------|-------------------|--------------|
| Internal (MCMC) | Employee ID validation | Manager approval | Based on department |
| External (Industry) | Company + SSM validation | Admin approval | Claimant |
| Auditor | Special registration | Director approval | Read-Only Auditor |
| System Admin | Internal only | IT Director approval | Administrator |

---

### 3.6 Audit & Compliance Process

```mermaid
flowchart TB
    Schedule[Scheduled Audit/<br/>Ad-hoc Request] --> DefineScope[Define Audit<br/>Scope]
    DefineScope --> SelectSample[Select Sample<br/>Records]
    SelectSample --> Extract[Extract Data<br/>from Systems]
    
    Extract --> Analyze[Analyze against<br/>Policies]
    Analyze --> Findings{Findings?}
    
    Findings -->|No| GenerateClear[Generate Clear<br/>Audit Report]
    GenerateClear --> Archive[Archive Report]
    Archive --> EndClear((End - Clear))
    
    Findings -->|Yes| Classify[Classify Finding<br/>Severity]
    Classify --> Severity{Severity}
    
    Severity -->|Critical| Immediate[Immediate<br/>Action Required]
    Severity -->|High| Urgent[Urgent Action<br/>- 7 days]
    Severity -->|Medium| Standard[Standard Action<br/>- 30 days]
    Severity -->|Low| Monitor[Monitor &<br/>Document]
    
    Immediate --> NotifyExec[Notify Executive<br/>Management]
    Urgent --> NotifyMgmt[Notify Department<br/>Head]
    Standard --> AssignOwner[Assign Action<br/>Owner]
    Monitor --> DocumentLow[Document for<br/>Tracking]
    
    NotifyExec --> Track[Track Remediation]
    NotifyMgmt --> Track
    AssignOwner --> Track
    DocumentLow --> Track
    
    Track --> Resolved{Resolved?}
    Resolved -->|No| Escalate[Escalate<br/>if Overdue]
    Escalate --> Track
    Resolved -->|Yes| Verify[Verify<br/>Remediation]
    Verify --> Close[Close Finding]
    Close --> GenerateReport[Generate Final<br/>Report]
    GenerateReport --> Store[(Store in<br/>Audit System)]
    Store --> EndAudit((End - Closed))
```

---

### 3.7 System Backup & Recovery

```mermaid
flowchart TB
    Schedule[Scheduled Backup<br/>Trigger] --> Type{Backup Type}
    
    Type -->|Full| FullBackup[Perform Full<br/>Database Backup]
    Type -->|Incremental| IncBackup[Perform Incremental<br/>Backup]
    Type -->|Archive| ArchiveBackup[Archive Old<br/>Data]
    
    FullBackup --> VerifyBackup[Verify Backup<br/>Integrity]
    IncBackup --> VerifyBackup
    ArchiveBackup --> VerifyArchive[Verify Archive]
    
    VerifyBackup --> Success{Verification<br/>Success?}
    VerifyArchive --> ArchiveSuccess{Archive<br/>Success?}
    
    Success -->|No| Retry{Retry<br/>Attempt?}
    Retry -->|Yes| FullBackup
    Retry -->|No| Alert[Alert Operations<br/>Team]
    Alert --> LogFailure[Log Failure]
    LogFailure --> EndFail((End - Failed))
    
    Success -->|Yes| Encrypt[Encrypt Backup]
    ArchiveSuccess -->|Yes| Encrypt
    
    Encrypt --> Transfer[Transfer to<br/>DR Site]
    Transfer --> Store[(Store in<br/>Backup Storage)]
    Store --> UpdateCatalog[Update Backup<br/>Catalog]
    UpdateCatalog --> CleanOld[Clean Old<br/>Backups per Policy]
    CleanOld --> Notify[Notify Backup<br/>Success]
    Notify --> Log[(Audit Log)]
    Log --> EndSuccess((End - Success))
```

**Backup Schedule:**

| Backup Type | Frequency | Retention | Storage Location |
|-------------|-----------|-----------|------------------|
| Full Database | Weekly | 4 weeks | Primary + DR |
| Incremental | Daily | 14 days | Primary + DR |
| Transaction Log | Every 15 min | 48 hours | Primary + DR |
| Archive | Monthly | 7 years | Offsite Tape |
| Configuration | On change | 12 versions | Git + DR |

---

## 4. CROSS-FUNCTIONAL PROCESS MAP

### 4.1 End-to-End Claim Lifecycle

```mermaid
flowchart LR
    subgraph "Claimant"
        A1[Submit Claim]
        A2[Respond to Queries]
        A3[Accept NOA]
    end

    subgraph "Claims Officer"
        B1[Screen Claim]
        B2[Assess Claim]
        B3[Prepare Package]
    end

    subgraph "Approver"
        C1[Review & Decide]
        C2[Sign NOA]
    end

    subgraph "Finance"
        D1[Verify Budget]
        D2[Process Payment]
    end

    subgraph "System"
        E1[Generate ID]
        E2[Route Workflow]
        E3[Archive Record]
    end

    A1 --> E1
    E1 --> B1
    B1 -->|Incomplete| A2
    A2 --> B1
    B1 -->|Complete| B2
    B2 --> B3
    B3 --> E2
    E2 --> C1
    C1 -->|Approved| C2
    C1 -->|Rejected| E3
    C2 --> D1
    D1 --> D2
    D2 --> A3
    A3 --> E3
```

---

## 5. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | January 2025 | Process Modeling Team | Initial version |

---

**END OF ANNEX T5**
