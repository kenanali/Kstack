---
name: pricing-intelligence
description: Run a full competitive pricing intelligence analysis for any product or service. Use this skill whenever a user wants to understand market pricing, benchmark competitors, analyze tier/packaging architecture, identify pricing white space, or produce a structured competitive pricing report with buyer psychology and willingness-to-pay analysis. Trigger when users say things like "analyze competitor pricing", "what should we charge", "how are competitors structured", "scrape pricing pages", "build a pricing report", "understand market pricing", "tier analysis", "willingness to pay", "what would my personas pay", or any variation of competitive pricing research. Also trigger when a user is preparing a go-to-market strategy, pricing a new product, repositioning an existing offering, or hands you persona documents alongside a pricing question. This skill handles three input paths: market data only, persona data only, or both combined — and always produces a recommendations section with clearly sourced rationale tagged as [MARKET], [PERSONA], or [INFERRED].
---

# Pricing Intelligence Skill

## Purpose
Produce a full competitive pricing intelligence report by combining:
- **Outside-in:** Market pricing data scraped from public pages and aggregators
- **Inside-out:** Buyer psychology and willingness-to-pay analysis from persona inputs

The output is a **decision-ready recommendations section** with every claim traceable to a source.

---

## Step 0: Orient and Detect Input Path

Before any analysis, determine which path applies:

| Path | Inputs Present | Approach |
|---|---|---|
| **A — Market Only** | No personas provided | Scrape → Normalize → Tier Inference → Report |
| **B — Persona Only** | No market data requested | Psychology Frame → WTP Matrix → Report |
| **C — Full** | Both inputs present | Run A + B → Gap Analysis → Integrated Report |

**Always state the active path at the start.** If inputs are ambiguous, ask one clarifying question before proceeding.

Also establish:
- What product/service category is being analyzed?
- Who are the 5–10 competitors to include?
- Are there analogous markets worth benchmarking?

---

## Step 1: Market Data Collection (Paths A and C)

Read → `references/scraping-strategy.md`

Collect pricing data from:
1. **Direct pricing pages** — each competitor's public `/pricing` URL
2. **G2 / Capterra / aggregators** — use web search targeting these platforms by category

For each competitor, capture:
- Tier names and prices (monthly + annual if available)
- Features included per tier
- Pricing model type (per seat, usage-based, flat, hybrid)
- Any "contact us" / hidden pricing signals
- Review signals about pricing sentiment (from G2/Capterra)

Tag every data point: `[MARKET: source-url]`

---

## Step 2: Market Normalization

Read → `references/normalization.md`

Raw scraped data is never directly comparable. Normalize across:
- Billing cadence (monthly vs annual — calculate effective monthly)
- Unit basis (per seat vs per org vs per usage unit)
- Feature parity (which tier is actually equivalent?)
- Market segment (SMB vs mid-market vs enterprise tiers)

Output: A normalized competitor pricing table ready for analysis.

---

## Step 3: Tier Architecture Inference

Read → `references/tier-inference.md`

This is the Unknown Known layer — the strategic insight most pricing analysis misses.

For each competitor's tier structure, decode:
- Where are the tier lines drawn and why?
- What feature acts as the "upgrade trigger" between tiers?
- Who is each tier actually designed for (inferred buyer profile)?
- What does the tier structure reveal about their GTM strategy?

The tier logic reveals who they're really selling to and what they believe the market will bear.

---

## Step 4: Persona Intake and Psychology Framing (Paths B and C)

Read → `references/buyer-psychology.md`

Accept persona input in any format:
- **Structured doc (PDF/Word):** Extract JTBD, pain points, decision context, budget signals
- **Raw interview notes / VOC:** Synthesize into psychology profile
- **Chat description:** Ask targeted clarifying questions (max 3) to build the profile

For each persona, identify the **primary WTP frame** (see buyer-psychology.md for full framework):
- Risk-reduction buyer → prices on cost of bad outcome
- Status/peer-reference buyer → prices relative to what peers spend
- Time-compression buyer → prices on speed to value
- Budget-constrained buyer → prices on which budget bucket this comes from

Tag all persona-derived signals: `[PERSONA: persona-name]`
Tag analytical synthesis: `[INFERRED]`

---

## Step 5: WTP Matrix Construction

For each persona × tier combination, produce:

| | Entry / Free | Core / Pro | Advanced / Enterprise |
|---|---|---|---|
| **Persona A** | Floor / Ceiling / Sweet Spot | ... | ... |
| **Persona B** | ... | ... | ... |

Definitions:
- **Floor:** Price below which they question quality or legitimacy
- **Ceiling:** Price above which they exit consideration regardless of value
- **Sweet Spot:** Price that feels calibrated to their frame — not necessarily the midpoint

Source every estimate. Never present an unsourced number. If data is thin, mark the cell `[INFERRED — low confidence]` and explain why.

---

## Step 6: Gap Analysis (Path C only)

Map market pricing against persona WTP matrix:

- **Underlap:** Market charges less than personas would pay → margin opportunity
- **Overlap:** Market and WTP aligned → competitive zone, differentiation required
- **Overhang:** Market charges more than personas will pay → conversion risk or wrong segment signal

This gap map is the strategic core of the full report. Do not skip it on Path C.

---

## Step 7: Assemble the Report

Structure:

```
1. Market Landscape Summary
   - Competitor pricing table (normalized)
   - Pricing model distribution
   - Tier architecture patterns

2. Tier Logic Analysis
   - What the market's tier structures reveal
   - Upgrade trigger patterns
   - Implied buyer targeting per tier

3. Buyer WTP Matrix
   - Per persona × per tier
   - Psychology frame applied
   - Confidence levels noted

4. Gap Analysis (Path C only)
   - Underlap / Overlap / Overhang map
   - Segment-level implications

5. Recommendations
   - Each formatted as: SIGNAL → IMPLICATION → ACTION [SOURCE TAGS]
   - Minimum 3 recommendations, maximum 7
   - Pre-mortem: "If we price this way and it fails in 12 months, why?"
```

---

## Evidence Tagging Protocol

Every factual claim must carry a source tag:

| Tag | Meaning |
|---|---|
| `[MARKET: url or platform]` | Directly scraped from a specific source |
| `[PERSONA: persona name]` | Derived from provided persona input |
| `[INFERRED]` | Analytical synthesis — not raw data |
| `[INFERRED — low confidence]` | Thin data, explicitly flagged |

Never present inference with the same confidence as evidence. The reader must always know which is which.

---

## Anti-Consensus Check (run before finalizing)

Before delivering the report, ask:
- Would any other analyst produce exactly this recommendation from this data?
- Is the pricing recommendation anchored to a non-obvious insight, or just the market midpoint?
- Has the pre-mortem surfaced a real failure mode, or a generic one?

If any answer is "yes / generic" — push one level deeper before delivering.
