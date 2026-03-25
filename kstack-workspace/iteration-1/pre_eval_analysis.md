# Pre-Eval Skill Analysis — Structural Weaknesses

Identified from careful reading of all 10 SKILL.md files before eval runs.

---

## Cross-Skill Issues (affect all 10 skills)

### 1. Descriptions not "pushy" enough
Per skill-creator guidelines, descriptions should be "pushy" to combat undertriggering. All current descriptions are accurate but passive. They describe what the skill does but don't aggressively name contexts when it should trigger even if not explicitly requested.

### 2. No graceful "no-documents" path documented
Several skills (trend-scan, biz-context, persona-build) rely on documents but users often won't have them. The intake asks for docs but doesn't explicitly state what happens if none exist, leaving Claude to improvise. Should state: "If no documents provided, conduct a structured verbal intake using these questions..."

### 3. Missing chain context in descriptions
Skills downstream in the workflow don't tell Claude to look for outputs from upstream skills in context. E.g., journey-map doesn't say "if a persona-build output is already in context, use it automatically."

### 4. No output quality floor stated
No skill specifies minimum acceptable specificity. When a user gives little context, Claude may produce generic outputs that don't meet the skill's quality bar.

---

## Skill-Specific Issues

### trend-scan
- Step 2.5 check-in asks about missing forces but doesn't ask if the Relevance scores need calibration from the user's internal knowledge
- "Tech Waves" dimension is listed separately from PESTLE but not given the same structure (2-4 signals format)
- Output Section 4 "What This Means for the CX Agenda" lacks a format spec (how long? what structure?)
- Missing: explicit instruction to refuse to write "customers will expect more" style implications

### biz-context
- Step 1.5 data gap check asks about thin data but doesn't specify what threshold triggers the check — every domain with limited evidence, or only critical gaps?
- Missing: instruction about what to do when no documents provided at all (verbal intake flow)
- Key Tensions section has a good bad-example but could use more guidance on what "specific" looks like
- The "So What" section could be stronger — it should explicitly connect to the decision the user named in Step 0

### scan-blockers
- Step 1 says "read blocker-taxonomy.md" but gives no fallback if the file can't be found
- The taxonomy categories listed in Step 3 are only 8 but the actual file likely has more nuance — the SKILL.md should not duplicate the taxonomy, just reference it
- "Where to Start" section should specify: leverage = addresses a blocker that is upstream of multiple other blockers, not just high severity
- Missing: explicit guidance on what to do when inputs are very thin — minimum viable scan approach

### persona-build
- Step 6.5 mandatory evidence review asks user to confirm but doesn't specify what kinds of "wrong" things to watch for (the prompt is weak — "anything I've missed?" is too open)
- The ASSUMED tag should be more explicitly handled — if >50% of claims are ASSUMED, skill should flag this as a data quality issue and recommend research before using the persona for decisions
- Missing: instruction that the persona card format should be literal (with the template headers shown)
- Designer's Note guidance is thin — "3-5 sentences" but no guidance on what the note should specifically address

### journey-map
- Step 1 says "load touchpoint-taxonomy.md" but no fallback if unavailable
- Emotion score guidance says "default to what context suggests, not 3" but doesn't give enough examples of what scores 1-2 look like vs. 4-5 — this leads to score inflation
- The journey map table has 10 columns — too wide to display well. Should specify that splitting by stage is essential.
- Step 6 "Design Provocations" is underspecified — "uncomfortable questions" could be anything. Should say: questions that challenge assumptions the design team will arrive with.

### service-map
- Step 0.5 mandatory system inventory is excellent, but doesn't say what happens after the user provides the list — does the skill do anything with it before mapping?
- Five layers don't have consistent guidance on specificity — Layer 3 (Backstage) needs the same "be specific" instruction that the blocker scan gives for description
- Failure point severity guidance (High/Med/Low) is good but missing: instruction not to understate severity to protect internal stakeholders (this is explicit in the full skill, good)
- Top 3 Systemic Opportunities format is well-specified but "Order by customer impact, not ease of implementation" is important and should be more prominent

### synthesize
- Affinity clustering: "5-8 named themes" — the guidance on memorable names is good but missing: instruction to name themes from the customer/strategic truth, not from the data source (e.g., NOT "Journey Map Findings" but "The Moment of Need is the Moment of Abandonment")
- Tension mapping: "Bad tensions" examples are good but "too generic" guidance needs a stronger test — the bad examples listed are indeed generic, but practitioners need a heuristic: if both sides of the tension can apply to ANY company in any industry, it's too generic
- HMW ranking by "strategic leverage" isn't defined well enough — what makes something High vs. Med leverage?
- Missing: explicit instruction that the synthesis should surface insights NOT already stated in the individual outputs — synthesis = new knowledge from combination, not summary

### workshop-prep
- Step 3 "Design the Arc" has good principles but no guidance on how to adapt for time — a 2-hour session arc is very different from a full-day arc
- Facilitation notes column in the runsheet table is underspecified — the guidance at Step 4 is good but the template column header alone won't generate the right depth
- Pre-read brief: "Max 400 words" is good but no guidance on tone calibration for different audiences (exec vs. practitioners vs. mixed)
- Missing: guidance on what happens when synthesis outputs aren't available — how to frame the problem for workshop anyway

### biz-case
- Step 4.5 mandatory numbers check is excellent — asks for what's available before building ROI. But the template for this check-in is weak ("here's what I have...") — it needs a more structured format to be useful
- The executive summary comes AFTER all sections in the instructions ("write this first, after completing all sections") — this is counterintuitive and confusing. Should be clearer: write the full case first, THEN write the executive summary and put it at the top.
- Risk register: "Do not list generic risks" is stated but no examples of what generic vs. specific looks like for risks (unlike tensions where there are good examples)
- Assumptions Register: "builds credibility" rationale is good but the register format could be more structured — currently just "assumption + basis + what must be true"

### prioritize
- Step 1 "Clarify vague initiatives" is well-designed (1-2 questions max, not a full intake) — this is the best intake efficiency instruction across all skills
- Score descriptions (1-5 for each dimension) are good but the composite formula should be stated more visually — practitioners will want to check the math
- Portfolio 2x2 diagram has an error in the text diagram: "STRATEGIC BETS" and "DEPRIORITIZE" are on the wrong sides relative to the axes as labeled. LOW FEASIBILITY should be on the left, HIGH FEASIBILITY on the right.
- Step 5 "explicitly not doing" is excellent — the three reasons given are exactly right. But the format (Initiative — Reason — Condition) could have an example to anchor the quality

---

## Priority Improvements (by impact)

1. **All skills**: Make descriptions pushier
2. **trend-scan, persona-build, journey-map, service-map**: Add fallback for when resource files can't be loaded
3. **biz-context, persona-build**: Add structured no-documents verbal intake path
4. **synthesize**: Add explicit instruction that synthesis = new knowledge, not summary
5. **prioritize**: Fix the 2x2 diagram axis error
6. **workshop-prep**: Add time-calibration guidance for the arc design
7. **All skills**: Strengthen the mandatory check-in templates to be more structured
