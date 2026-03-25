# CX Initiative Prioritization
## EVAL-18 | prioritize | Prompt 1

---

## Clarifying Questions Before Scoring

Two things I need to resolve before I can score these accurately:

**Initiative 3 — Proactive Complaint Prediction Model:**
Is this a net-new AI/ML capability build (requiring data infrastructure, model development, and integration), or do you have existing data infrastructure and this is primarily a model-training and integration effort? The feasibility score swings significantly between these two.

**Initiative 7 — Digital Onboarding:**
Who is the target customer for "new customers"? Is this the premium segment (aligns with Strategic Priority 1) or all new customers? And what's the current completion rate for onboarding — is this fixing a broken process or building a new capability from scratch?

*[Note: In an interactive session, I would wait for answers. For this evaluation, I'm proceeding with stated assumptions below and flagging them explicitly.]*

**Assumptions I'm making:**
- Initiative 3: Treating as a net-new AI/ML build requiring data infrastructure — this is the more common scenario and the more conservative feasibility assumption.
- Initiative 7: Treating as applicable to all new customers with premium segment being a key beneficiary. Treating as fixing a friction-heavy existing process, not starting from zero.

---

## Section 1: Scoring Table

**Criteria and weights:**
- Strategic Alignment (25%): Does this directly advance the stated priorities (grow premium segment, reduce cost-to-serve, improve NPS)?
- Customer Impact (35%): Significance of direct improvement to customer experience and outcomes.
- Feasibility (25%): Deliverable within $4M budget, 12-person team, 18-month horizon.
- Time-to-Value (15%): Speed to demonstrable results — something to show in 6 months.

**Scale: 1 (low) → 5 (high)**

| # | Initiative | Strategic Alignment (25%) | Customer Impact (35%) | Feasibility (25%) | Time-to-Value (15%) | Composite | Notes |
|---|---|---|---|---|---|---|---|
| 1 | Real-time application status tracker | 4 | 4 | 4 | 4 | **4.00** | Directly reduces friction and NPS drag; buildable with existing mobile platform; visible in 6 months |
| 2 | Agent empowerment program | 4 | 5 | 4 | 3 | **4.20** | Reduces cost-to-serve (repeat contacts, AHT) and NPS simultaneously; requires training + authority redesign — 6-month results possible but full value takes 12+ months |
| 3 | Proactive complaint prediction model | 3 | 3 | 2 | 1 | **2.40** | High potential but requires data infrastructure, model development, and integration; 6-month deliverable is unlikely; team capacity is a binding constraint |
| 4 | Complaint process redesign | 4 | 4 | 4 | 3 | **3.90** | High NPS and cost-to-serve impact; manageable scope; value visible at 9–12 months |
| 5 | CRM system replacement | 2 | 2 | 1 | 1 | **1.70** | Already funded, non-negotiable — but scoring it shows why it shouldn't consume optional budget. High risk, low direct CX value in the short term, all effort |
| 6 | Voice of customer program (NPS + interviews) | 3 | 2 | 5 | 5 | **3.25** | Foundational to measuring everything else; high feasibility and speed; but limited direct customer impact — it enables, doesn't deliver |
| 7 | Digital onboarding | 5 | 4 | 3 | 3 | **3.90** | Strongest strategic alignment (premium segment + NPS + cost-to-serve); moderate feasibility given CRM dependency; value at 9–12 months |

**Sorted by composite score:**

| Rank | Initiative | Composite |
|---|---|---|
| 1 | Agent Empowerment Program | 4.20 |
| 2 | Real-time Application Status Tracker | 4.00 |
| 3 | Complaint Process Redesign | 3.90 |
| 3= | Digital Onboarding | 3.90 |
| 5 | Voice of Customer Program | 3.25 |
| 6 | Proactive Complaint Prediction Model | 2.40 |
| 7 | CRM System Replacement | 1.70 |

**Before proceeding: do any of these scores seem significantly wrong to you?** The most contestable calls are: (a) Agent Empowerment at 4.20 — if your team believes the real cost driver is something other than agent empowerment, the Strategic Alignment and Customer Impact scores should be revisited. (b) Complaint Process Redesign at 3.90 — if your complaint volumes are relatively low, the impact score should drop. (c) Proactive Complaint Prediction at 2.40 — if you have existing ML infrastructure I'm not aware of, feasibility improves significantly.

---

## Section 2: Portfolio View

```
                        HIGH IMPACT
                              │
              Digital          │         Agent
              Onboarding       │         Empowerment
              (strategic bet)  │         (strategic bet)
                               │
              Complaint        │         Real-time Status
              Process          │         Tracker
              Redesign         │         (quick win)
HIGH ─────────────────────────────────────────────── LOW
EFFORT        VoC Program     │                     EFFORT
              (quick win /     │
              capability       │
              builder)         │
                               │
              Complaint        │         [CRM —
              Prediction       │          non-optional,
              (deprioritize)   │          tracked separately]
                               │
                        LOW IMPACT
```

**Quadrant assignments:**

**Quick Wins (High Impact / Low Effort):**
- Real-time Application Status Tracker — visible customer improvement, probably achievable on existing mobile platform, demonstrable in 4–6 months
- VoC Program — fast to stand up, high feasibility, but *impact is indirect* — it enables you to measure and improve everything else

**Strategic Bets (High Impact / High Effort):**
- Agent Empowerment Program — significant training, authority redesign, and process change; high payoff on NPS and cost-to-serve
- Digital Onboarding — premium segment alignment and multi-strategic-priority coverage; constrained by CRM dependency
- Complaint Process Redesign — meaningful scope; end-to-end process change takes time to execute well

**Capability Builders (Lower immediate impact, builds future capability):**
- VoC Program sits here when viewed over a longer horizon — it produces the data that makes future prioritization and measurement credible

**Deprioritize:**
- Proactive Complaint Prediction Model — feasibility is the binding constraint; absorbs team and budget capacity that produces better ROI elsewhere right now
- CRM Replacement — already funded and non-optional; tracked separately; not competing for optional budget

---

## Section 3: Sequencing Recommendation

**The core logic: start with what delivers visible value in 6 months, fund what builds toward 12-month impact, and don't let CRM consume team attention that belongs to customer-facing initiatives.**

### Now (Months 1–6): Two parallel tracks

**Track A — Real-time Application Status Tracker**
Start immediately. This is the highest feasibility, highest time-to-value initiative in the portfolio. It directly addresses the most common source of inbound friction (status anxiety), it's visible to customers quickly, and it gives you something concrete to report at the 6-month mark. Assign 2–3 product/digital team members.

**Track B — VoC Program foundations**
Run in parallel, but keep it lean. You need NPS infrastructure to measure whether any of these initiatives are working. Without a VoC program, you'll be running a $4M portfolio blind. This does not need to be expensive — 4–6 post-interaction surveys, a structured interview cadence, and a reporting dashboard is sufficient to start. 1–2 team members.

**Dependency note:** Track B also produces the data that will sharpen the business case for initiatives later in the sequence.

### Months 3–9: Launch Agent Empowerment + begin Complaint Process Redesign

**Agent Empowerment Program** is the highest-composite initiative and has a natural 6-month lag before full value materialises — start the design and training build in Month 3 to have measurable results by Month 9. This program is the single highest-leverage cost-to-serve lever in the portfolio. Assign 3–4 team members.

**Complaint Process Redesign** can begin root-cause analysis and design in Months 4–6, implementation in Months 7–9. The VoC program will produce early data to sharpen the redesign scope. Assign 2–3 team members.

**CRM management:** The CRM replacement is non-optional and will consume team and vendor attention throughout. Assign 2 team members to CRM governance and integration work. Critically — Digital Onboarding has a dependency on CRM: do not start the full Digital Onboarding build until CRM is sufficiently stable. Run a scoping/design phase in parallel (Months 4–8) to be ready to build once CRM is live.

### Months 9–18: Digital Onboarding

Once the CRM replacement reaches sufficient stability (likely Month 9–12), begin the Digital Onboarding build. This is the initiative with the highest premium-segment alignment — the strategic priority #1. Do not rush it before CRM is ready; a Digital Onboarding experience built on an unstable CRM will degrade quickly and cost more to fix than delay.

### Not in this portfolio cycle: Proactive Complaint Prediction Model

This initiative is deferred — not killed. The conditions for it to be viable are: (a) stable CRM data foundation (requires CRM replacement to be complete), (b) team and budget capacity not consumed by higher-priority initiatives, (c) sufficient complaint volume and data quality to train a meaningful model. Revisit in Month 18 when CRM is complete and early initiatives are delivering value.

---

## Section 4: What We Are Not Doing and Why

**Proactive Complaint Prediction Model — Deferred to Month 18+**

*Why not now:* This initiative has the worst feasibility-to-impact ratio in the portfolio at this stage. Building a meaningful AI/ML prediction model requires: clean, integrated customer data (which you won't have until CRM replacement is complete), data science capability (expensive, in short supply, and not confirmed in your 12-person team), model training time, and integration effort. With $4M total budget and a 12-person team already committed to higher-priority initiatives, this will either be done poorly (a model trained on bad data producing unreliable predictions) or crowd out initiatives with more certain value.

*Revisit when:* CRM is live and data is clean (estimated Month 12–15). At that point, the data foundation exists. If complaint volumes justify it and team capacity allows, this becomes a viable Phase 2 initiative.

**CRM System Replacement — Tracked separately, not prioritized against optional budget**

*Why it's different:* It's already funded and non-negotiable — continuing to include it in prioritization conversations wastes decision-making energy. However, two things about CRM need active management: (1) it will consume significant team and vendor attention that must be explicitly ring-fenced, and (2) Digital Onboarding has a CRM dependency that requires sequencing discipline. The risk is that CRM scope creep silently absorbs team capacity that was allocated to customer-facing initiatives. Assign an explicit "CRM interface budget" from the team and enforce it.

*The honest note:* CRM replacements rarely deliver direct CX value in the short term. The CX value comes from what you build on top of it (Digital Onboarding, Complaint Prediction) — which is exactly why those initiatives are sequenced after CRM stabilises.

---

## Budget Allocation Guidance

*[ASSUMPTION: rough allocation based on typical initiative sizing at stated scale. Validate with your Finance and delivery leads.]*

| Initiative | Estimated Allocation | Team Allocation |
|---|---|---|
| Real-time Application Status Tracker | $400K | 2–3 people, Months 1–6 |
| VoC Program | $200K | 1–2 people, ongoing |
| Agent Empowerment Program | $750K | 3–4 people, Months 3–12 |
| Complaint Process Redesign | $500K | 2–3 people, Months 4–12 |
| Digital Onboarding | $900K | 3–4 people, Months 9–18 |
| CRM management (interface budget) | $250K ring-fenced | 2 people, ongoing |
| **Total** | **$3.0M** | **12 people** |
| Reserve / contingency | $1.0M | — |

Note: The $1M reserve is intentional — CRM replacements and new capability builds almost always have cost overruns or scope additions. Holding 25% in reserve is prudent, not conservative.
