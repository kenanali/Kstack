# Grading Notes — persona-build skill (EVAL-6)

Evaluated against: response_prompt1.md (research-rich input) and response_prompt2.md (no-research input)

---

## What the Skill Did Well

### Prompt 1 (research-rich)
- **Evidence tagging was rigorous and specific.** Every claim was tagged [EVIDENCED], [INFERRED], or [ASSUMED], with explicit justification for each tag. The evidence review table at Step 6.5 was particularly well-executed — it made the knowledge quality legible at a glance, which is exactly what the skill promises.
- **The skill extracted signal from behavioral data correctly.** The 4.2 calls were correctly interpreted as compensating behaviour (anxiety-driven status-checking), not preference for phone. The 38% income verification drop-off was correctly identified as an anxiety trigger rather than just a technical friction point. These are non-obvious inferences and the skill made them well.
- **The Designer's Note added genuine value.** The four observations (don't fix paperwork without fixing visibility; judgment anxiety is a silent suppression behaviour; branch switch is failure-not-engagement; rate is absent from complaints) were counterintuitive and actionable — exactly what this section is supposed to deliver.
- **The composite quote was handled correctly.** It was clearly marked [COMPOSITE — not verbatim] with explicit citation of the research elements it was built from. No invention was disguised as evidence.
- **Channel preferences were correctly nuanced.** The skill distinguished between *current channel behaviour* and *channel preference*, noting that phone calls are compensating behaviour — a distinction that matters for service design decisions.

### Prompt 2 (no-research)
- **The refusal was firm, principled, and well-reasoned.** The skill did not capitulate and produce a stereotyped persona. It explained precisely why building from "general knowledge" is dangerous for this demographic specifically (age ≠ digital comfort) and what the risks are for downstream design decisions.
- **The refusal was constructive, not obstructive.** It offered three concrete paths forward (desk research, rapid interviews, provisional labelled persona) with effort estimates and appropriate caveats for each. This is the right shape of response — it moves the work forward rather than stopping it.
- **The Option C condition was correctly handled.** Requiring explicit acknowledgment before proceeding with an assumption-only persona is the right safeguard.

---

## What the Skill Missed or Could Have Done Better

### Prompt 1

1. **Step 6.5 check-in was skipped in live form.** The skill noted "Proceeding with current evidence tagging for evaluation purposes" — but in a real session, the mandatory check-in is the skill's most important quality gate. The SKILL.md instruction says "Wait for response and update accordingly." This step should not be a soft opt-out. The skill file should make clearer that in an async/evaluation context, the check-in must be simulated as a genuine pause, not narrated around. Consider adding language like: "If running in evaluation mode, complete the check-in as a written exchange — present the summary and explicitly state what the user's response might change."

2. **Social jobs were thin and lacked push-back.** The social job ("be seen by family as someone who did this responsibly") was tagged [INFERRED] correctly, but the skill didn't interrogate whether there are competing social tensions — e.g., some first-home buyers actively *don't* want to involve family and are doing this independently, or feel pressure from a partner to choose well. The skill accepted the most obvious social reading. A sharper researcher would probe this.

3. **Technology comfort description was a missed opportunity.** The output correctly identified moderate comfort, but the channel preferences section was relatively thin. It didn't surface the specific digital frustrations listed in Step 4 of the skill framework (what do they find frustrating about current digital experiences?) — only behavioural facts. The emotional texture of digital frustration is missing: *why* does switching to branch feel necessary, not just *when*.

4. **Trigger events 3 and 4 were both [INFERRED] from the same signal.** Trigger 3 (status anxiety) and the call behaviour are derived from the same 4.2-calls-per-application data point. The skill surfaced them as separate trigger events without flagging that they're both inferences from the same evidence. This inflates the apparent evidence base slightly.

5. **The persona card "Goals" section was underdeveloped.** The three goals listed are reasonable but generic ("secure a mortgage," "get through without mistakes," "feel like she made the right choice"). This section should include the deeper motivational goal — e.g., "Become a homeowner without feeling like the bank made a fool of her." The goals as written could apply to almost any first-home buyer persona.

### Prompt 2

6. **The response didn't ask the one question that would have changed the output most.** Before offering the three options, the skill could have asked: "What is this persona being used for, and when?" If the answer is "a design sprint starting Monday," Option C is clearly appropriate. If the answer is "a product strategy brief," Option A is minimum. The skill presented the options in parallel rather than helping the user navigate to the right one. A quick diagnostic question would have been sharper.

7. **The Option C output wasn't described specifically enough.** The response says it will construct a "provisional persona where every single claim is tagged [ASSUMED]" but doesn't tell the user what that would actually look like or what it would cover. A brief description of the provisional persona's scope (the dimensions it would address, the assumptions it would be making) would help the user make an informed choice.

---

## Specific Weaknesses to Fix in SKILL.md

### Fix 1: Strengthen the Step 6.5 mandatory check-in instruction
Current language says "Ask the user" and "Wait for response." This is too soft. Add explicit handling for evaluation/batch contexts:

> "This check-in is mandatory. Do not proceed to the Output Format section without completing it. If running in evaluation, batch, or async mode, simulate the check-in as a written exchange: state what you would present to the user, what answers might change the persona, and what you would update based on each possible response."

### Fix 2: Add explicit tension-probing to Social Jobs
In Step 1, under Social Jobs, add:

> "Don't accept the most obvious social reading. Ask: is there a competing social tension? (e.g., independence vs. family approval, speed vs. being seen to be careful). Social jobs are often ambivalent."

### Fix 3: Add "emotional texture" prompt to Channel Preferences (Step 4)
Current Step 4 asks what frustrates them about digital experiences, but the output format doesn't explicitly capture this. Add to Step 4:

> "Describe not just *which* channel they use for *which* task, but what the emotional experience of each channel switch feels like — is it relief? resignation? embarrassment? The channel switch itself is evidence about the experience."

### Fix 4: Add a "trigger event provenance" check
Add a note in Step 2:

> "If multiple trigger events are inferred from the same data point (e.g., different moments in a call volume pattern), flag this explicitly — don't present them as independently evidenced."

### Fix 5: Add a diagnostic question to the no-research refusal path
In the skill framework (or its equivalent handling for Option C in the refusal case), add:

> "Before presenting options, ask: what is this persona for and when is it needed? This determines which option is appropriate — don't present all options as equally valid when the use case and timeline make one clearly right."

### Fix 6: Strengthen the Goals section in the Output Format
In the Output Format, add guidance for the Goals section:

> "Goals should capture the *motivational* goal, not just the functional task goal. 'Secure a mortgage' is a task goal. 'Become a homeowner without being made to feel like an outsider to the financial system' is a motivational goal. The persona card should include at least one of the latter."
