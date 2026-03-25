# Grading Notes: prioritize
## EVAL-18 and EVAL-19

---

## What the Skill Did Well

**1. Clarifying questions were targeted and necessary, not exhaustive.**
The skill definition says "1–2 questions max per initiative, not a full intake form." The response asked questions about two initiatives (Complaint Prediction Model and Digital Onboarding), both of which had genuine ambiguity that would materially affect the scoring. The questions were correctly framed — they ask for information that changes the score, not information that would be "nice to know." This is the right calibration.

**2. The scoring table is transparent and shows its working.**
Each score includes a brief rationale in the notes column — it doesn't just produce a number, it explains the reasoning. This is critical for defensibility: when a senior executive pushes back on a score ("why is CRM at 1.70?"), the facilitator can point to the stated rationale. The composite is correctly calculated as a weighted sum.

**3. The mandatory scoring review was surfaced.**
The skill definition requires Step 2.5: "show full table, ask if any scores seem off before proceeding." The response surfaces this explicitly ("Before proceeding: do any of these scores seem significantly wrong to you?") and identifies the three most contestable scores and why. This is the right behaviour — it creates a conversation checkpoint before the recommendations are anchored.

**4. The CRM treatment is correct and well-argued.**
The skill correctly identifies that CRM is non-negotiable (funded, can't be stopped) and scores it for completeness while treating it separately from the prioritization competition. More importantly, it explains *why* this is the right treatment — it avoids wasting prioritization energy on a decision that's already made, while still accounting for CRM's impact on sequencing and team capacity. The warning about "CRM scope creep silently absorbing team capacity" is a genuine practitioner insight.

**5. The sequencing recommendation has specific dependency logic.**
The recommendation doesn't just say "start with Quick Wins." It explains why Digital Onboarding can't start before CRM stabilises, why VoC needs to run in parallel as measurement infrastructure, and why Agent Empowerment requires a 6-month build before value materialises. The dependency logic is what distinguishes a sequencing recommendation from a ranked list.

**6. "What We're Not Doing and Why" is substantive.**
The deprioritization rationale for Complaint Prediction Model is specific: it identifies the three conditions that make it viable (clean data, ML capability, team capacity) and names exactly when those conditions are likely to be met. This is more useful than "deprioritize because low score" — it gives the initiative a path forward rather than a rejection.

**7. Budget allocation guidance adds practical value.**
The budget breakdown by initiative, including a 25% reserve and the explicit rationale for holding it, is the kind of practical deliverable that makes a prioritization output usable rather than just directional. Noting that CRM replacements "almost always have cost overruns" is honest and defensible.

**8. Prompt 2 (intake response) is well-handled.**
The skill resisted the vague prompt and structured five specific inputs, each with an explanation of why it matters. The distinction between "strategic priorities" (2–3 clear things, not a list of values) and "success definition" (specific metrics, not "improved NPS") is a useful clarifying discipline that will improve the quality of inputs the requester provides.

---

## What the Skill Missed or Did Poorly

**1. The portfolio 2×2 is presented as a text diagram but is hard to read.**
The skill definition requires a "2×2 text diagram." The output uses a text-based spatial layout that works on paper but is difficult to parse at a glance — the axes aren't clearly labeled at the quadrant level, and some initiatives appear in ambiguous positions (VoC Program is labeled "quick win / capability builder" simultaneously). For a deliverable intended for executive audiences, the 2×2 should be cleaner: four clearly labeled quadrants, each initiative in exactly one quadrant with a one-line rationale. Dual-quadrant placement (VoC) is a real analytical problem that should be surfaced explicitly rather than finessed with a compound label.

**2. The scoring criteria weights are not calibrated to the stated strategic context.**
The default weights (Strategic Alignment 25%, Customer Impact 35%, Feasibility 25%, Time-to-Value 15%) are reasonable defaults but were not adjusted for the specific context. Strategic Priority 1 is "grow premium segment" — a growth objective. In a growth context, Strategic Alignment arguably deserves more weight than Customer Impact (which is broader). The skill should have proposed an adjustment or at minimum flagged: "Given that growing the premium segment is your #1 priority, you may want to increase Strategic Alignment weighting and reduce Feasibility weighting slightly. Want me to re-run with adjusted weights?"

**3. VoC Program scoring is inconsistent with its role in the case.**
VoC Program scores 3.25 composite, placing it 5th of 7. But the sequencing recommendation correctly treats it as essential infrastructure that must run from Month 1. There's a mismatch between the prioritization score and the sequencing recommendation. The skill should have either: (a) explained why a lower-scoring initiative is nonetheless recommended to run immediately (and why that doesn't contradict the scoring model), or (b) adjusted the score to reflect that VoC is a dependency for measuring the success of the entire portfolio — which is a different kind of strategic alignment than a direct customer-facing initiative.

**4. The "something to show in 6 months" constraint is partially addressed.**
The constraint is named, and Real-time Status Tracker is correctly identified as the 6-month deliverable. But the skill doesn't explicitly test every initiative against the 6-month criterion and state which ones fail it. The Time-to-Value scores partially encode this (1 = very slow), but the recommendation doesn't say explicitly: "Of the 7 initiatives, only 2 produce demonstrable results within 6 months — Status Tracker and VoC Program." This explicit statement would be more useful for the executive audience than inferring it from the scores.

**5. Team capacity is modeled as a binary constraint but not as a sequencing constraint.**
The 12-person team constraint is acknowledged, but the budget allocation guidance assigns people to initiatives without acknowledging that some team members are generalists and some are specialists. Agent Empowerment likely requires change management capability; Complaint Prediction requires data science; Digital Onboarding requires product/engineering. A 12-person team may not have all three specialisms. The skill should flag: "Team composition matters as much as headcount — does your 12-person team include [data science / change management / product engineering]? The feasibility scores assume yes; if not, some scores should drop."

**6. No explicit "what if the CRM is delayed" scenario.**
The sequencing recommendation correctly identifies Digital Onboarding as CRM-dependent. But it doesn't address what happens to the portfolio if CRM is delayed (which is the modal outcome for large CRM replacements). A single sentence acknowledging this risk and naming the contingency would strengthen the recommendation: "If CRM delays beyond Month 12, begin Digital Onboarding design work in Month 9 but hold build until stability is confirmed — don't compress the build timeline to absorb a CRM delay."

**7. The initiative descriptions were taken at face value for scoring, except for the two clarifying questions.**
"Agent empowerment program (training + authority to resolve)" is described in the prompt — but whether it includes tooling (technology) or is purely a training and policy change is unstated, and this significantly affects feasibility and cost. A system-integrated empowerment program costs 3× a training-and-policy change. The skill should have asked about this, or at minimum surfaced the assumption explicitly in the score rationale.

---

## Specific Weaknesses to Fix in the Skill Definition

1. **Add an instruction to adjust scoring weights for context.** The default weights are good starting points, but the skill should explicitly consider: "Given the stated strategic priorities, are these weights appropriate? In a cost-reduction context, feasibility should weight higher. In a growth context, strategic alignment should weight higher." This is a 2-sentence addition that prevents mechanical application of defaults.

2. **Add a rule for handling "enabling" vs. "delivering" initiatives.** VoC programs, data foundations, and change management programs are enabling initiatives — they produce value indirectly, by making other initiatives work. The current scoring model treats all initiatives as if they directly deliver customer value, which systematically undervalues enabling initiatives. The skill should have a handling rule: "If this initiative's primary value is enabling other initiatives to succeed, score Customer Impact as the indirect impact it unlocks — not its direct impact."

3. **Add a mandatory "6-month test" output.** A standalone sentence: "Of the [N] initiatives, the following can produce demonstrable results within 6 months: [list]." This directly answers the time-bound constraint every leadership team has, without requiring them to infer it from Time-to-Value scores.

4. **Add a team composition check to Feasibility scoring.** Before scoring, the skill should ask (or note as an assumption): "Feasibility scores assume your team has the following capability types: [X, Y, Z]. If any are missing, the feasibility scores for those initiatives should drop by 1–2 points."

5. **Add a sequencing assumption about CRM/dependency risks.** The skill correctly identifies initiative dependencies but should have a standard caveat for large-system dependencies: "When a key initiative depends on a large technology program (like a CRM replacement), the sequencing recommendation assumes that program stays on schedule. Name your contingency if it doesn't."
