# Pricing Normalization Reference

## Why Normalization Is Non-Negotiable

Raw pricing data is never directly comparable. A $99/month plan and a $79/month plan may serve completely different segments at completely different feature depths. Normalization creates the apples-to-apples surface that makes analysis meaningful.

---

## Normalization Layer 1: Billing Cadence

Always convert to **effective monthly cost.**

- Monthly list price → use as-is
- Annual plan → divide total by 12
- If annual pricing is "X/month billed annually" → that is already effective monthly

**Document both:** Record the list monthly price AND the effective annual monthly price. The gap between them is itself a signal — a large gap (>25%) indicates they're aggressively incentivizing annual commitment, which often means churn is a known problem.

---

## Normalization Layer 2: Unit Basis

Competitors rarely price on the same unit. Map everything to a common basis before comparing.

| Pricing Model | Normalization Approach |
|---|---|
| Per seat / user | Calculate at 1, 5, 10, 25, 50 users — the curve matters |
| Per organization (flat) | Calculate implied per-seat cost at target team size |
| Usage-based (API calls, credits) | Estimate cost at low / medium / high usage profiles |
| Tiered usage | Map usage bands to the most common real-world consumption patterns |
| Hybrid (base + usage) | Calculate total cost at each usage profile |

**Key output:** A normalized price-per-user (or per-unit) table at 3 usage/scale scenarios: small, medium, large. This reveals which competitors are optimized for which scale.

---

## Normalization Layer 3: Feature Parity

Not all "Pro" tiers are equivalent. Before comparing prices, establish which tier is actually comparable.

**Method:**
1. Identify the 8–12 features that are most commonly used as tier gates across competitors
2. Map each competitor's tier against this feature set
3. Identify the tier at which each competitor includes the same core feature set
4. Compare prices at that equivalent tier — not at the same tier name

**Common tier gate features to track:**
- SSO / SAML authentication
- API access
- Advanced analytics / reporting
- Custom integrations / webhooks
- Dedicated support / SLA
- White labeling
- Audit logs / compliance features
- Number of seats / workspaces / projects included

---

## Normalization Layer 4: Market Segment Targeting

Competitors are often optimized for different segments even when their pricing looks similar. Decode segment signals:

| Signal | Implied Segment |
|---|---|
| Free tier with usage limits | PLG / SMB / developer |
| "Starter" at <$50/mo | SMB / prosumer |
| "Professional" at $100–500/mo | SMB to mid-market |
| "Business" with seat minimum | Mid-market |
| "Enterprise" with "Contact Sales" | Enterprise / large org |
| No self-serve at all | Enterprise-only |
| Usage-based with no seat concept | Developer / API-first |

When a competitor has a tier you can't map to a segment, treat it as a strategic signal worth investigating — unusual packaging usually reflects an unusual GTM hypothesis.

---

## Output: Normalized Pricing Table

After normalization, produce this table:

| Competitor | Comparable Tier | Effective Monthly (annual) | Per Seat @ 10 users | Segment Target | Free Option | Annual Discount |
|---|---|---|---|---|---|---|
| [Name] | [Tier] | $X | $Y | SMB/MM/ENT | Yes/No | X% |

Plus a separate table for usage-based competitors normalized at the 3 usage scenarios.

---

## Normalization Confidence Flags

| Flag | Meaning |
|---|---|
| ✓ Confirmed | Price confirmed from direct page |
| ~ Estimated | Price inferred from aggregator or indirect source |
| ? Hidden | Pricing not public — enterprise signal |
| ↑ Likely stale | Aggregator data only, may lag 3–6 months |
