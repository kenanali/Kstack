# KStack

**13 expert slash-command skills for CX transformation, brand strategy, and pricing intelligence — inside Claude Code.**

Each skill encodes a specific methodology: the way a senior service designer, management consultant, or brand strategist actually works through a problem. Skills chain together — the output of one becomes the input of the next.

---

## Skills

### CX Transformation

| Skill | Behaves as | What it does | Accepts |
|---|---|---|---|
| `/trend-scan` | Futurist + macro analyst | Macro trend radar across PESTLE + tech waves, scored for CX relevance | Analyst reports, strategy decks, competitor intelligence, news/social listening exports, Google Trends exports, VOC reports |
| `/biz-context` | Management consultant | Five-domain business diagnostic + Porter's Five Forces + key tensions | Annual reports, board papers, financial summaries, NPS/CSAT/VOC reports, org charts, website analytics, social listening, employee engagement surveys |
| `/scan-blockers` | Organizational consultant | Full blocker map across 8 categories, rated by severity and addressability | Stakeholder interview transcripts, CX post-mortems, org charts, process docs, complaint data, strategy/transformation roadmaps |
| `/persona-build` | UX researcher + behavioral psychologist | Rich persona with JTBD, trigger events, anxieties, and unmet needs | Interview transcripts, survey verbatims, segmentation decks, CRM profiles, NPS/VOC reports, review site exports, social listening, usability test notes |
| `/journey-map` | Senior service designer | Stage-by-stage journey map with emotion scores, moments of truth, and HMW opportunities | `/persona-build` output, interview transcripts, call summaries, complaint data, NPS verbatims, existing journey maps, session recordings |
| `/service-map` | Service designer + operations consultant | 5-layer service blueprint with failure points and handoff risks | `/journey-map` output, process maps, system architecture diagrams, org charts, SLA docs, ticket/case management exports, incident logs |
| `/synthesize` | Senior strategist | Insight clusters, tension map, ranked How Might We questions, burning platform | Any KStack skill outputs, research reports, interview notes, workshop outputs, complaint analysis, contact reason data |
| `/biz-case` | Management consultant + financial analyst | 7-section executive business case — every number tagged as data-backed or assumption | `/biz-context`, `/synthesize`, `/scan-blockers` outputs, financial data, operational metrics, benchmark reports, prior business cases |
| `/prioritize` | Portfolio strategist | Multi-criteria initiative scoring, phased roadmap, and sequencing recommendation | `/synthesize` or `/biz-case` outputs, initiative lists, budget/resource constraints, technology roadmaps, capability assessments |

### Brand Strategy

| Skill | Behaves as | What it does | Accepts |
|---|---|---|---|
| `/brand-building-blocks` | Brand strategist + research synthesizer | 5-8 named building blocks across Audience, Company, and Moment forces | `/persona-build`, `/biz-context`, `/trend-scan` outputs, interview transcripts, VOC/NPS verbatims, review exports, brand audits, competitive analysis |
| `/brand-territories` | Brand strategist + creative director | 3 distinct territory directions, each anchored by a different emotional benefit | `/brand-building-blocks` output, existing brand positioning docs, competitor brand analysis, prior territory work |
| `/name-check` | Naming strategist + clearance analyst | Generate candidate names from a creative brief, then run a multi-source clearance sweep — trademark, app stores, domains, social handles, web presence — with an interactive refinement loop until a clear name is found | `/brand-territories` output (optional), creative brief, existing name candidates |
| `/pricing-intelligence` | Competitive pricing analyst | Full competitive pricing intelligence report — market data scraping, tier architecture inference, buyer WTP matrix, gap analysis, and decision-ready recommendations tagged as [MARKET], [PERSONA], or [INFERRED] | `/persona-build` output (optional), competitor list, product category description |

Skills flow in phases:

```
/session-start → creates output folder

Phase 1: Intelligence          Phase 2: Customer Understanding
  /trend-scan                    /persona-build
  /biz-context                   /journey-map
  /scan-blockers                 /service-map
       └──────────── both feed into ────────────┘
                          /synthesize
                        /biz-case  /prioritize

Brand track: /brand-building-blocks → /brand-territories → /name-check
(feeds from /persona-build, /biz-context, /trend-scan)

Pricing track: /pricing-intelligence
(can consume /persona-build output for WTP analysis)
```

---

## Installation

**Requires:** [Claude Code](https://claude.ai/code)

### Option A — Clone with git

```bash
git clone https://github.com/YOUR_USERNAME/KStack.git
cd KStack
./setup
```

### Option B — Download as zip (no git required)

1. Click **Code → Download ZIP** on the GitHub repo page
2. Extract the zip and open the `KStack` folder in VS Code
3. Open the VS Code terminal and run:

```bash
./setup
```

Either way, restart Claude Code after setup — all skills will appear in the slash command menu.

---

## How to use

Start a session for an engagement:

```
/session-start Acme Health
```

This creates `outputs/acme-health-2026-03-25-1400/` and all subsequent skills write their outputs there automatically. Run any skill next:

```
/trend-scan
/biz-context
/persona-build
/journey-map
```

Skills ask intake questions, work through their methodology, and save their output as a file — an HTML document you can open in a browser, or a markdown document you can paste into any tool.

**Chaining outputs:** Paste the output of one skill directly into the next session. `/synthesize` is designed to consume outputs from Phase 1 and Phase 2 together.

> **Note:** Sessions and file outputs work best in Claude Code running in a terminal or VS Code. In the Claude web app or desktop app, outputs may stay in the chat rather than being saved as files.

---

## Requirements

- [Claude Code](https://claude.ai/code)
- macOS or Linux (the setup script uses symlinks)
- Claude Pro or above recommended for longer skill sessions

---

## Inspiration

Built in the spirit of [gstack](https://github.com/garrytan/gstack) — domain expertise encoded as slash commands that give you a specific cognitive mode on demand. Where gstack encodes engineering and product thinking, KStack encodes CX transformation and brand strategy thinking.

---

## Changelog

### v1.11.0 — Pricing Intelligence (2026-04-13)

New `/pricing-intelligence` skill for full competitive pricing analysis. Three input paths: market data only, persona data only, or both combined. Produces a normalized competitor pricing table, tier architecture inference, buyer WTP matrix per persona, gap analysis (underlap/overlap/overhang), and decision-ready recommendations with every claim tagged as [MARKET], [PERSONA], or [INFERRED]. Also ships `/name-check` — naming strategy and multi-source clearance sweep with interactive refinement loop, KB fallback when web tools are unavailable, and adverse-association screening at generation.

### v1.10.0 — Session Management + Disclaimer Footers (2026-03-25)

New `/session-start` skill creates a dated output folder per engagement; all skills read `.kstack-session.json` and write their outputs there automatically. All HTML and markdown outputs now include an AI disclaimer and creator credit. HMW opportunities freed from prescriptive 1:1 category requirements — 3–7 quality questions per stage, tagged thematically where appropriate.

### v1.9.2 — Journey Map Visual Improvements (2026-03-25)

Synthesis footer redesigned to light slate (no more black panel); Top Opportunities column removed for cleaner two-column layout; HTML generation moved to isolated subagent to prevent context stalling on large outputs.

### v1.9.1 — Journey Map HTML Output (2026-03-25)

`/journey-map` automatically generates a self-contained visual HTML file at the end of every session. Horizontal grid layout with stages as columns, six content rows, and emoji-based emotion indicators.

### v1.9.0 — Porter's Five Forces (2026-03-25)

`/biz-context` — Porter's Five Forces assessment added to Market Position domain, with intensity, trend, and CX implication per force.

### v1.8.0 — Brand Strategy Track (2026-03-24)

Two new skills: `/brand-building-blocks` and `/brand-territories`. Feeds from `/persona-build`, `/biz-context`, and `/trend-scan`.

### v1.7.0 — Persona Design Principles (2026-03-24)

`/persona-build` — Purpose-calibrated scope, explicit exclusion guidance, contextual narrative section, beyond-the-product unmet needs.

### v1.6.0 — Live Data Integration (2026-03-23)

`/biz-context`, `/trend-scan`, `/biz-case` — Live web search and public data retrieval when user-provided data is missing. All web-sourced findings labeled for verification.

### v1.5.0 — Interview Synthesis (2026-03-23)

Advanced multi-interview analysis across `/persona-build`, `/synthesize`, and `/scan-blockers`. Individual transcript analysis before cross-interview synthesis; dominant vs. outlier theme distinction.

### v1.4.0 — Evidence Scaffolding (2026-03-23)

"What to Upload" intake tables in every skill. Expanded blocker taxonomy, decision points in service map, mandatory confirmation gates in journey map and service map.

### v1.3.0 — Journey Architecture (2026-03-23)

`/journey-map` — Stage header blocks, named insight cards with sourced evidence, per-stage HMW questions, linear vs. cyclical journey type.

### v1.2.0 — Signal Grounding (2026-03-23)

Skills grounded in real-world data signals. Community verbatim in persona build; multi-source confirmation in trend scan; unfiltered sentiment vs. formal NPS in biz context.

### v1.1.0 — Portfolio Refinement (2026-03-23)

`/workshop-prep` removed. KStack narrowed to 11 core skills across intelligence, customer understanding, synthesis, activation, and brand strategy.

### v1.0.0 — Initial Release (2026-03-23)

First full evaluation cycle across all skills. 20 test cases, graded, and improved.
