# Scan Blockers — State Government Digital Transactions Program

**Organization:** Large state government department (~3,000 staff)
**Program goal:** Move 60% of citizen transactions online
**Status:** 2 years of effort, minimal progress
**Input materials:** Interview notes (5 quotes provided)

---

## Step 2.5: Check-In Before Full Output

I've identified **12 blockers** across **6 categories** from the materials provided. Before I complete the full severity and grouping assessment, I want to flag what I have — and ask if anything is missing.

> **Draft blocker count: 12 blockers across Culture & Leadership, Org Structure, Process & Operations, Technology & Data, People & Capability, and Regulatory & Compliance.**
>
> Are there blockers you already know about that should be on this list — for example, anything about citizen digital literacy, accessibility obligations, or budget constraints? Anything from the interviews I might have missed?

---

*For this evaluation, proceeding through all steps with available materials.*

---

## Section 1: Blocker Map

### Culture & Leadership

| Blocker | Category | Description | Severity | Addressability |
|---|---|---|---|---|
| Leadership rhetoric-action gap | Culture & Leadership | Senior leaders publicly endorse "digital first" strategy but continue to sign off on paper-heavy processes and approvals — creating a permission structure that contradicts the stated transformation direction and signalling to staff that digital is aspirational, not operational | High | Strategic |
| Political timeline override | Culture & Leadership | Minister has attached a headline transaction-volume target to the electoral cycle, creating pressure to report a number rather than embed a capability — incentivising cosmetic wins (e.g., PDF-to-web form conversions) over genuine end-to-end digital journeys | High | External Constraint |
| Change fatigue and transformation cynicism | Culture & Leadership | Two years of minimal visible progress has likely eroded staff belief that this program will succeed — creating passive resistance, low discretionary effort on implementation tasks, and an "it'll pass" posture that quietly stalls momentum | Med | Strategic |

### Organizational Structure

| Blocker | Category | Description | Severity | Addressability |
|---|---|---|---|---|
| Fragmented digital journey ownership | Org Structure | No evidence of a single accountable owner for the end-to-end citizen digital journey — digital, policy, service delivery, and IT teams likely each own a layer without a shared definition of what "60% online" actually means or who is accountable for the outcome | High | Strategic |
| IT as gatekeeper with no delivery mandate | Org Structure | IT team is the primary blocker-identifier (CRM integration problem) but does not appear to have a clear mandate or resourcing to solve it — creating a structure where the team who knows the problem has neither the authority nor the budget to fix it | High | Structural |

### Process & Operations

| Blocker | Category | Description | Severity | Addressability |
|---|---|---|---|---|
| Procurement cycle destroying digital delivery cadence | Process & Operations | 18-month procurement timeline for new software makes it structurally impossible to iterate on digital channel capability at any meaningful pace — by the time a solution is contracted, the original problem has evolved and political pressure has shifted | High | Structural |
| Paper process approvals embedded in governance | Process & Operations | Leadership approval workflows remain paper-based, which not only slows internal operations but models and reinforces paper-as-default throughout the department — digitisation of citizen-facing touchpoints cannot outpace the paper dependency in internal governance | High | Strategic |
| No feedback loop from failed digital transactions to improvement | Process & Operations | No evidence of a mechanism to capture where citizens abandon digital attempts and revert to paper/phone — meaning the program cannot see its own failure rate or learn from it | Med | Quick Win |

### Technology & Data

| Blocker | Category | Description | Severity | Addressability |
|---|---|---|---|---|
| Three-CRM fragmentation with no integration layer | Technology & Data | Three separate CRM systems with no integration capability mean citizen identity, history, and case status cannot be unified — digital self-service journeys that require any form of account recognition or case lookup are either impossible or require manual staff intervention to complete | High | Structural |
| Legacy system architecture blocking digital channel capability | Technology & Data | Core transaction processing systems appear unable to expose APIs or connect to modern digital front-ends — meaning digital forms can capture citizen intent but cannot complete transactions end-to-end without a human re-keying data into backend systems | High | Structural |

### People & Capability

| Blocker | Category | Description | Severity | Addressability |
|---|---|---|---|---|
| Frontline staff perceiving automation as job elimination threat | People & Capability | Staff fear that digital transaction volume increases directly equates to headcount reduction — creating active and passive resistance to adoption, workaround behaviour, and an incentive to keep citizens in paper channels where staff roles are visibly necessary | High | Strategic |
| Change management capability gap | People & Capability | A 3,000-person department moving to digital service delivery requires structured change management at scale — no evidence this capability exists internally, and absence of it is a common reason large government digital programs succeed in pilot and fail at rollout | Med | Strategic |

### Regulatory & Compliance

| Blocker | Category | Description | Severity | Addressability |
|---|---|---|---|---|
| Procurement and legal approval cycles | Regulatory & Compliance | Government procurement rules (18-month cycle noted explicitly) are a structural external constraint — not an internal inefficiency that can be easily waived. Some relief is possible through pre-approved vendor panels, digital-specialist procurement pathways, or sandbox/pilot exemptions, but this requires deliberate navigation | High | External Constraint |

---

## Section 2: Where to Start

**Three blockers with the highest leverage for this program:**

---

**1. The Leadership Rhetoric-Action Gap (Culture & Leadership — High)**

This is the root permission structure for every other blocker. When leaders say "digital first" and then approve paper processes, they are sending a signal throughout a 3,000-person organisation that digital is optional. Staff take their cues from what leadership actually approves, not what it says. The IT team has no urgency to solve the CRM problem if the systems above them still run on paper. Procurement has no pressure to create a faster digital pathway if the ministerial priority is a headline number, not a working system.

Addressing this concretely means making leadership behaviour the intervention, not just the mandate. The first step is a controlled audit: identify the five highest-volume paper processes that still require SES-level approval, and present them to the leadership team as a direct choice — sign-off on digitising these or acknowledge that the program target is not achievable. This forces the gap into the open.

Ownership sits with the Secretary or DG and the program sponsor. Without their visible behavioural change, nothing downstream will move at pace.

---

**2. Three-CRM Fragmentation (Technology & Data — High)**

This is the technical blocker that makes genuine end-to-end digital transactions impossible, not just difficult. A citizen can fill out a beautiful digital form, but if the back-end requires a staff member to re-key their data into a legacy CRM to complete the transaction, that is not a digital transaction — it is a digital intake form attached to a manual process. The 60% target will be gamed (counting form submissions rather than completed transactions) unless this is resolved.

The first step is not a three-year CRM consolidation program. It is a rapid technical assessment to identify which of the highest-volume transaction types can be completed using one of the three existing CRMs — start building digital journeys end-to-end against the most capable system. Run a parallel workstream to identify the minimum viable integration layer (API gateway or middleware) that would allow the other two CRMs to feed and receive from a single citizen-facing digital layer. This avoids a rip-and-replace timeline while creating immediate delivery options.

Ownership is split: the CIO or IT Director owns the architecture decision; the Digital Transformation lead or equivalent owns the product definition of what "complete transaction" means.

---

**3. Procurement Cycle as Program Killer (Regulatory & Compliance / Process & Operations — High)**

18 months is longer than most government electoral cycles, and it is approximately four times the delivery cadence needed to learn and iterate on a digital channel. Every time the program needs a new vendor capability — a digital identity solution, a payments gateway, a case management module — it enters an 18-month queue. This means the program will never be able to respond to what it learns.

The first step is not to fight procurement — it is to work within it strategically. The program should immediately map which vendor capabilities it will need over the next 24 months, and either (a) get those on contract now under existing approved panels, or (b) build a business case to establish a Digital Transformation Standing Panel that pre-approves a shortlist of digital delivery vendors under expedited terms. Several Australian state governments have done this successfully. This requires a procurement specialist with digital program experience, not a general procurement officer.

Ownership sits with the CFO or Chief Procurement Officer in partnership with the program director.

---

## Section 3: Landmines

**Blockers that look manageable but could derail the program:**

---

**Landmine 1: The Job Security Fear (People & Capability)**

This blocker is almost always underestimated in government digital programs because it operates silently. Staff who fear their roles are at risk do not send emails saying so. They process citizen digital inquiries via phone instead of directing them online. They tell citizens the system "doesn't work properly." They escalate edge cases that could be self-served. They generate enough exceptions and workarounds that the digital channel never reaches the transaction volumes needed to prove the model.

Why it's deceptive: The program team will see low digital adoption rates and attribute them to citizen digital literacy or poor UX — both of which are tractable problems. They will not see that frontline staff are the channel routing decision-makers, and those staff have an active incentive to route citizens away from digital.

Early warning signal: Watch for a gap between digital channel availability and digital channel use that doesn't close as UX improves. If the forms are good, the journey is clear, and adoption is still flat — check what frontline staff are saying to citizens at first contact.

---

**Landmine 2: The Electoral Timeline (Culture & Leadership)**

A ministerial target attached to an electoral cycle is not a program delivery target — it is a political communications target. The danger is that it will be met on paper (transactions re-classified, pilots counted as scaled, PDF forms on a website counted as "online") without changing the underlying capability. When the next administration reviews the program, they will find the number was hit but the transformation didn't happen, and the program will be wound back or restarted.

Why it's deceptive: In the short term, ministerial pressure creates momentum — budget gets approved, blockers get cleared, decisions get made. The program will feel like it's working. The deception is that it is working toward a headline, not a durable digital capability.

Early warning signal: When the program team starts having conversations about "what counts" as an online transaction — that is the moment the measurement is being shaped to the target rather than the target driving genuine transformation. Establish a locked-down definition of "completed digital transaction" before that conversation starts.

---

**Landmine 3: Absent Feedback Loop (Process & Operations)**

There is no evidence of a mechanism to capture where citizens abandon digital channels and why. Without this, the program is flying blind — it cannot distinguish between "citizens don't want to use digital" and "the digital experience is broken at a specific step." This sounds like a measurement gap (manageable) but it becomes a landmine when the program uses absence-of-complaint as evidence that the digital channel is working.

Why it's deceptive: Low complaint volumes on a new digital channel usually mean citizens are reverting to phone and paper silently, not that the experience is good. Government departments particularly are not set up to hear from citizens who gave up — they hear from citizens who escalated.

Early warning signal: Track the ratio of digital channel starts to digital channel completions from day one. If this data doesn't exist, build it before any citizen-facing digital capability goes live. A completion rate below 60% on any transaction type is a red flag that needs investigation before scale-up.

---

## Section 4: Data Gaps

The following areas were not covered in the materials provided. Absence of evidence here is not evidence of absence — these may represent additional blockers that would surface with more input.

1. **Citizen digital literacy and access** — No data on the citizen population's digital capability, device access, or internet access. In state government contexts this is often a significant constraint, particularly for transactions involving vulnerable populations. The 60% target may be technically achievable but practically unachievable for specific citizen segments.

2. **Accessibility compliance posture** — No information on whether the department has assessed its digital channel build-out against accessibility obligations (WCAG, Disability Discrimination Act requirements). This is a common late-discovery blocker that forces redesign.

3. **Budget and funding structure** — No information on whether the program has a dedicated budget, how it is structured (capital vs. operational), and whether it is subject to annual budget cycles that create stop-start delivery. 18-month procurement delays suggest this may be symptomatic of a broader funding constraint.

4. **Previous program post-mortems** — Two years of minimal progress implies at least one prior program attempt. No information on what was tried, what failed, and what organizational learning (if any) was captured. This is critical context — the same structural blockers may have been named before without resolution.

5. **Union and industrial relations landscape** — Staff job security fears were noted but the IR environment wasn't described. In a 3,000-person government department, any program affecting roles will intersect with union agreements and consultation obligations. The extent of this constraint is unknown.

6. **Whole-of-government digital infrastructure** — No information on whether the department has access to shared state government digital infrastructure (digital identity platforms, payments gateways, shared service layers). This could significantly accelerate or constrain the program depending on what's available and what's mandated.
