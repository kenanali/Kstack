# Service Blueprint: Mortgage Application Journey

**Skill:** /service-map
**Journey:** Mortgage Application
**Date:** 2026-03-23

---

## Step 0: Context Loaded

**Journey:** Mortgage Application — 5 stages
**Systems inventory confirmed:**
- Online banking portal
- Document upload system
- Credit decisioning engine (legacy)
- CRM (Salesforce)
- Notifications system (email + SMS)
- Core banking

**Teams:** Digital/Web, Credit Operations, Home Loan Specialists, Settlement Team

**Known failure points:** None provided — identified through blueprint analysis below.

---

## Section 1: Stage-by-Stage Blueprint

---

### STAGE 1: Discovering and Applying Online

| Layer | Description |
|---|---|
| **CUSTOMER ACTIONS** | Searches for mortgage products online; compares rates and features; uses repayment calculator; selects product; begins application form; enters personal, financial, and employment details; submits initial application |
| **FRONTSTAGE** | Online banking portal displays product options and rates; application form collects customer data; real-time field validation; confirmation screen on submission; automated email acknowledgment sent |
| **--- LINE OF VISIBILITY ---** | |
| **BACKSTAGE** | Application data written to CRM (Salesforce); Digital/Web team monitors form completion and drop-off rates; no human review at this stage; application queued for processing |
| **SUPPORT PROCESSES** | Digital/Web team maintains portal and form logic; CRM integration keeps application record current; marketing and product data feeds rate display; Identity verification triggered (if integrated at this point) |
| **SYSTEMS** | Online banking portal (form, calculator, product display) → CRM (Salesforce) record creation; Notifications system sends acknowledgment email; Core banking not yet engaged |

**Failure Points:**
- Form abandonment due to length or ambiguity — no save-and-return functionality confirmed
- Rate displayed on portal may not match rate locked at submission (data freshness lag)
- CRM record creation failure creates silent drop — customer receives confirmation but application is not logged
- No identity verification at this stage means fraudulent or incomplete applications proceed unchecked

**Handoff Risks:**
- Portal → CRM: data mapping errors can corrupt application record at creation; no human review catches these

**Complexity Rating: Medium**
Key reason: Largely automated, but silent failures in portal-to-CRM handoff and rate data accuracy create downstream problems that are invisible to both customer and staff at this stage.

---

### STAGE 2: Document Submission

| Layer | Description |
|---|---|
| **CUSTOMER ACTIONS** | Receives document checklist (email); gathers payslips, bank statements, tax returns, ID; uploads documents via document upload system; waits for confirmation; re-uploads if rejected or additional items requested |
| **FRONTSTAGE** | Document upload system provides checklist and upload interface; automated email/SMS acknowledgment on upload; rejection or request for additional documents communicated via notifications system |
| **--- LINE OF VISIBILITY ---** | |
| **BACKSTAGE** | Credit Operations receives documents in queue; staff manually review document completeness and quality; incomplete submissions flagged and returned; documents manually indexed and attached to CRM record; Home Loan Specialists may make outbound contact if customer stalls |
| **SUPPORT PROCESSES** | Credit Operations team triages and routes document packs; document quality standards enforced manually; CRM updated with document status; Home Loan Specialists monitor stalled applications and follow up |
| **SYSTEMS** | Document upload system (customer-facing) → manual review by Credit Operations; documents linked to CRM (Salesforce) record; notifications system sends status updates; credit decisioning engine not yet engaged |

**Failure Points:**
- Document upload system provides no real-time quality check — customers upload blurry, incomplete, or wrong documents and are notified days later
- No status visibility between upload and Credit Operations review — customer anxiety gap, drives inbound calls
- Manual document indexing to CRM is error-prone and creates mismatched records
- Home Loan Specialist outreach is inconsistent — some stalled applications go unfollowed for extended periods
- Document requirements not clearly communicated upfront — customers frequently submit incomplete packs on first attempt

**Handoff Risks:**
- Document upload system → Credit Operations queue: no SLA enforcement, no prioritization logic — older applications can be buried
- Credit Operations → CRM: manual update means CRM record lags reality, other staff see stale status

**Complexity Rating: Very High**
Key reason: Entirely manual processing behind an automated-looking facade; multiple failure modes invisible to the customer; highest volume of inbound complaints and re-work concentrated at this stage.

---

### STAGE 3: Credit and Eligibility Assessment

| Layer | Description |
|---|---|
| **CUSTOMER ACTIONS** | Waits; may receive requests for additional information; makes follow-up calls or portal logins to check status; if stalled, may consider competitors |
| **FRONTSTAGE** | Occasional outbound contact from Home Loan Specialist if additional info needed; no proactive status updates in most cases; portal shows generic "under review" status |
| **--- LINE OF VISIBILITY ---** | |
| **BACKSTAGE** | Credit Operations submits application to credit decisioning engine (legacy); analysts review system output, apply manual overrides and judgment; serviceability calculations run; fraud checks performed; application referred to Home Loan Specialist for complex cases; final credit recommendation prepared |
| **SUPPORT PROCESSES** | Credit Operations manages queue and applies policy; Home Loan Specialists handle referrals and exceptions; compliance and risk teams involved in policy edge cases; core banking queried for existing customer data |
| **SYSTEMS** | Credit decisioning engine (legacy) — primary assessment tool; CRM (Salesforce) — application record and case notes; Core banking — customer financial history; no automated status push to customer-facing systems during assessment |

**Failure Points:**
- Legacy credit decisioning engine produces outputs that require significant manual interpretation — high analyst cognitive load, inconsistency between analysts
- Engine downtime or latency (legacy system) creates processing backlogs with no customer notification
- No real-time status feed from decisioning engine to CRM — staff manually update CRM, creating lag
- Manual override culture: inconsistent decisions on comparable applications depending on which analyst handles the case
- Customer-facing portal shows no meaningful status — "under review" is uninformative and anxiety-inducing; drives high inbound call volume to Credit Operations (deflecting from assessment work)
- Complex or edge-case applications stall in referral queue when Home Loan Specialists are at capacity

**Handoff Risks:**
- Credit Operations → Home Loan Specialists (referrals): handoff criteria inconsistently applied; referred cases lack full context, requiring rework
- Credit decisioning engine output → analyst review: no structured handoff — analysts receive raw output with varying levels of supporting documentation

**Complexity Rating: Very High**
Key reason: Legacy system dependency, manual override reliance, zero proactive customer communication, and inter-team referral ambiguity make this the highest-risk stage in the journey. Decision quality and turnaround time are both variable.

---

### STAGE 4: Decision Communication

| Layer | Description |
|---|---|
| **CUSTOMER ACTIONS** | Receives approval, conditional approval, or decline via email/SMS or phone call from Home Loan Specialist; reviews offer documents; asks questions; accepts or declines offer; if conditional, provides additional items |
| **FRONTSTAGE** | Home Loan Specialist phones approved customers to deliver decision and explain offer; notifications system sends formal letter/document; conditional approval triggers additional document requests; declined customers receive standardized letter |
| **--- LINE OF VISIBILITY ---** | |
| **BACKSTAGE** | Home Loan Specialists prepare and dispatch offer letters; communicate conditions to customer; update CRM with decision and customer response; escalations handled by senior specialists; declined customers may request review |
| **SUPPORT PROCESSES** | Credit Operations passes decision to Home Loan Specialists; document management for formal offer letters; compliance review of decline communications; senior escalation path |
| **SYSTEMS** | CRM (Salesforce) — decision recorded, communication logged; notifications system — formal letter and document delivery; core banking — not yet engaged for settlement; document generation system (if separate — unclear) |

**Failure Points:**
- Declined customers receive form letters with no personalisation and insufficient explanation — regulatory exposure and high complaint rate
- Approval-to-offer letter lag: decision made but letter not dispatched promptly due to manual preparation
- Conditional approval communication inconsistent — conditions not always clearly specified, leading to repeat document requests
- Home Loan Specialist phone call to approved customers sometimes not made (capacity issue), leaving customer to discover decision via letter alone with no opportunity to ask questions
- Offer document errors (name, rate, amount) require rework and re-issue, delaying settlement entry

**Handoff Risks:**
- Credit Operations (decision) → Home Loan Specialist (communication): decision data passed via CRM update only — specialist must interpret CRM notes, not always complete
- Home Loan Specialist → notifications system: manual trigger for letter dispatch — easily forgotten or delayed under workload

**Complexity Rating: High**
Key reason: Human-dependent communication at a high-stakes moment creates inconsistency; declining customers is structurally under-resourced; document preparation is manual and error-prone.

---

### STAGE 5: Settlement

| Layer | Description |
|---|---|
| **CUSTOMER ACTIONS** | Confirms settlement date with solicitor/conveyancer; reviews and signs loan documents; follows up on settlement progress; receives confirmation of settlement; loan funded and property transfer complete |
| **FRONTSTAGE** | Settlement Team coordinates with customer and third parties; notifications sent on key settlement milestones; Home Loan Specialist available for queries; settlement date confirmed |
| **--- LINE OF VISIBILITY ---** | |
| **BACKSTAGE** | Settlement Team coordinates with solicitor/conveyancer, real estate agent, and vendor's lender; prepares loan documents; books settlement; arranges funds transfer via core banking; manages last-minute issues (delays, shortfalls, title issues) |
| **SUPPORT PROCESSES** | Settlement Team ↔ solicitor/conveyancer coordination; core banking funds management; compliance sign-off on settlement documentation; Home Loan Specialist available for customer escalation |
| **SYSTEMS** | Core banking — funds management, loan account creation; CRM (Salesforce) — settlement record, communication log; notifications system — settlement date and completion confirmation; document management for executed loan documents |

**Failure Points:**
- Settlement Team coordination with external parties (solicitors, conveyancers) relies on manual phone/email — no integrated workflow, no shared visibility
- Last-minute settlement delays due to external party issues create customer distress with no proactive communication protocol
- Core banking loan account creation can fail or produce errors requiring manual correction — settlement day delays
- Document execution errors (incorrect dates, amounts) discovered at or near settlement create emergency rework
- Customer not proactively informed of settlement progress — discovers completion passively

**Handoff Risks:**
- Home Loan Specialist → Settlement Team: incomplete handoff of customer preferences, conditions, and special circumstances
- Settlement Team → Core banking: manual funds instruction submission — timing-sensitive with no automated fallback
- Settlement Team → external parties: no SLA enforcement mechanism; entirely relationship-dependent

**Complexity Rating: High**
Key reason: High dependency on external parties outside organisational control; manual coordination with core banking at a timing-critical moment; insufficient proactive customer communication at a high-emotion moment.

---

## Section 2: Failure Point Register

| Failure Point | Stage | Layer | Severity | Root Cause Hypothesis | Frequency |
|---|---|---|---|---|---|
| CRM record creation failure — application not logged despite customer confirmation | Stage 1: Apply | Systems | High | No error handling or reconciliation between portal and CRM integration | Occasional |
| Rate displayed ≠ rate locked at submission | Stage 1: Apply | Systems | Med | Rate data cache not synchronised in real time | Occasional |
| Form abandonment with no save-and-return | Stage 1: Apply | Frontstage | Med | Portal designed for completion in one session; no persistent session management | Common |
| Document upload system provides no real-time quality check | Stage 2: Documents | Systems/Frontstage | High | Upload system is a file transfer tool, not an intelligent intake system; no OCR or validation layer | Common |
| No status visibility between upload and Credit Operations review | Stage 2: Documents | Support Processes | High | No integration between document upload system and CRM status field; manual update only | Common |
| Manual document indexing error — mismatched records | Stage 2: Documents | Backstage | High | No automated document-to-application matching; all attachment done manually | Common |
| Legacy credit decisioning engine downtime/latency creates unnotified backlog | Stage 3: Assessment | Systems | High | Legacy infrastructure with no redundancy; no SLA monitoring connected to customer-facing status | Occasional |
| Inconsistent decisions on comparable applications | Stage 3: Assessment | Backstage | High | Manual override culture without structured decision rules; no quality review mechanism | Common |
| Portal shows "under review" — no meaningful status | Stage 3: Assessment | Frontstage | Med | No integration between decisioning engine and portal status display | Common |
| Home Loan Specialist referral queue stalls on complex cases | Stage 3: Assessment | Support Processes | High | No capacity management or priority routing in referral workflow | Occasional |
| Declined customers receive form letter — no explanation | Stage 4: Decision | Frontstage | High | Decline communication is standardised to manage compliance/legal risk but creates complaint risk | Common |
| Conditional approval conditions not clearly specified | Stage 4: Decision | Frontstage | Med | No structured template for conditional communication; specialist-by-specialist variation | Common |
| Offer document errors require rework and re-issue | Stage 4: Decision | Backstage | Med | Manual document preparation without systematic data pull from CRM | Occasional |
| Settlement Team ↔ external party coordination relies on manual phone/email | Stage 5: Settlement | Backstage | High | No integrated conveyancer/solicitor portal or workflow; entirely relationship-managed | Common |
| Core banking loan account creation failures on settlement day | Stage 5: Settlement | Systems | High | Manual funds instruction submission; legacy core banking with low fault tolerance | Occasional |
| Customer not proactively informed of settlement progress | Stage 5: Settlement | Frontstage | Med | No automated milestone notifications from settlement workflow; ad hoc communication | Common |

---

## Section 3: Handoff Risk Register

| Handoff | From → To | Stage | Risk | What can go wrong |
|---|---|---|---|---|
| Application submission | Online banking portal → CRM (Salesforce) | Stage 1 | High | Data mapping errors corrupt application record at creation; silent failures produce confirmation without CRM record |
| Document receipt | Document upload system → Credit Operations queue | Stage 2 | High | No SLA enforcement; no prioritisation; older applications buried; no alert on stuck items |
| Document status update | Credit Operations → CRM | Stage 2 | Med | Manual update creates lag; other staff see stale status; Home Loan Specialist acts on outdated information |
| Assessment referral | Credit Operations → Home Loan Specialists | Stage 3 | High | Inconsistent referral criteria; referred cases lack full context; specialist must reconstruct file, creating delays and potential error |
| Decision dispatch | Credit Operations (decision) → Home Loan Specialist (communication) | Stage 4 | Med | CRM note handoff only; specialist must interpret incomplete notes; conditions may be lost or misread |
| Offer letter trigger | Home Loan Specialist → Notifications system | Stage 4 | Med | Manual trigger; easily delayed under workload; customer waits with no status |
| Case handover | Home Loan Specialist → Settlement Team | Stage 5 | High | Customer context, conditions, and preferences not systematically transferred; Settlement Team operates from incomplete CRM record |
| Funds instruction | Settlement Team → Core banking | Stage 5 | High | Manual submission at timing-critical moment; no automated fallback; failure causes same-day settlement collapse |
| External coordination | Settlement Team → Solicitor/Conveyancer | Stage 5 | High | No shared workflow or SLA; entirely relationship-managed; third-party delays have no escalation mechanism |

---

## Section 4: Complexity Rating Summary

| Stage | Complexity | Key Reason |
|---|---|---|
| Stage 1: Discovering and Applying Online | Medium | Largely automated but silent CRM failures and rate data gaps create invisible downstream problems |
| Stage 2: Document Submission | Very High | Manual processing behind automated facade; highest re-work volume; no status visibility creates inbound call spike |
| Stage 3: Credit and Eligibility Assessment | Very High | Legacy system dependency; manual override inconsistency; zero proactive customer communication; referral queue ambiguity |
| Stage 4: Decision Communication | High | Human-dependent at high-stakes moment; declining customer communication structurally under-resourced; manual document preparation error-prone |
| Stage 5: Settlement | High | External party dependency outside organisational control; timing-critical manual core banking instructions; proactive communication absent |

---

## Section 5: Top 3 Systemic Design Opportunities

**1. Redesigning the document intake and processing layer would dramatically reduce application cycle time and customer anxiety by enabling real-time submission feedback and automated completeness checks — currently preventing this because the document upload system is a passive file transfer tool with no intelligence layer, requiring manual human review for every submission before the process can advance.**

Fixing this single backstage bottleneck would address: the highest-volume failure point in the journey (incomplete document submissions), the greatest source of inbound call volume (status anxiety during Stage 2–3 wait), and the manual indexing errors that corrupt CRM records and downstream decisions.

**2. Redesigning the credit decisioning engine integration with the CRM and customer-facing portal would give customers meaningful real-time status visibility and reduce analyst decision inconsistency — currently the legacy engine operates as a black box with no output integration to either the CRM or the portal, forcing manual status updates, hiding processing delays, and producing analyst-by-analyst variation with no quality review mechanism.**

This would address the complete absence of proactive communication across Stages 3 and 4 — the two highest-emotion, lowest-satisfaction stages — and reduce inbound contacts that currently disrupt Credit Operations assessment capacity.

**3. Redesigning the settlement coordination workflow — replacing manual phone/email coordination with an integrated multi-party platform (lender, solicitor, conveyancer) — would reduce settlement-day failure rates and eliminate the customer distress caused by last-minute delays that have no communication protocol.**

Settlement failures are low in frequency but catastrophic in customer impact (highest emotional stakes in the entire journey). The root cause is entirely structural: there is no shared workflow, SLA, or escalation mechanism between the bank and the external parties who co-produce the outcome. This cannot be fixed at the frontstage level.

---

*Generated by /service-map | KStack CX Transformation Skill System*
