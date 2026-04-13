# Scraping Strategy Reference

## Source Priority Order

### Tier 1: Direct Pricing Pages
The highest-confidence source. Most SaaS and product companies maintain a public `/pricing` page.

**Approach:**
1. Construct URL: `https://[competitor].com/pricing`
2. Use web_fetch to retrieve the page
3. If pricing is hidden behind "Contact Us," note this as an enterprise signal
4. Check for annual/monthly toggle — always capture both
5. Look for embedded schema markup (JSON-LD) which often contains structured pricing data

**What to extract:**
- Tier names (these are intentional brand signals — note them)
- Price points per tier per billing cadence
- Feature lists per tier — copy verbatim, normalize later
- CTA language ("Start Free", "Get a Quote", "Talk to Sales") — reveals segment targeting
- Any footnotes or asterisks — often contain critical conditions

**Red flags that signal enterprise-only pricing:**
- "Custom pricing" with no anchor
- "Starting at" language without a ceiling
- Demo-required flows
- Case studies replacing pricing pages entirely

---

### Tier 2: G2 and Capterra

These aggregators often surface pricing data that companies don't publish directly, including:
- User-reported pricing from reviews
- Historical pricing changes mentioned in reviews
- Pricing sentiment ("too expensive for what you get", "fair for the value")

**G2 search pattern:**
```
site:g2.com "[competitor name]" pricing
```
Or navigate to: `https://www.g2.com/products/[product-slug]/pricing`

**Capterra search pattern:**
```
site:capterra.com "[competitor name]" pricing
```

**What to extract from aggregators:**
- Listed price ranges (often more current than company pages)
- "Free trial available" / "Free version available" signals
- User review excerpts mentioning pricing — these are real WTP signals
- Pricing model category (one-time, subscription, usage-based)

**Aggregator reliability note:**
G2/Capterra pricing data can lag 3–6 months. Cross-reference with direct pages when discrepancies appear. Tag aggregator data as `[MARKET: G2]` or `[MARKET: Capterra]` — never as `[MARKET: competitor-name]` directly.

---

### Tier 3: Indirect Signals (supplementary)

When direct and aggregator data is thin or hidden, use:

**Job postings:**
- Senior AE / Enterprise Sales roles → signals active upmarket push
- "Deal sizes of $X–$Y" in JD → reveals actual contract range
- SDR:AE ratio → indicates volume vs. enterprise motion

**Press / funding announcements:**
- "Closed $Xm in ARR" with known customer count → implied ACV
- Customer logos on homepage → infer segment from brand tier

**LinkedIn:**
- Headcount in Sales vs. CS → reveals whether they're hunting or farming
- Growth rate of CS team → signals retention challenges or expansion motion

Tag all indirect signals as `[INFERRED]` — they are signals, not pricing facts.

---

## Handling Anti-Scraping Measures

Some pages block automated fetching. If web_fetch fails:
1. Try the Google cache: `cache:[url]`
2. Search for the pricing page content directly: `"[competitor] pricing [tier name] per month"`
3. Check Wayback Machine signals via search: `site:web.archive.org [competitor] pricing`
4. Fall back to G2/Capterra as primary source
5. Note the block in the report — "Contact us" walls are themselves a strategic signal

---

## Data Capture Template

For each competitor, populate:

```
Competitor: [name]
Source URL: [url]
Date captured: [date]
Pricing model: [per seat / usage / flat / hybrid / hidden]

Tiers:
  [Tier 1 name]: $[price]/[unit] | Features: [list]
  [Tier 2 name]: $[price]/[unit] | Features: [list]
  [Tier 3 name]: $[price]/[unit] | Features: [list] or "Contact Sales"

Annual discount: [%] or [not offered]
Free tier / trial: [yes/no/trial length]
Notable CTA language: [verbatim]
Aggregator data: [G2/Capterra price range if different]
Pricing sentiment from reviews: [1–2 sentences]
```
