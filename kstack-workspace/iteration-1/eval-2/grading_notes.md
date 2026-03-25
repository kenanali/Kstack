# Grading Notes — Biz Context Skill Eval-2

---

## 1. What the Skill Did Well

**Honest, non-flattering tone maintained throughout.**
Both responses avoided the "the company is well-positioned for growth" problem the skill specifically warns against. Revenue growth was immediately interrogated as price-driven rather than celebrated. This is the most important behavioural requirement of the skill, and it held.

**Evidenced vs. inferred distinction was consistently applied.**
Both responses explicitly separated what was stated by the user from what was inferred. The "Inferred (not evidenced)" labels were applied correctly and consistently, which builds credibility and models good analytical thinking for the user.

**Data Gaps Register was substantive and actionable.**
The gaps weren't generic ("more data would help") — they were specific, paired with the analytical consequence of each gap ("cannot determine whether high-value customers are churning at higher rates than average"). This is genuinely useful for a CX Director preparing a business case.

**Key Tensions were specific and evidenced.**
The tensions in both responses cited specific metrics in conflict with each other rather than abstract platitudes. Tension 1 in Prompt 2 ("Price increases applied to customers who are becoming less satisfied and more likely to leave") is a good example: it names the conflict precisely and doesn't soften it.

**Step 0 intake in Prompt 1 was well-structured.**
The intake questions were domain-organised, specific, and explained why each question mattered. The note to the user explaining that data gaps would themselves strengthen the business case was a useful reframe that the skill instruction doesn't explicitly require but the consultant persona naturally generates.

**Prompt 2 surfaced the operational failure loop.**
The diagnosis that cost-to-serve rising + NPS declining + churn rising is a "failure demand loop" — rather than treating these as three separate problems — is the kind of synthesis that distinguishes a consultant mode from a data-summary mode. The strategic "So What" in Prompt 2 was notably stronger for this reason.

**Employee NPS was treated as a first-class signal.**
Rather than noting Employee NPS of -12 as a culture footnote, the response correctly identified it as an execution risk for the transformation itself. This is an insight the skill instruction supports but doesn't spell out.

---

## 2. What It Missed or Could Improve

**Prompt 1: The skill proceeded to full diagnostic without explicitly waiting for intake answers.**
The SKILL.md instruction says "Read all provided materials thoroughly before proceeding" and Step 1.5 says "Wait for response." In a real conversation, the skill should ask intake questions and pause — not ask questions and then answer them itself. The eval format forced a workaround (the "For the purposes of this evaluation..." note), but this reveals a structural weakness: the skill doesn't have clear handling instructions for the "no documents, verbal only" scenario. It should.

**Health ratings weren't surfaced in a scannable summary.**
The five domain ratings (AT RISK, CRITICAL, UNKNOWN, etc.) are embedded in each domain section but there's no at-a-glance dashboard at the top of the output. A CX Director presenting this to a CFO would want a one-line summary table before the detail. The skill instruction describes the format but doesn't require a summary header — it should.

**"UNKNOWN" as a health rating is underspecified.**
In Prompt 1, Operational Health and Org Capability are rated "UNKNOWN (Insufficient Data)." This is honest, but it doesn't give the reader a directional signal. The skill could benefit from a fifth rating option like "Unassessed — Directionally At Risk" for cases where the absence of data is itself a warning sign. The skill instruction only offers Strong / Adequate / At Risk / Critical.

**Section 3 "So What" in Prompt 1 was slightly generic in its final sentence.**
The success metrics named (premium churn rate, NPS recovery to +20, cost-to-serve reduction) were appropriate but not quantified tightly enough to serve a business case. The skill instruction says "what does success look like" but doesn't prompt for time-bound targets. This led to vague language ("within 24 months") without clear numeric anchors beyond what the user had already provided.

**The skill doesn't ask about the competitive landscape unprompted.**
In Prompt 1, the user mentioned an MVNO competitor but the skill didn't probe on it in the intake (the question about the MVNO was buried in the market position section). For CX transformation, competitive intelligence is often the most persuasive element of a business case. The skill should have a dedicated intake question: "Who are your main competitors, and what do customers say about their experience relative to yours?"

**No cross-domain synthesis summary was produced.**
The five domains are diagnosed separately, which is correct — but there's no explicit "here is how these domains connect" paragraph before the tensions section. In Prompt 2, the failure loop insight appeared in the "So What" rather than as a bridging section, which means a skim reader would miss it.

**The step numbering in the output doesn't match the SKILL.md structure.**
The skill produces Sections 1-4 correctly, but the thinking process (Steps 0, 1, 1.5, 2, 3) isn't visible to the reader. This is fine in most cases, but a CX Director using this as an artifact to share with stakeholders would benefit from the intake questions and data gap check being clearly labeled as part of the process — not just embedded in the text.

---

## 3. Specific Weaknesses to Fix in SKILL.md

**Fix 1: Add explicit handling for "no documents" scenario.**
Currently the skill says "Read all provided materials thoroughly before proceeding" — but it has no instruction for what to do when no materials exist. Add a specific branch:

> "If no documents are provided and the user is working from memory or summary data: proceed with structured intake questions, then conduct the diagnostic based on verbal input. Label all evidence as 'User-stated' rather than document-cited. Note at the top of the output that the diagnostic is based on undocumented information and that conclusions are provisional pending data review."

**Fix 2: Require a diagnostic summary table at the top of Section 1.**
Add to the output format instructions:

> "Begin Section 1 with a five-row summary table: | Domain | Health Rating | One-Line Summary |. Then provide the full domain detail below."

This gives readers a scannable entry point and makes the output more presentation-ready.

**Fix 3: Add a fifth health rating for data-absent domains.**
Replace the four ratings with five:

> Strong / Adequate / At Risk / Critical / **Unassessed** (insufficient data — treat as potential risk)

Add a note that "Unassessed" domains should be flagged as priority data requests, not treated as neutral.

**Fix 4: Add a competitive landscape intake question.**
In Step 0, add:

> "Who are your main competitors? Are any of them growing faster than you or winning your customers? What do you believe customers experience with them vs. with you?"

This is especially important for CX transformation contexts where the competitive threat is often the primary business case driver.

**Fix 5: Add a cross-domain synthesis step between Domain scan and Key Tensions.**
Add a brief instruction after Step 1.5:

> "Before writing tensions, note any patterns that run across multiple domains — e.g., if NPS, churn, and employee engagement are all deteriorating simultaneously, name that as a systemic pattern rather than treating each in isolation. Cross-domain patterns are usually the highest-leverage insight in the diagnostic."

**Fix 6: Tighten the "success looks like" prompt in Step 3.**
Change the current instruction from:

> "What does success look like — what business outcomes would CX improvement drive?"

To:

> "What does success look like — expressed as specific, measurable business outcomes (e.g., churn rate, NPS, cost-to-serve) with a realistic timeframe (12-24 months). Anchor these to the metrics already presented in the diagnostic where possible."

This prevents the "So What" from being vague and ensures it generates material that can be directly used in a business case.

**Fix 7: Clarify the waiting behaviour at Step 0 and Step 1.5.**
The skill instruction says "Wait for response" at Step 1.5 but doesn't say this at Step 0. Make the pause behaviour explicit at both steps:

> "Do not proceed to the next step until the user has responded (or explicitly said they have nothing more to add)."

This prevents the skill from front-loading all analysis in cases where the user might have had more to share.
