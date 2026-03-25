# Grading Notes: /service-map Skill

**Evals covered:** EVAL-10 (Prompt 1 — mortgage blueprint), EVAL-11 (Prompt 2 — insurance claims, systems unknown)
**Date:** 2026-03-23

---

## What the skill did well

### Structural faithfulness
The skill executed all five steps of the blueprint methodology without omission. Every stage received all five layers, failure points, handoff risks, and a complexity rating. The Failure Point Register, Handoff Risk Register, Complexity Summary, and three Systemic Design Opportunities were all delivered as specified.

### Failure point specificity
The skill identified granular, plausible, non-sanitised failure points — not generic observations. Examples like "CRM record creation failure creates silent drop — customer receives confirmation but application is not logged" and "Manual document indexing to CRM is error-prone and creates mismatched records" are the kind of operationally honest findings the skill definition demands. It did not soften or hedge failure severity.

### Systems layer engagement
Given a systems inventory, the skill named specific systems at each stage and traced data flows between them (e.g., portal → CRM → notifications system). The legacy credit decisioning engine was correctly identified as a systemic risk rather than just a technology inconvenience.

### Systemic Design Opportunity framing
The three opportunities used the mandated format ("Redesigning X would Y by enabling Z — currently preventing because...") and were ordered by customer impact, not implementation ease. The framing was specific enough to brief a technology or process design team. No vague strategy-speak.

### Mandatory system inventory enforcement (Prompt 2)
When the user explicitly stated they didn't know the systems involved, the skill correctly refused to proceed and asked structured system inventory questions. It explained why the systems layer is not optional without being combative. This is precisely the Step 0.5 behaviour the skill definition specifies.

### Prompt 2 added value beyond the gating question
Rather than just asking for systems and stopping, the response:
- Proposed a stage structure for the user to validate
- Explained why insurance claims make back-office systems particularly important
- Told the user what partial information would still be useful
This is the right calibration between enforcement and helpfulness.

---

## What the skill missed or could improve

### No known failure points were provided — the skill didn't flag this gap explicitly
The user in Prompt 1 did not provide known complaint patterns or failure points, which Step 0 explicitly asks for. The skill proceeded without noting this absence. A stronger response would acknowledge "you haven't shared known failure patterns — the failure points I've identified are hypothesised from structural analysis; they should be validated against your complaint and operational data." This matters because the skill definition says "if the service is structurally broken, say so" — implying the skill should distinguish between confirmed failure points and inferred ones.

### Complexity ratings lack quantitative grounding
The complexity ratings (Low/Medium/High/Very High) are correct in relative ranking but are not anchored to any quantitative data (e.g., estimated rework rates, call volumes per stage, average processing time). In a real engagement, these ratings should reference observable metrics where available. The skill has no mechanism to request this data, and the output doesn't note the absence of it.

### The Systemic Design Opportunities could be more specific about customer outcome metrics
The opportunity framing names the customer outcome ("reduce application cycle time," "give customers meaningful real-time status visibility") but doesn't connect to the specific emotion scores or NPS implications from the journey map. If a journey map had been provided, the skill should explicitly cross-reference it. Here, it was working without one — the skill didn't note this as a limitation.

### No journey map input was provided — the skill didn't ask for one
The skill definition (Step 0) explicitly asks whether a journey map output from /journey-map exists and invites the user to paste it. The skill should have asked for this before proceeding, or at minimum noted "I'm building this blueprint without a journey map — customer actions and emotion data are inferred, not confirmed. Running /journey-map first would produce a more grounded blueprint." It proceeded without raising this.

### Handoff risk severity calibration could be sharper
Several handoffs are rated "High" without differentiating between high-frequency/low-impact and low-frequency/high-impact risks. The register would be more actionable if it included a frequency dimension alongside risk level — mirroring the Failure Point Register format.

### Prompt 2 doesn't offer a provisional blueprint with explicit uncertainty markers
An alternative valid approach for Prompt 2 would be: proceed with a provisional blueprint using common insurance claims system patterns, clearly marked as "assumed — confirm against your actual systems." The current approach (hard gating) is correct per the skill spec but may frustrate users who want immediate output and intend to validate later. The skill could offer this as an option rather than a binary wait/proceed.

---

## Specific weaknesses to fix in the skill definition

1. **Add to Step 0:** Explicitly instruct the skill to note when a journey map has not been provided, and to ask for one or flag its absence as a gap that reduces blueprint accuracy.

2. **Add to Step 2 (Failure Point Register):** Distinguish between failure points confirmed by the user (from known complaint patterns) and failure points inferred from structural analysis. Add a "Confidence" column: Confirmed / Inferred / Hypothesised.

3. **Add to Step 4 (Complexity Rating):** Instruct the skill to reference any quantitative data available (call volumes, rework rates, processing times) when rating complexity, and to note when ratings are based on structural assessment only.

4. **Add to Step 0.5 (System Inventory):** Give users the option of receiving a provisional blueprint with assumed system patterns, clearly marked as unverified — alongside the standard request for system information. Remove the hard binary between "provide systems" and "no blueprint."

5. **Handoff Risk Register:** Add a "Frequency" column to mirror the Failure Point Register format, and clarify the distinction between high-probability/low-impact and low-probability/high-impact handoff risks.

---

*Grading notes generated for KStack iteration-1 evaluation*
