# Grading Notes: biz-case
## EVAL-16 and EVAL-17

---

## What the Skill Did Well

**1. Recommendation goes at the top — correctly.**
The skill definition states "Recommendation goes at the top. Evidence after." The response delivers an explicit, actionable recommendation in the first line of the executive summary, not buried after six sections of context. This is the single most important structural discipline for an executive-facing business case and the skill executes it correctly.

**2. DATA / INFERRED / ASSUMPTION tagging is thorough and honest.**
Every significant number is tagged. The tagging is specific — it doesn't just say "this is an assumption" in a generic disclaimer but names what the assumption is, what it drives, and how to validate it. The Numbers Check section (4.5) produces a clear distinction between what was provided vs. what was estimated vs. what was assumed. This is the most important epistemic discipline in the skill and it's executed at a high standard.

**3. The value drivers are calibrated to the specific initiative.**
The skill uses the Value Driver Library correctly: it selects the applicable drivers (FCR, AHT/productivity, deflection, attrition, NPS) and rejects drivers that don't apply (conversion rate improvement, upsell, etc.). The mechanism logic for each driver is connected to the specific data points provided (e.g., using the 34% repeat contact rate directly in the FCR calculation). This avoids the common biz-case failure of applying generic impact ranges without grounding them in the client's actual numbers.

**4. The ROI logic is internally consistent.**
Investment breakdown, value estimates, and payback calculation are consistent with each other. The 3-year net value figure is correctly calculated. The skill correctly identifies the most assumption-sensitive driver (NPS/retention linkage) and treats it with appropriate conservatism.

**5. The Risk Register is specific, not generic.**
Each risk names the specific mechanism, not just a category ("adoption risk"). Risk 1 (AHT is not tools/process-driven) and Risk 3 (root cause is product complexity) are particularly well-formed — they identify exactly when the case breaks and what to do about it before committing. Risk 4 (CFO withdraws support during the cost-before-value period) is a real program risk that is often missed in business cases.

**6. The Assumptions Register is a genuinely useful deliverable.**
It enables the CFO's team to interrogate the case systematically. Confidence levels are differentiated, and each assumption has a "how to validate" column that makes it actionable. Most business cases bury assumptions in footnotes — this surfaces them as a primary output.

**7. Prompt 2 (intake response) was correctly handled.**
The skill resisted vague input and asked targeted questions that are genuinely necessary — not a laundry list, but six specific inputs with an explanation of why each one matters. The framing "I'll flag what I'm estimating vs. what's known" sets the right expectation with the requester.

**8. The Numbers Check (Step 4.5) is explicitly surfaced, not skipped.**
The skill definition requires a mandatory numbers check before building the ROI model. This was executed and produced a specific request for three additional data points before CFO presentation. This is the right behaviour — it prevents the common failure of presenting a case with unstated assumptions that the CFO then demolishes in the room.

---

## What the Skill Missed or Did Poorly

**1. The Problem Statement's "why now" is weak.**
Section 1 identifies "why now" as the negative compounding spiral (attrition → poor resolution → higher repeat contacts → more attrition), which is real. But it misses the most powerful "why now" argument available from the data: an NPS of -18 means the contact centre is a net brand-destruction engine. Every dollar spent managing this creates negative value beyond the direct call cost. The "why now" should connect to a growth or competitive urgency — if the organisation is trying to grow the premium segment or enter a new market, a -18 contact centre NPS is an active business risk, not just an operational inefficiency. This argument is implied but not stated.

**2. The Solution Hypothesis doesn't address the "why this vs. alternatives" requirement adequately.**
The skill definition requires: "why this vs. alternatives (3–5 sentences)." The response names three alternatives (technology-only, training-alone, sequenced) but doesn't engage seriously with the most likely alternative a CFO would propose: "Can we just replace the IVR and automate the tier-1 contacts?" This is the most common CFO objection to contact centre transformation — "why are we redesigning processes when we can just automate?" — and the case should pre-empt it directly.

**3. The Target Segment is underdeveloped.**
Section 3 identifies "all customers who contact the contact centre" plus two sub-segments. This is accurate but thin. A well-formed target segment would distinguish between: customers whose contact was avoidable (deflection opportunity), customers whose issue was resolvable in first contact (FCR opportunity), and customers whose repeat contact is driven by process failure vs. product complexity. This segmentation matters for the ROI logic — you can only claim value on the addressable portion of contacts, not all 1.2M.

**4. The Implementation Roadmap has a dependency gap.**
The roadmap lists milestones but doesn't explicitly connect the "root-cause analysis in M1–2" to the "programme investment decision." Best practice for a transformation of this scale is: Phase 1 is a "diagnostic and design" phase with a committed investment of $X, followed by a gate review before committing to full build investment. The current roadmap implies full $2.5M commitment upfront, but the skill's own risk register identifies that AHT and repeat contact root causes might not be what we think. A phased commitment structure would be more defensible.

**5. The cost-per-call assumption is used without interrogation.**
The case uses $8.40/call throughout. This is a loaded cost figure (presumably including FTE, infrastructure, and overhead). The ROI logic treats productivity savings as equivalent to direct cost reduction — but if 70% of the $8.40 is fixed overhead (facilities, management, IT), then a 30% AHT reduction doesn't produce $2.52M in savings unless headcount can be reduced or reallocated. The skill correctly flags this as an assumption but should have pressed harder: the loaded cost breakdown matters for whether the value driver is cost savings vs. headcount avoidance vs. volume absorption.

**6. No mention of regulatory context.**
For a contact centre business case in financial services (implied by the mortgage application journey context in EVAL-14), a -18 NPS and 34% repeat contact rate are potential regulatory risk signals — complaints that aren't being resolved are often a precursor to regulatory scrutiny (AFCA, FCA, CFPB depending on jurisdiction). The Risk Register has a Regulatory Risk Reduction driver in the Value Driver Library that was not applied here. Even a brief acknowledgement that this program reduces regulatory exposure would strengthen the case for an Investment Committee.

**7. The One-Page Executive Summary is good but not ready to stand alone.**
The summary references six value drivers and a payback period but doesn't include a single figure for total 3-year net value. For a CFO who reads only the summary, the question "what's the net return on $2.5M" requires digging into the full case. The summary should contain one line: "3-year net value: $13.4M on $2.5M investment — a 5.4× return."

---

## Specific Weaknesses to Fix in the Skill Definition

1. **Add a "why now" forcing function to Section 1.** The current instruction ("why now" as a component) is too easy to satisfy with incremental logic. Add: "The 'why now' must connect to a competitive, growth, or regulatory urgency — not just an operational trend. What happens to the business if this problem persists for another 18 months?"

2. **Require explicit alternative comparison in Section 2.** Add: "Name the most likely alternative a CFO would propose (often: automation, offshore, incremental improvement) and explain specifically why this approach outperforms it on the value/risk tradeoff."

3. **Add a phased commitment structure option to Section 7.** When the program has high root-cause uncertainty (the first risk is always "the problem is different from what we think"), the roadmap should offer a "diagnostic gate" before full investment — not because the full program is wrong, but because it's more defensible.

4. **Add Regulatory Risk Reduction as a default consideration** for financial services context. The skill should prompt: "Is this organization operating in a regulated environment? If so, is the regulatory risk reduction driver applicable?"

5. **Add a standalone-test for the Executive Summary** — the skill should produce an executive summary that contains total investment, total 3-year net value, payback period, and recommendation in the first 150 words. Test: "Can a CFO read only the summary and know the ROI?"
