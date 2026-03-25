# Grading Notes — eval-4 (scan-blockers with skill)

**Skill:** scan-blockers
**Date evaluated:** 2026-03-23
**Prompts:** Government digital transformation (rich input) + Intake question (sparse input)

---

## 1. What the Skill Did Well

**Specificity of blocker descriptions**
The skill consistently produced specific, contextual descriptions rather than generic labels. "Three separate CRM systems with no integration capability mean citizen identity, history, and case status cannot be unified" is meaningfully different from "legacy systems." This is the core quality gate the skill definition is designed to enforce, and it held up.

**Taxonomy coverage**
The skill worked systematically through the taxonomy and surfaced blockers across six categories from only five interview quotes. It didn't pad the list with speculative entries — each blocker had a traceable link back to something in the input.

**Leverage logic in Where to Start**
The three leverage point blockers were well-chosen and the rationale was coherent. Selecting the rhetoric-action gap as the root permission structure — rather than the more obvious technology blocker — showed genuine analytical judgment. The sequencing logic (culture unlocks technology and process) was sound.

**Landmines section**
The job security landmine was a strong catch. It identified the mechanism by which this blocker operates silently (frontline staff as channel routers) rather than just naming it as a concern. The electoral timeline landmine correctly identified the distinction between political targets and program capability targets — a real and common failure mode in government digital programs.

**Early warning signals**
The early warning signals in the Landmines section were concrete and actionable, not vague ("watch for signs of resistance"). The instruction to "track the ratio of digital channel starts to digital channel completions from day one" is something a program manager can actually act on.

**Data Gaps section**
Six well-differentiated gaps were identified. The note on union and IR landscape was a genuinely insightful addition given the staff job security concern in the input. The whole-of-government infrastructure gap is highly relevant to state government programs and often missed.

**Check-in step (Step 2.5)**
The skill correctly included the check-in before proceeding, flagged the blocker count, and asked specific probing questions (citizen digital literacy, accessibility) that went beyond the surface of the inputs. Good practice demonstrated.

**Prompt 2 — Intake quality**
The intake response for the sparse prompt was excellent. The table of materials with "why it matters" explanations does something most intake flows don't — it tells the user what value each piece of input will unlock, which makes it much more likely they'll provide useful material. The question set was structured without being interrogative. The preview of the output format at the end creates appropriate expectation.

---

## 2. What It Missed or Could Improve

**No explicit severity/addressability justification in the table**
The blocker table assigns severity and addressability ratings but does not explain them. For a senior stakeholder reviewing the output, "High / Structural" on three separate blockers reads as undifferentiated — they all look the same. A single-sentence rationale column, or at minimum a footnote explaining what pushes something to High vs. Med, would improve usability.

**Interconnection between blockers not surfaced**
The skill identified blockers well but did not explicitly map how they reinforce each other. For example: the rhetoric-action gap enables paper approvals, which de-prioritises the CRM integration problem, which makes the 60% target impossible to achieve honestly, which creates the conditions for the electoral gaming landmine. This systems-level narrative exists implicitly in the Where to Start section but is not made explicit. A brief "blockers that compound each other" callout would be high value for a program director.

**The "2 years of minimal progress" signal was underused**
The prompt explicitly states the program has been running for two years with no results. This is diagnostic evidence of something — either the blockers were known and not addressed, the wrong interventions were tried, or the program was never resourced to address structural issues. The skill didn't ask about or comment on this pattern specifically. A strong consultant would have named it as a systemic signal, not just background context.

**Change fatigue blocker was under-weighted**
The skill identified change fatigue as Medium severity, which may be accurate, but the description was thin compared to other blockers. In a government department that has been running a two-year transformation with minimal progress, change fatigue is likely more active and more specific than described. It deserved a richer description and possibly higher severity.

**Prompt 2 — No acknowledgment of what CAN be inferred already**
The intake response for Prompt 2 was thorough but missed an opportunity to demonstrate analytical credibility upfront. Even with the two targets provided (40% complaint reduction, 15 days to 3 days resolution), a skilled consultant would note: "A 5x reduction in resolution time typically points to either a system or data access bottleneck, a high handoff count, or an escalation backlog — here are the hypotheses I'll be testing." This would signal diagnostic depth and build user trust before they've committed to providing materials.

**No quantification framing on severity**
"High" is a relative rating with no anchoring. For a government program with a fixed electoral window, it would be useful to know whether "High / Structural" means "this will take 18+ months and therefore cannot be solved within the program timeline." The skill could add a note distinguishing between blockers that are high severity and solvable within the program window vs. high severity and outside the window — the latter require political management, not technical resolution.

---

## 3. Specific Weaknesses to Fix

**Fix 1: Add a "blocker system" callout**
After the blocker table (or in the Where to Start section), add a short paragraph identifying 2-3 blocker pairs that compound each other. This turns a list into a systems map and is significantly more useful for program planning. The skill definition doesn't currently require this, and it should.

**Fix 2: Require severity justification in the table**
Add a "Severity rationale" mini-column or require a single sentence explaining why each High-severity blocker is High rather than Med. This prevents the table from becoming a flat list of red flags and forces the skill to show its analytical work.

**Fix 3: Require acknowledgment of program history signal**
If the prompt includes information that a program has been running for >12 months with minimal progress, the skill should explicitly name this as a diagnostic signal and ask: "What has been tried?" and "What stopped it?" This is one of the most important questions a consultant asks and it's currently absent from the Step 0 intake.

**Fix 4: Strengthen the sparse-input response with upfront hypotheses**
When the user provides clear targets (e.g., resolution time) but no context, the intake response should include 2-3 hypotheses about what typically drives that class of problem — before asking for materials. This demonstrates expertise, helps the user provide more targeted input, and makes the intake feel like a consultation rather than a questionnaire.

**Fix 5: Add a program-window filter to the Where to Start section**
The Where to Start section currently recommends based on leverage. It should also filter by addressability relative to the program's stated timeline. A Structural blocker with an 18-month resolution path needs different handling in a program with a 12-month election window than one with open-ended duration. The skill should flag this explicitly when the timeline is known.
