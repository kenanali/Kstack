# Tier Architecture Inference Reference

## The Core Principle

Tier structures are not arbitrary. Every pricing tier reflects a deliberate hypothesis about:
1. Which buyers exist in the market
2. What each buyer values most
3. Where the upgrade trigger lives
4. What the company is optimizing for (growth, retention, expansion revenue)

Reading tier architecture is reading competitive strategy.

---

## The Four Tier Archetypes

### Archetype 1: The Land-and-Expand Stack
**Pattern:** Very cheap or free entry tier → significant jump to mid tier → enterprise on request
**What it reveals:** Company is optimizing for bottom-up adoption. They want to get into the org at low friction and expand from within. Individual users are the initial buyer; budget holders are the eventual buyer.
**GTM implication:** Product-led growth motion. Sales team is expansion-focused, not acquisition-focused.
**Example signals:** Free tier with team limits, seat-based upgrade triggers, "invite your team" CTA on free plan.

### Archetype 2: The Segment Carve
**Pattern:** Distinct tiers priced for clearly different segments (individual / team / org / enterprise)
**What it reveals:** Company has done real segmentation work. They know who buys at each level and have priced to extract value at each segment's WTP. Tier lines are drawn at natural organizational boundaries.
**GTM implication:** Multi-motion sales — PLG for low tiers, outbound for upper tiers.
**Example signals:** Tier names that reference org size or role type, hard limits that map to team structures.

### Archetype 3: The Feature Gate Stack
**Pattern:** Similar price points across tiers but dramatically different feature sets
**What it reveals:** Company believes certain features have high perceived value and is using them to drive upgrade behavior. The price delta is small; the value delta is large. Often signals a product with sticky advanced features.
**GTM implication:** CS-led expansion. Customers upgrade when they need the feature, not when they hit a seat limit.
**Example signals:** "Advanced analytics", "API access", "SSO" appearing only at upper tiers.

### Archetype 4: The Anchor + Custom
**Pattern:** 1–2 self-serve tiers + immediate "Contact Sales" for anything meaningful
**What it reveals:** The published tiers are anchoring tools, not the real business. The company lives in enterprise deals. Self-serve tiers exist to create price reference points and capture SMB overflow.
**GTM implication:** Enterprise-first, sales-led motion. Product is a demo vehicle.
**Example signals:** Very low self-serve ceiling (seats, usage, features), prominent "Talk to Sales" CTAs even on mid tiers.

---

## Upgrade Trigger Analysis

The upgrade trigger is the single feature or limit that forces a tier change. It is the most important strategic decision in tier design.

**Common upgrade triggers:**
| Trigger Type | Example | What it reveals |
|---|---|---|
| Seat ceiling | "Up to 5 users" | Company believes team adoption drives value |
| Usage cap | "1,000 API calls/month" | Company can quantify value per unit |
| Feature gate | "SSO on Enterprise only" | Feature has high enterprise value, low SMB relevance |
| Data limit | "10GB storage" | Company expects data growth to correlate with value |
| Workflow limit | "5 active projects" | Company believes workflow expansion = success |
| Support SLA | "Priority support on Business" | Company knows support is a pain point at scale |

**The diagnostic question:** If you removed the upgrade trigger, would customers stay on the lower tier forever? If yes, the trigger is a forcing function — it's not adding value, it's extracting it. This is a competitive vulnerability if a challenger removes the same gate.

---

## Tier Naming as Signal

Tier names are brand decisions that reveal strategic intent:

| Name Pattern | Signal |
|---|---|
| Free / Pro / Business / Enterprise | Generic — company hasn't differentiated positioning |
| Starter / Growth / Scale | Growth-oriented framing — targets startups and scaling teams |
| Individual / Team / Organization | Org-size segmentation — B2B focus |
| Basic / Standard / Premium | Value-ladder framing — commodity market signal |
| [Named tiers: "Spark" / "Blaze"] | Brand-forward — company invests in perceived differentiation |
| Single tier + "Enterprise" | Two-motion company — mass market + enterprise |

---

## White Space Detection

After mapping all competitor tier architectures, look for:

**Price gaps:** Is there a meaningful price range with no competitive offering? (e.g., everyone jumps from $50 to $200 with nothing in between)

**Segment gaps:** Is there a buyer profile that none of the tier structures address well?

**Feature gaps:** Is there a feature that users consistently request in reviews that no tier includes?

**Model gaps:** Is everyone per-seat in a market where usage-based would be more natural?

Document each gap as: `Gap identified → Who it affects → Strategic opportunity`
