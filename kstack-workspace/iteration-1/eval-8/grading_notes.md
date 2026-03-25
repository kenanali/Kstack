# Grading Notes — journey-map skill (EVAL-8)

Evaluated against: response_prompt1.md (persona-supplied input) and response_prompt2.md (no-persona input)

---

## What the Skill Did Well

### Prompt 1 (persona + journey context supplied)
- **Emotion scores were specific and justified throughout.** The skill did not default to 3 (neutral) — scores ranged from 1 to 5 with clear reasoning at each. The pattern of 1s during Stage 4 (silence) and Stage 3 (additional document request) correctly captures the emotional bottom of the journey. The 5 at formal approval was justified specifically as "relief from sustained anxiety" rather than just joy — which is a sharper emotional read.
- **Customer thoughts were first-person, unfiltered, and specific.** Across the table, the Customer Thought column contained genuine internal monologue: "None of these options say 'check on my application'" and "But I already submitted everything. Why didn't they tell me this at the start? Am I failing?" These are not sanitized summaries — they capture what a person actually thinks in those moments.
- **The absent touchpoint was mapped.** Stage 4 included a row for the *absence* of communication — "No proactive communication (absence of touchpoint)" with Emotion Score 1. This is excellent practice: a journey map that only maps what exists will miss the experience gaps that are often most damaging. The skill correctly treated silence as a touchpoint.
- **Moments of Truth were marked generously and correctly.** The majority of high-stakes touchpoints were marked Y, including the income verification document discovery (which is the most important failure point), the additional document request, and the decline notification. The skill did not under-mark MoT to keep the list tidy.
- **The Emotional Arc narrative was analytically strong.** The most valuable sentence was: "the emotional quality of that elation is more *relief from sustained anxiety* than pride in a seamless experience — which reveals how much cumulative stress the journey has inflicted." This is the kind of interpretive layer that makes a journey map useful for executive communication, not just service design.
- **Design Provocations were genuinely uncomfortable.** All three provocations are the kind that stakeholders want to avoid answering — which is exactly the standard. The third ("Are we designing for completion or for delight?") is particularly sharp.
- **The decline path was mapped.** The skill included an alternative row for the decline outcome in Stage 6, not just the happy path. This is a significant quality signal — most AI-generated journey maps only map the approval path.
- **Opportunities were framed correctly as improvement → outcome → mechanism.** The five opportunity areas followed the required format precisely, and the mechanisms were specific (e.g., "the mechanism is transparency, not process change" for the status tracker opportunity).

### Prompt 2 (no persona supplied)
- **The refusal was grounded in the journey map's own methodology.** The skill explained exactly why the Customer Thought and Emotion Score columns require a persona to be non-generic — it didn't just say "you need a persona" but articulated the specific parts of the output that would fail without one.
- **The intake questions were well-targeted.** The four rapid questions in Option B (complaint type, emotional peak, desired outcome) are exactly the right questions to ask — they're the minimum needed to anchor the emotion scores and internal monologue.
- **The "process diagram vs. journey map" framing was clear and persuasive.** "A journey map without a persona is a process diagram wearing a journey map's clothing" is a crisp, memorable explanation for why the skip isn't possible. This framing will work with non-expert stakeholders.

---

## What the Skill Missed or Could Have Done Better

### Prompt 1

1. **Step 2.5 mandatory check-in was noted but not performed.** Like the persona-build skill, the journey-map skipped the mandatory stage confirmation step and narrated around it ("In a live session, stages would be confirmed…"). This is the same structural weakness — mandatory interactive gates are bypassed in batch output mode without a protocol for handling them. The output is good, but this is a reliability gap in the skill's process compliance.

2. **The touchpoint taxonomy was not explicitly cited or attributed.** The skill was instructed to use the touchpoint-taxonomy.md vocabulary. The output used accurate taxonomy terms (IVR, Queue / hold experience, In-Person — Branch — Staff consultation, Self-Service Portal — Claims or application portal) but did not note that it was drawing from the taxonomy. This matters for auditability — the user should be able to verify that the channel vocabulary is consistent and sourced.

3. **The Comparison & Aggregator touchpoint in Stage 1 is slightly miscast.** The skill includes a row for "Comparison/aggregator site" but the persona context states Sarah has just received pre-approval and is comparing lenders. At this point, she is more likely to be on lender websites and reading Google Reviews than on a formal aggregator (which is more common earlier in the shopping process). The taxonomy has Review Platforms and lender website touchpoints that would be more accurate to her actual behaviour at this stage.

4. **Stage 7 (Completing Formalities) is thin.** The two touchpoints in Stage 7 (contract documents and settlement confirmation) are correct but could go deeper. The document signing stage often involves a solicitor, conveyancer, or third-party interaction that is not captured. The journey ends at settlement confirmation, but Sarah's emotional state at this point is not explored in the arc (the arc effectively ends at approval). The post-resolution experience matters for NPS and referral.

5. **The branch consultation touchpoint in Stage 3 is placed correctly but the Opportunity is too broad.** "Train branch staff with first-home buyer scripts" is a valid but generic recommendation. The more specific opportunity — given that judgment anxiety is evidenced — is to create a visible artefact that *normalises* first-time-buyer questions (e.g., a physical "Common Questions" guide on the desk that signals "these questions are expected"). The mechanism matters for why the improvement will work.

6. **No service blueprint layer is surfaced.** Journey maps for complex, multi-channel journeys like mortgage applications benefit from noting the backstage process alongside the front-stage experience — particularly at the points where front-stage failure is caused by backstage constraint. For example, the reason the status dashboard shows only "Application in Progress" is probably an internal system limitation, not a design choice. Noting the backstage constraint makes the opportunity more actionable. The skill framework doesn't require a full blueprint (that's /service-map's job), but a brief "backstage note" at key failure points would increase the map's actionability.

### Prompt 2

7. **The response didn't name the most common complaint customer archetype even briefly.** When offering Option A (provisional persona, assumption-only), the skill described it abstractly but didn't give the user enough of a preview to decide whether it would be useful. A brief sketch — "this would likely be based on a long-tenured customer who has experienced a service failure and feels disappointed rather than just transactionally inconvenienced" — would help the user make a more informed choice.

8. **The complaint journey's known emotional arc wasn't referenced.** The skill could have noted: "The emotional arc of a complaint journey is consistently one of the most negative in any service context — customers arrive already unhappy, and every additional hurdle compounds their distress. We know the arc even before we have the persona; what we need the persona for is to know *why* specific touchpoints hit as hard as they do." This framing would make the persona requirement feel less like a bureaucratic gate and more like a practical necessity.

---

## Specific Weaknesses to Fix in SKILL.md

### Fix 1: Strengthen the Step 2.5 mandatory check-in instruction
Same issue as persona-build. The "stop and ask" language is too soft. Add:

> "This is a mandatory pause. Do not proceed to Step 3 without stage confirmation. In evaluation or batch contexts, complete the check-in as a written exchange: state the proposed stages, describe what each covers, and explicitly name what would change if a stage were split, merged, or added. Do not narrate around this step."

### Fix 2: Require explicit taxonomy citation in the output
In Step 1 (Load Channel Vocabulary), add:

> "When naming channels in the journey map table, use the exact vocabulary from touchpoint-taxonomy.md. At the start of the Journey Map Table section, include a brief note: 'Channel vocabulary sourced from touchpoint-taxonomy.md.' This ensures consistency and auditability across journey maps."

### Fix 3: Add guidance on the accuracy of Stage 1 touchpoints
Add to Step 2 (Define Journey Stages):

> "For the first stage, be precise about what channel and touchpoint the customer is actually using at the *exact moment* described — not the generic category of activity. 'Comparing lenders' may involve review sites, aggregators, lender websites, or word of mouth depending on where the customer is in their consideration arc. Check the persona context for timing cues."

### Fix 4: Add a backstage constraint note option to the table
Optionally add a "Backstage Constraint" column (or a footnote field) for touchpoints where the customer-facing failure is caused by an internal system or process limitation. Add a note in Step 3:

> "For key pain points: where is the customer-facing failure caused by a backstage constraint (system, process, policy, org structure)? Note this briefly in the Opportunity field or as a separate annotation. Opportunities that don't account for backstage constraints are hard to action."

### Fix 5: Require the decline/unhappy path to be mapped
Add to Step 3:

> "If the journey has a failure outcome (decline, unresolved complaint, failed transaction), map at least the key touchpoints on the failure path. A journey map that only covers the happy path will miss the highest-intensity emotional moments and the highest-leverage recovery opportunities."

### Fix 6: Strengthen the no-persona refusal with an emotional arc preview
In the skill's handling of the no-persona case, add:

> "You can note the general emotional shape of this journey type (e.g., 'complaint journeys consistently start with negative emotion and require active recovery') to explain why the persona is needed to specify the *severity* and *texture* of that arc, not just its general direction. This makes the persona requirement feel practical, not procedural."

### Fix 7: Add "referral and loyalty" framing to post-resolution stages
Add to Step 3 guidance:

> "For the final stage, explicitly consider: what does the emotional state at resolution mean for future customer behaviour? Relief is not the same as delight. A customer who is relieved the process is over is not a referrer. Flag whether the end-state emotion creates advocacy, retention, or churn risk — this is often the most executive-relevant insight in the map."
