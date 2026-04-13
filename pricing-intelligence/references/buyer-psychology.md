# Buyer Psychology and WTP Framework Reference

## Core Principle

Willingness to pay is not a number. It is a psychological state determined by:
1. How the buyer **frames the value** of the purchase
2. What **reference point** they use to anchor price
3. What **risk** they associate with the purchase decision
4. What **budget context** they're operating in

Stated WTP (what people say they'll pay) and revealed WTP (what they actually pay) diverge significantly. This framework excavates the psychology behind both.

---

## The Four Primary WTP Frames

### Frame 1: Risk-Reduction Buyer
**Psychology:** Prices relative to the cost of the bad outcome this product prevents.
**Signals in persona data:** Mentions of compliance, liability, downtime, errors, loss of customers, regulatory risk. Language like "can't afford for this to go wrong."
**WTP logic:** They will pay a significant fraction of the risk they're trying to eliminate. A $500k compliance risk justifies $50k+ in tooling.
**Pricing implication:** Anchor price to the risk cost, not the feature set. ROI framing works better than feature comparison.
**Sweet spot behavior:** Will pay more than they expect to, but need to see the risk quantified. Undersell and they'll question your credibility.

### Frame 2: Status / Peer-Reference Buyer
**Psychology:** Prices relative to what peers or competitors are spending. Wants to be in the right category — not cheapest, not most expensive.
**Signals in persona data:** References to what competitors use, what "companies like us" do, what their industry standard is. Job titles that carry external visibility (CMO, CTO, VP of).
**WTP logic:** They will pay to be in the peer cluster. If the peer cluster uses the $500/month tool, they won't seriously consider the $50/month alternative — it signals they're not at the same level.
**Pricing implication:** Price at or slightly above the peer cluster. Discounting signals downmarket. Case studies from peer companies matter more than ROI calculators.
**Sweet spot behavior:** The sweet spot is whatever the perceived "serious" option costs in their peer group — research this specifically.

### Frame 3: Time-Compression Buyer
**Psychology:** Prices relative to how much time or effort this saves. Thinks in hours, cycles, headcount.
**Signals in persona data:** Mentions of bandwidth, being stretched thin, "we don't have time to," needing to move faster, reducing cycles.
**WTP logic:** Calculate the cost of the time being saved. If this saves a $150k/year employee 20% of their time, that's $30k/year in recovered capacity. They'll pay a fraction of that.
**Pricing implication:** Make time savings concrete and visible. Speed to value matters — long onboarding destroys this buyer's WTP before they've seen the return.
**Sweet spot behavior:** They want to buy quickly. Complex procurement is a WTP destroyer. Simple pricing structures and fast starts increase effective WTP.

### Frame 4: Budget-Constrained Buyer
**Psychology:** Prices on what they have access to, not what the product is worth. The ceiling is the budget bucket, not the value.
**Signals in persona data:** References to budget cycles, approval thresholds, fiscal year timing, needing to stay under a certain number. "We have X available."
**WTP logic:** The question isn't what the product is worth — it's which bucket it comes from (discretionary vs. allocated, opex vs. capex, credit card vs. PO).
**Pricing implication:** Price to fit the budget bucket. Sub-$5k/year is often a manager decision. Sub-$25k/year is often a director decision. $50k+ typically requires VP or C-suite. Know where the approval threshold sits.
**Sweet spot behavior:** Slightly below a round-number threshold is significantly better than slightly above it. $9,800 outperforms $10,200 disproportionately for this buyer.

---

## Persona Intake Protocol

Accept persona data in any format. Extract these elements regardless of input format:

**From structured persona docs:**
- Job title and seniority (maps to budget authority and approval threshold)
- Primary KPIs / what they're measured on (maps to value frame)
- Key frustrations (maps to risk or time compression frame)
- Decision process (maps to budget context and approval chain)
- Tools they currently use (maps to peer reference and switching cost)

**From raw interview notes / VOC:**
- Pull quotes about price sensitivity verbatim — these are gold
- Note any mentions of competitors or alternatives they considered
- Extract any stated budget ranges, even approximate
- Identify emotional language — fear, frustration, aspiration — as WTP frame signals

**From chat description:**
Ask at most 3 of these clarifying questions (choose based on what's missing):
1. "What is their primary pain — avoiding a bad outcome, staying competitive, moving faster, or staying in budget?"
2. "What would happen if they didn't solve this problem? What's at stake?"
3. "Who approves the purchase, and what's the typical budget threshold for that person?"

---

## WTP Estimation Methodology

Never fabricate a number. Construct WTP estimates from triangulated signals:

**Signal sources (in confidence order):**
1. Verbatim price mentions from persona interviews or reviews `[PERSONA]`
2. Current tool spend mentioned by persona `[PERSONA]`
3. Budget authority thresholds implied by seniority `[INFERRED]`
4. Competitor pricing at equivalent tier `[MARKET]`
5. Value-frame calculation (risk cost, time cost, peer cluster) `[INFERRED]`

**Always produce three estimates:**
- **Floor:** Below this, they question legitimacy or value
- **Ceiling:** Above this, they exit regardless of value
- **Sweet Spot:** The price that feels right for their frame — explain why

**Confidence levels:**
- High confidence: 2+ direct signals from persona data
- Medium confidence: 1 direct signal + frame inference
- Low confidence: Frame inference only — flag as `[INFERRED — low confidence]`

---

## Multi-Persona WTP Dynamics

When multiple personas are involved in a purchase decision (e.g., end user + budget holder + IT):

- Map each persona's frame independently
- Identify the **primary buyer** (who controls budget) vs. **influencer** (who champions internally)
- The primary buyer's ceiling sets the hard limit
- The influencer's frame determines how the value story must be told
- WTP sweet spot is where both frames are satisfied simultaneously

---

## Red Flags in WTP Analysis

- **Uniform WTP across all personas:** Almost never true. Personas at different seniority levels have different budget authority and different frames. If your matrix is uniform, you haven't dug deep enough.
- **WTP that exactly matches market midpoint:** This is the consensus answer. It means you've anchored to market data rather than buyer psychology. Run the frame analysis again independently of market data.
- **No floor estimate:** Every buyer has a legitimacy threshold. If a product is priced too low, it signals low quality. Identify the floor — it matters for discounting strategy.
