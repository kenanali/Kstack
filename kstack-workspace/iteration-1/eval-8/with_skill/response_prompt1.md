# Journey Map — First-Home Buyer: Mortgage Application

---

## Section 1: Journey Overview

**Persona:** Sarah Chen, 31 — first-home buyer, anxious about being judged, needs to feel in control and informed. Core anxiety: not knowing where she is in the process; fear of being declined.

**Journey trigger:** Sarah has received pre-approval from one bank and decides to formally apply with a lender she's comparing. She begins the application online.

**Journey resolution:** Sarah receives formal mortgage approval (or a decline decision) and the application process concludes.

**Channels involved:** Website (online application), Mobile App (status checking), Email (notifications), Contact Centre — Inbound (4+ calls per application average), Branch — In-Person (for complex steps), Physical Materials (document submission, printed contracts).

**Journey stages:**
1. Deciding to Apply — comparing and committing to a lender
2. Starting the Application — getting in online and understanding what's required
3. Gathering and Submitting Documents — dealing with paperwork and income verification
4. Waiting Without Visibility — the opaque middle phase
5. Reaching Out for Answers — calling the bank to find out what's happening
6. Getting the Outcome — receiving approval or decline
7. Completing the Formalities — signing and settling (approval path)

---

## Step 2.5: Stage Confirmation Note

*(In a live session, stages would be confirmed with the user before proceeding. The above stages are proposed based on the persona context and the known journey structure. Proceeding on that basis for evaluation.)*

---

## Section 2: Journey Map Table

---

### Stage 1: Deciding to Apply

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| Comparison/aggregator site | Comparison & Aggregator Sites | Scans rate comparison tools and reads reviews | "The rates look similar. How do I know which process is actually going to be less painful?" | Uncertain, cautious | 2 | No reliable way to compare lenders on process experience, only rate | Y — First impression of lender formed here | Surface process transparency and customer experience ratings at the point of comparison, not just rate |
| Lender website — product/service info page | Website | Reads mortgage product page and eligibility information | "OK so I think I qualify. But I still don't know what they'll actually ask me for." | Hopeful, slightly anxious | 3 | Information is product-focused, not process-focused. No "here's what to expect" guidance | Y — Decision to proceed starts here | Add a "How it works" process overview and document checklist to the product page, before the CTA |
| Word of mouth — friend/family | Word of Mouth | Calls a friend who recently got a mortgage | "She said theirs was a nightmare but that was a different bank. Maybe this one will be better?" | Nervous, seeking reassurance | 2 | No reliable source of process-level comparison | N | N/A at this touchpoint, but opportunity to design for referrability later |

---

### Stage 2: Starting the Application

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| Online application form — start | Website — Online application or form | Creates account and begins form; reads through initial fields | "OK, this seems manageable so far. I hope it doesn't get complicated." | Cautiously optimistic | 3 | No indication of how long the form is or what stages are coming | N | Add a progress indicator showing all phases upfront — sets expectations and reduces abandonment |
| Online application form — document requirements revealed mid-form | Website — Online application or form | Reaches income verification section and discovers document list | "Wait, I need two years of tax returns AND payslips AND bank statements? I don't have all of this ready." | Surprised, frustrated | 2 | Document requirements not communicated upfront; discovered mid-flow | Y — This is the point at which 38% abandon | Move full document checklist to before the form begins, as a "gather these first" pre-application step |
| Account creation / registration confirmation email | Email — Transactional confirmation | Receives confirmation email after starting application | "Good, at least I know it saved. But now what? Do I just wait?" | Uncertain | 2 | Email confirms creation but gives no guidance on next steps or timeline | N | Transform confirmation email into an onboarding email: what happens next, what to prepare, expected timeframe |

---

### Stage 3: Gathering and Submitting Documents

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| Document upload interface | Self-Service Portal — Claims or application portal | Gathers documents and uploads them one by one | "I hope this is the right format. It doesn't say what file type it needs. Did that actually upload?" | Stressed, uncertain | 2 | No real-time confirmation of upload success; no guidance on format requirements; no acknowledgement that submission is complete | Y — Successful document submission is critical to progression | Add per-file upload confirmation, format guidance, and a "submission complete" state with clear next step |
| Branch — staff consultation | In-Person — Branch — Staff consultation or service delivery | Visits branch to ask about income verification requirements | "I feel embarrassed asking this. Like I should have already known. The person behind the desk is nice enough but I can tell they're busy." | Anxious, slightly humiliated | 2 | Asking basic questions at branch triggers judgment anxiety identified in research | Y — This interaction determines whether she trusts this lender | Train branch staff with first-home buyer scripts; normalise the questions; brief consultation guides that treat asking as expected, not remedial |
| Income verification — additional request | Email — Account alert or notification | Receives an email asking for an additional document | "But I already submitted everything. Why didn't they tell me this at the start? Am I failing?" | Frustrated, worried | 1 | Ad hoc document requests after initial submission feel like failure signals; no context about why it's needed or what it means for the application | Y — This is a critical anxiety point and a driver of the 38% abandonment | Reframe additional document requests as a progress notification: "We're moving forward — to complete this step, we need one more item: [X]. Here's why: [brief reason]." |

---

### Stage 4: Waiting Without Visibility

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| Account dashboard | Website — Account dashboard | Logs into account to check status | "It still just says 'Application in Progress.' That's what it said five days ago. What does that even mean?" | Frustrated, anxious | 1 | Status display is static and uninformative; shows that *something* is happening but not what | Y — Every failed status check compounds distrust | Build a live application tracker: stage-by-stage progress, current stage clearly marked, estimated time to next update |
| No proactive communication (absence of touchpoint) | — | Waits without hearing anything | "Maybe something went wrong. Maybe they've already decided no and just haven't told me. Should I call?" | Catastrophising, resigned | 1 | Total silence from the lender for days at a time while the application is under assessment | Y — Silence reads as bad news to anxious applicants | Implement a "no news is good news" proactive communication cadence: brief SMS/email every 48-72 hours confirming the application is progressing even when there's nothing new to report |

---

### Stage 5: Reaching Out for Answers

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| IVR menu navigation | Contact Centre — Inbound — IVR | Calls the bank; navigates the menu trying to find the mortgage application option | "None of these options say 'check on my application.' Is it 'home loans'? 'New applications'? 'Existing accounts'?" | Frustrated, impatient | 1 | IVR menu not designed around the applicant's mental model; forces them into ambiguous categories | N | Add a "Check the status of an existing application" option to the IVR tree |
| Queue / hold experience | Contact Centre — Inbound — Queue / hold | Waits on hold, listening to repeated hold music | "I've been on hold for 12 minutes. I'm doing this from my lunch break. I'm not going to make it." | Stressed, resentful | 1 | Hold wait times are incompatible with working applicants' schedules | N | Offer an automated callback option at queue entry; this single change reduces hold-time resentment dramatically |
| Agent conversation — information gathering | Contact Centre — Inbound — Agent conversation — information gathering | Finally gets through; explains she wants a status update | "I've explained this three times now. She asked for my reference number, then my date of birth, then put me on hold again." | Exhausted, defeated | 2 | No visible case context for agent at call start; applicant must re-identify and re-explain every time | Y — This is the moment the lender could recover trust — or confirm her worst fears about the process | Surface full application context to the agent before the call begins; the agent should greet with "I can see your application — it's currently at [stage]" not "Can you give me your reference number?" |
| Agent conversation — outcome delivery | Contact Centre — Inbound — Agent conversation — outcome delivery | Agent tells her the application is with the assessor and should be 5-7 more business days | "Five to seven more days?! That's two weeks from now. Why didn't the website tell me that?" | Deflated, slightly relieved to have an answer | 2 | Information is available inside the bank but not surfaced proactively to the customer | Y — The answer she gets here shapes her perception of the entire experience | The content of this answer should be on the digital tracker, not gated behind a phone call |

---

### Stage 6: Getting the Outcome

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| Formal approval notification email | Email — Transactional confirmation | Receives email with approval outcome | "Oh my god. It's approved. I actually did it." | Elated, relieved, proud | 5 | On the approval path, this moment is genuinely positive — but note that the emotion reflects relief from anxiety as much as joy from achievement | Y — This is the highest-stakes moment of truth in the journey | Make this email feel like a celebration, not a system notification. Include: what happens next, timeline to settlement, a clear "you're on your way" message. This is a loyalty moment. |
| Decline notification (alternative path) | Email — Account alert or notification | Receives decline notification by email | "I can't believe I went through all of that and got told no by email. I don't even know why." | Devastated, humiliated, angry | 1 | Decline by email without explanation, without a call, without an offer of support or next steps | Y — Potentially the most damaging moment of truth in the entire journey | Decline outcomes must never be delivered by automated email alone. Require a proactive outbound call; include explanation; offer an alternative pathway or timeline. |

---

### Stage 7: Completing the Formalities (Approval Path)

| Touchpoint | Channel | Customer Action | Customer Thought | Feeling | Emotion Score | Pain Point | Moment of Truth | Opportunity |
|---|---|---|---|---|---|---|---|---|
| Contract / loan documents (digital or physical) | Physical Materials — Contract or agreement document | Receives and reviews final loan documents | "This is 47 pages. I don't know what half of this means. Am I supposed to just sign it?" | Overwhelmed, anxious | 2 | Document complexity and volume at the final stage; no plain-language summary | Y — Final commitment point: confusion here can cause last-minute withdrawal | Provide a 1-page "What you're agreeing to" plain language summary alongside the full contract |
| Settlement confirmation | Email — Transactional confirmation | Receives settlement confirmation | "It's real. It's actually done." | Joyful, proud, exhausted | 5 | None at this moment — it's genuinely positive | Y — End-state shapes long-term perception and referral likelihood | Use this moment to invite NPS feedback while the emotion is positive; also seed the relationship with the next logical product (insurance, offset account) |

---

## Section 3: Emotional Arc

Sarah begins the journey in a state of cautious optimism shadowed by low-level anxiety — she has pre-approval, which gives her confidence she can qualify, but she doesn't know what the process ahead actually requires of her. The first significant emotional drop happens at the document discovery stage, when she realises she doesn't have what's needed and the form offers no grace — just requirements and a cursor. The arc bottoms out in Stage 4, during the extended silence of the assessment phase: with no status updates and no proactive contact, anxiety escalates into near-catastrophising, and every day of silence is interpreted as a potential bad signal. The phone call in Stage 5 provides partial relief — at least she has an answer — but the relief is exhaustion, not satisfaction; she should not have had to call at all. On the approval path, the outcome email produces genuine elation, but the emotional quality of that elation is more *relief from sustained anxiety* than pride in a seamless experience — which reveals how much cumulative stress the journey has inflicted. The overall arc exposes a lender relationship that begins transactionally and, through process failure, becomes adversarial by the midpoint — with the resolution phase doing heavy lifting to recover goodwill that should never have been lost.

---

## Section 4: Top 5 Moments of Truth

1. **Income verification document request mid-form (Stage 3)** — This is where 38% abandon. The gap between what Sarah expected and what was suddenly required at this step is the single highest-leverage point in the entire journey. Getting this right (pre-application checklist) is the most direct lever on completion rate.

2. **Extended status silence during assessment (Stage 4)** — The absence of communication is experienced as active indifference. Because Sarah's dominant anxiety is "not knowing where I am," the silence during the longest phase of the journey inflicts the most cumulative damage. This is a moment of truth spread across days, not seconds.

3. **First call to the contact centre (Stage 5 — IVR + agent)** — This call should not be necessary. The fact that Sarah is making it is already a failure signal. But it's a recoverable moment: an agent who immediately surfaces her application context, names the stage, and gives a confident timeline can partially restore trust. An agent who asks her to re-identify and then puts her on hold compounds the injury.

4. **Formal approval notification (Stage 6)** — On the approval path, this is the highest positive moment. Its emotional quality determines whether Sarah becomes a referrer or simply a relieved customer. The gap between a warm, celebratory communication and a generic system email is the difference between a loyal customer and one who felt the process "worked out eventually."

5. **Additional document request mid-process (Stage 3)** — This touchpoint reads to Sarah as "you did something wrong," when it is actually normal underwriting process. Reframing it from a failure signal to a progress signal is a low-cost intervention with high anxiety-reduction impact.

---

## Section 5: Top 5 Opportunity Areas

1. **Building a real-time application status tracker at [Website — Account Dashboard / SMS notifications] would eliminate the majority of Sarah's 4+ calls because the information she is calling for (current stage, next step, expected timeline) is already known to the bank — it's just not surfaced to the customer.** The mechanism is transparency, not process change.

2. **Moving the full document checklist to before the application form begins [Website — pre-application step] would reduce income verification abandonment because Sarah would arrive at that stage prepared, not surprised.** The mechanism is expectation-setting; the current design creates the crisis by revealing requirements progressively rather than upfront.

3. **Implementing a proactive "no news is good news" communication cadence [Email / SMS — every 48-72 hours during assessment] would reduce anxiety and call volume during the silent middle phase because it converts absence-of-contact from a negative signal into a reassurance signal.** Brief, automated messages ("Your application is progressing — we'll be in touch by [date]") require no manual effort.

4. **Reframing additional document requests as progress notifications [Email — account alert] would reduce abandonment at the follow-up document request stage because it repositions a normal underwriting step from a perceived failure signal to a confirmation that the application is advancing.** The content is nearly identical; the framing is entirely different.

5. **Requiring a proactive outbound call for all decline outcomes [Contact Centre — Outbound] would reduce the reputational damage of the decline path because an email-only decline is experienced as cold, unexplained rejection, while a human call with explanation and alternatives reframes a negative outcome as a relationship the bank wants to preserve.** This is a trust and referral protection measure, not a conversion measure.

---

## Section 6: Design Provocations

1. **If Sarah is calling 4.2 times per application and 73% feel overwhelmed, what does that tell us about how we've designed digital self-service — and whether we're actually trying to replace the calls or just tolerate them?**

2. **The 38% abandonment at income verification is the most measurable failure point in the journey. But is the real problem the documents — or the fact that we've built a form that reveals requirements mid-commitment, when the cost of stopping feels higher than the cost of proceeding confused?**

3. **Sarah's emotional arc ends in relief, not delight. She got her mortgage. But she wouldn't describe the experience as "great." What would it take for a first-home buyer to end this journey saying "I'm so glad I went with that bank" — and are we designing for that outcome, or just for completion?**
