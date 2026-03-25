# kstack Decision Engine — Requirements & Vision

**Version:** 0.2 — Obsidian-First Memory Architecture
**Date:** March 2026
**Context:** An additive "Decision Track" for the kstack skill system that transforms analysis into rigorous, memory-backed, debate-tested decisions.

---

## The Problem It Solves

kstack is a masterclass at *getting to* a decision. After running through `/trend-scan`, `/biz-context`, `/persona-build`, `/journey-map`, `/synthesize`, and `/prioritize`, you have everything you need to decide — but the moment of actual deciding is left to the human, unassisted.

That gap is where most strategic value leaks. Great analysis gets collapsed into hasty choices. Trade-offs go unexamined. Second-order consequences are ignored. And three months later, nobody can remember *why* they chose Option A over Option B.

The Decision Engine closes that gap. It is not a replacement for human judgment — it is a structured adversary, memory system, and accountability layer that makes the judgment itself dramatically better.

---

## Where It Sits in the kstack Stack

```
INTELLIGENCE PHASE        CUSTOMER UNDERSTANDING        SYNTHESIS
/trend-scan               /persona-build                /synthesize
/biz-context        →     /journey-map          →       /biz-case
/scan-blockers            /service-map                  /prioritize
                                                              |
                                                              ↓
                                              [ DECISION ENGINE ]
                                            /decide-frame
                                            /decide-debate
                                            /decide-tradeoffs
                                            /decide-record
                                                 |
                                                 ↓
                                          [ MEMORY VAULT ]
                                    Obsidian Vault (primary layer)
                              Dataview · Backlinks · Canvas · Smart Connections
                                                 |
                                                 ↓
                                          /decide-review  (async)
```

The Decision Engine is a new third track — **Decision Track** — that accepts structured markdown outputs from existing kstack skills as its primary inputs.

---

## Skill Architecture: The Four-Skill Decision Loop

### 1. `/decide-frame` — Sharpen the Decision

**Purpose:** Transform a fuzzy strategic question into a decision that can actually be debated and recorded.

**Inputs:** Outputs from `/synthesize`, `/prioritize`, or `/biz-case` (or any combination).

**What it does:**

- Extracts the core decision statement from kstack outputs and forces one precise sentence: *"We are deciding whether to [action] in order to [outcome] by [date]."*
- Classifies the decision on two axes:
  - **Reversibility:** Type 1 (irreversible, high stakes) vs. Type 2 (reversible, low stakes) — following Bezos's framing.
  - **Complexity domain** (Cynefin): Simple / Complicated / Complex / Chaotic — because different domains require different decision-making modes.
- Surfaces **the real decision** beneath the stated one. (Teams often debate tactics when the real unresolved decision is strategic.)
- Defines what a "good decision" looks like, independent of outcome — because luck and quality are not the same thing.
- Identifies who owns the decision vs. who is merely consulted.

**Decision gate:** Human confirms the framed decision before proceeding.

---

### 2. `/decide-debate` — Run the Adversarial Council

**Purpose:** Stress-test the decision through structured multi-perspective debate before any choice is made.

**Inputs:** Framed decision from `/decide-frame`, supporting context from kstack.

**The Council — Five Expert Voices:**

Each voice is an AI agent instructed to argue from a genuine perspective, not just play-act:

| Voice | Role | Primary Question |
|---|---|---|
| **The Strategist** | Argues for the leading option | What does this enable long-term? |
| **The CFO** | Financial & resource lens | What does this cost, really — including opportunity cost? |
| **The Customer** | Voice of the people most affected | What does this look like from the other side? |
| **The Devil's Advocate** | Genuine opposition | What if everything we're assuming is wrong? |
| **The Pre-Mortem Ghost** | Future failure narrator | It's 18 months from now and this failed — what happened? |

Research basis: Published work from ACM's IUI 2024 conference shows LLM-powered devil's advocates are *more effective* than human ones, precisely because they have no social inhibition and no career to protect. They will argue against the CEO's idea without flinching.

**Debate Protocol:**
1. Each voice gets an opening statement (2-3 paragraphs).
2. Cross-examination: each voice surfaces the single strongest challenge to one other voice's argument.
3. Synthesis of the sharpest unresolved tensions.
4. A forced "integrative thinking" prompt: *"What would a solution look like that doesn't require making this trade-off at all?"* — per Jennifer Riel's HBR integrative thinking model.

**Outputs:** Structured debate transcript, ranked tensions, integrative possibility flags.

---

### 3. `/decide-tradeoffs` — Map the Consequence Architecture

**Purpose:** Make trade-offs explicit, quantified where possible, and connected to downstream dependencies.

**Inputs:** Debate output, kstack analysis.

**What it does:**

**Criteria Weighting:**
- Elicits the criteria that matter (growth, risk, speed, customer impact, team capacity, brand coherence).
- Forces explicit weighting — teams often *think* they've agreed on criteria until they see the weights assigned.
- Runs a weighted decision matrix across 2-4 options.

**Second-Order Consequences Map:**
For each leading option, maps three rings:
- **Ring 1 — Direct effects:** What immediately changes.
- **Ring 2 — Second-order effects:** What changes *because* Ring 1 changed. (This is where most strategic surprises live.)
- **Ring 3 — Third-order signals:** What to watch as early warning indicators.

Inspired by Farnam Street's second-order thinking framework and the "pre-mortem" methodology from Gary Klein.

**Dependency Architecture:**
- *What must be true* for this decision to work (assumptions that need to hold).
- *What this decision unlocks* (downstream decisions that become possible).
- *What this decision forecloses* (paths that close off).
- *What other active decisions depend on this one* — pulled from the Decision Memory Vault.

**Wardley Mapping Integration (Optional):**
For decisions about capability-building or market positioning, a simplified Wardley axis can be generated: where does this capability sit on the evolution spectrum (Genesis → Custom → Product → Commodity)? Is the decision moving *with* or *against* the evolutionary current?

**Output:** Trade-off matrix, second-order map, dependency graph (markdown-renderable), assumption register.

---

### 4. `/decide-record` — Commit to Memory

**Purpose:** Capture the decision and its full reasoning before the organizational memory fades.

**Inputs:** All outputs from the three preceding skills.

**The Decision Record — fields:**

```yaml
decision_id: DEC-2026-042
date: 2026-03-24
decision: "We are choosing to [X] over [Y] and [Z]."
decision_type: Type-1 / Type-2
cynefin_domain: Complex
owner: [name/role]
stakeholders: [list]

context_inputs:
  - kstack_skill: synthesize
    file: cx-synthesis-q1-2026.md
  - kstack_skill: prioritize
    file: opportunity-prioritization.md

alternatives_rejected:
  - option: "Option B"
    reason: "Too resource-intensive given current capacity constraints (see CFO argument)"
  - option: "Option C"
    reason: "Closes off the international expansion path we want to preserve"

expected_outcomes:
  - outcome: "30% improvement in NPS within 9 months"
    confidence: 0.65
  - outcome: "Team capacity stretched for Q2"
    confidence: 0.85

assumptions_required:
  - "Customer segment X will respond to self-serve"
  - "Engineering can ship MVP in 6 weeks"

dependencies:
  unlocks: [DEC-2026-038, DEC-2026-040]
  depends_on: [DEC-2026-031]

review_date: 2026-09-24
```

**Obsidian Integration:**
Each decision record is written as a markdown note into an Obsidian vault via the Obsidian MCP server. Notes include:
- Bidirectional links to related decisions using `[[decision_id]]` syntax.
- Tags for domain, decision type, outcome status.
- Embedded links back to the kstack outputs that informed it.
- A `#to-review` tag with the scheduled review date.

The vault becomes a navigable decision graph — not just a log.

---

## The Memory Layer

This is the architectural backbone that makes the engine compound in value over time. The approach is **Obsidian-native first** — using Obsidian's built-in capabilities as the primary memory and retrieval system, with a clear upgrade path to semantic search only when the vault grows large enough to warrant it.

### Why Obsidian-Native First

Obsidian is not just a notes app — it is a local-first, markdown-based knowledge graph with a query engine (Dataview), a visual canvas, and a bidirectional link system. For the volume of decisions a typical strategy practitioner makes (5–20 significant decisions per quarter), these native capabilities are sufficient and far simpler to maintain than external infrastructure.

The Obsidian MCP server is the bridge that makes this actionable: it lets Claude read from and write to the vault directly, meaning every `/decide-record` output becomes a permanent, navigable, queryable artefact without any manual copy-paste.

### Memory Architecture: Two Tiers (Obsidian-Native)

**Tier 1 — Working Memory (conversation context)**
The current kstack session and decision being processed. Ephemeral — exists only for the duration of the session.

**Tier 2 — Vault Memory (Obsidian)**
The durable layer. Every decision record, debate transcript, assumption, and outcome log lives here as a markdown file. This tier does four things:

*Structured retrieval via Dataview.* Dataview treats the YAML frontmatter of every decision note as a database. You can query across the entire vault with SQL-like syntax:

```dataview
TABLE decision, owner, review_date, outcome_status
FROM "decisions/active"
WHERE review_date <= date(today)
SORT review_date ASC
```

This surfaces *"all decisions overdue for review"* without any external tooling. Similarly: all decisions in a given domain, all decisions with unresolved assumptions, all decisions that unlocked a specific downstream choice.

*Graph traversal via backlinks.* Every decision note links to related decisions using `[[DEC-2026-031]]` syntax. Obsidian's graph view makes the dependency architecture visual — you can see at a glance which decisions are load-bearing (many things depend on them) and which are downstream leaves. The MCP server can traverse these links programmatically during `/decide-frame` to surface related decisions automatically.

*Semantic search via Smart Connections (optional plugin).* Smart Connections is an Obsidian plugin that runs local embeddings over the vault and enables natural-language queries *within* Obsidian — without any external vector database or running service. It is the one piece of semantic capability that fits within an Obsidian-native architecture. It answers questions like *"what have we previously decided about customer self-serve?"* even when no note uses those exact words. It is the recommended bridge between pure keyword search and a full vector DB.

*Canvas for dependency mapping.* Obsidian Canvas lets you place decision notes on a visual board and draw arrows between them — a human-readable version of the dependency graph that can be shared or reviewed in strategy sessions.

### Vault Structure

```
/decisions/
  /active/          ← decisions in-flight or awaiting review
  /reviewed/        ← closed decisions with outcome logged
  /templates/       ← the standard decision record template
/kstack-outputs/
  /cx-transformation/
  /brand-strategy/
  /innovation/
/assumptions-register/  ← one note per recurring assumption, linked across decisions
/outcome-log/           ← running log of actual outcomes, linked to decision records
```

The `/assumptions-register/` folder is a key addition. Rather than burying assumptions inside individual decision notes, each significant assumption gets its own note — *"Customer segment X responds to self-serve"* — and every decision that relies on it links to it. When a review reveals an assumption was wrong, that single note gets updated and every linked decision is immediately surfaced. This is Obsidian's native knowledge graph doing work that a vector DB would otherwise handle.

### How Claude Queries the Vault

With the Obsidian MCP server connected, Claude can:

- Read the full contents of any decision note by ID
- Search notes by tag, folder, or YAML field value
- Follow backlinks to retrieve the dependency chain of a decision
- Write new notes (decision records, retrospectives) directly into the vault
- Update outcome status and review dates on existing notes

The queries that matter for the Decision Engine map cleanly onto these primitives:

| Decision Engine Need | Obsidian Mechanism |
|---|---|
| "What decisions depend on this one?" | Backlink traversal via MCP |
| "Show me decisions overdue for review" | Dataview query on `review_date` |
| "What assumptions have we made about pricing?" | Backlinks to `/assumptions-register/pricing-sensitivity` |
| "Find decisions related to this topic" | Smart Connections semantic search |
| "What did we decide about enterprise customers?" | Tag filter + Dataview on `themes:` field |
| "Which assumptions turned out wrong?" | Dataview on `assumption_status: failed` |

### The `themes:` Field: Lightweight Semantic Layer

The one discipline the Obsidian-native approach requires is consistent use of the `themes:` field in the decision record YAML. This is a list of free-text tags that capture the conceptual territory of the decision — not just the domain, but the strategic question it touches.

```yaml
themes:
  - pricing-sensitivity
  - enterprise-segment
  - self-serve-adoption
  - channel-strategy
```

These themes are the backbone of Dataview queries and the primary way Claude can find related decisions without semantic search. The key is that they are normalised across the vault — `enterprise-segment` always means the same thing, not sometimes `enterprise` and sometimes `B2B`. The `/decide-record` skill enforces this by checking proposed themes against existing ones in the vault and suggesting matches before writing a new note.

### Claude's Vault Writing Protocol

The semantic layer only works if every note written to the vault follows the same discipline. Because Claude is writing these notes via the MCP server — not a human — it can enforce this consistently. The following protocol defines exactly what Claude must do every time it writes a decision record or related note.

**Step 1 — Theme normalisation before writing.**
Before writing a new decision note, Claude queries the vault for the full list of existing `themes:` values across all decision records. It then maps the new decision's concepts to existing themes where a match exists, and only mints a new theme tag if there is genuinely no appropriate existing one. This prevents the vocabulary drift that breaks Dataview queries over time (e.g., `enterprise` vs `enterprise-segment` vs `B2B-enterprise` all meaning the same thing).

Prompt used internally:
> *"Here are all themes currently in the vault: [list]. The new decision concerns [topic]. Which existing themes apply? If a new theme is needed, what is the canonical form it should take?"*

**Step 2 — Backlink to the assumptions register.**
Every assumption listed in `assumptions_required:` must have a corresponding note in `/assumptions-register/`. Before writing, Claude checks whether each assumption already has a note. If it does, it links to it using `[[assumption-slug]]` syntax. If it doesn't, it creates the assumption note first, then links. This ensures the assumptions register stays complete and every assumption is navigable across decisions.

**Step 3 — Backlink to related decisions.**
Claude queries the vault for decisions sharing themes with the new record, decisions listed in `depends_on:` or `unlocks:`, and any decision flagged during `/decide-frame` as relevant context. All are linked using `[[DEC-YYYY-NNN]]` syntax within the note body and in the YAML frontmatter. This builds the graph progressively — each new decision enriches the connections of prior ones.

**Step 4 — Outcome status initialisation.**
Every new decision note is written with `outcome_status: open`. This is the field Dataview queries use to surface decisions awaiting review. Claude never writes a note without this field populated.

**Step 5 — Write the inverse link.**
When a decision note lists `unlocks: [DEC-2026-038]`, Claude also opens DEC-2026-038 and adds the new decision to its `depends_on:` list if not already present. Links in Obsidian are bidirectional by convention but the YAML is not — Claude enforces the bidirectional relationship explicitly.

**Step 6 — Validate completeness before committing.**
Before writing any note to the vault, Claude checks that all required YAML fields are populated: `decision_id`, `date`, `decision`, `decision_type`, `cynefin_domain`, `owner`, `themes`, `alternatives_rejected`, `expected_outcomes`, `assumptions_required`, `dependencies`, `review_date`, `outcome_status`. Partial records create dead ends in the graph. If any required field is missing, Claude asks before writing rather than leaving it blank.

**What this means in practice:** the human using the Decision Engine never has to think about tagging, linking, or vault hygiene. Every note Claude writes is correctly wired into the graph. The semantic layer is an emergent property of Claude's writing discipline, not a separate system to maintain.

### Upgrade Path: When to Add a Vector DB

The Obsidian-native architecture is the starting point. The upgrade to an external vector database (Chroma, SQLite-vec, or FAISS pointed at the vault directory) becomes worth the complexity when one of these conditions is met:

- The vault exceeds ~75 decision records and Dataview queries + Smart Connections are returning too much noise
- Queries increasingly require synthesising *across* many decisions simultaneously (rather than retrieving specific ones)
- The engine is being used by a team, not a solo practitioner, and the vault grows faster than themes can be normalised manually

At that point, the entire vault is already in a vector-DB-ready format (structured markdown with YAML frontmatter), so the migration is additive — a new retrieval layer, not a replacement of the existing one.

---

## `/decide-review` — The Closing of the Loop

**Purpose:** Return to past decisions at scheduled intervals to compare predicted vs. actual outcomes, and feed learnings back into the engine.

**Trigger:** Scheduled task (e.g., monthly Cowork automation) that surfaces decisions with a `review_date` in the past.

**What it does:**
- Pulls the original decision record from the vault.
- Prompts the user for actual outcomes against each predicted outcome.
- Scores the decision on two dimensions: *quality of process* (were the right questions asked?) and *quality of outcome* (did it land well?).
- Updates the assumption register: which assumptions held, which failed.
- Generates a "decision retrospective" note linked back to the original.
- Over time, surfaces patterns: *"Decisions about customer-facing features have consistently underestimated implementation time"* or *"Our devil's advocate arguments about resource constraints have been right 70% of the time."*

This is the compound interest mechanism. Each review makes the next debate smarter.

---

## Cross-Skill Intelligence: What the Engine Learns to Do

As the decision vault accumulates records, the engine gains emergent capabilities:

**Pattern Detection:**
- Which types of decisions consistently get the assumptions wrong?
- Which Council voices have historically been most predictive for this team?
- Are there recurring tensions that suggest a structural organizational issue?

**Proactive Dependency Alerts:**
When running `/decide-frame`, automatically scan the vault and surface: *"This decision touches the same assumptions as DEC-2026-031, which was made 4 months ago and is currently under-performing. You may want to revisit that context before proceeding."*

**Calibration Tracking:**
When users assign confidence levels (e.g., 0.65) to expected outcomes, track actual hit rate. Over time, determine whether this team over- or under-estimates confidence, and apply a calibration nudge in future debates.

**Strategic Coherence Check:**
Before recording a new decision, scan the vault for conflicts: *"This decision assumes 'price sensitivity is low' — but DEC-2026-029 was made under the assumption 'price sensitivity is high'. These may need reconciliation."*

---

## Integration with Existing kstack Skills

The Decision Engine doesn't replace existing skills — it reads their outputs as evidence:

| kstack Skill | What it feeds into the Decision Engine |
|---|---|
| `/synthesize` | Primary strategic context for `/decide-frame` |
| `/prioritize` | The option set and ranking that frames the debate |
| `/biz-case` | Financial data for the CFO voice and trade-off matrix |
| `/scan-blockers` | Pre-loaded ammunition for the Devil's Advocate |
| `/persona-build` | Voice of the Customer council member |
| `/trend-scan` | Environmental assumptions for the second-order map |

A new `/decide` shortcut can accept any combination of these as `--input` flags and route them automatically.

---

## Technical Implementation Considerations

### Skill Design Principles (Consistent with kstack Philosophy)
- Each skill encodes a specific methodology, not generic prompting.
- Decision gates at critical moments require human validation before proceeding.
- Outputs are structured markdown designed to be machine-readable by subsequent skills.
- Evidence is tagged as "evidenced" (from kstack outputs) or "inferred" (generated reasoning).

### Obsidian Plugins Required

- **Dataview** — SQL-like queries over vault YAML frontmatter. Core to every dashboard and structured retrieval query.
- **Smart Connections** — Local embedding-based semantic search within the vault. Enables natural-language queries without an external vector DB.
- **Templater** — Enforces the decision record template structure on every new note created by Claude or the user.
- **Canvas** (built-in) — Visual dependency mapping of the decision graph.

### MCP Servers Required

- **Obsidian MCP Server** — Read/write to vault, query notes by field/tag, traverse backlinks. The primary integration layer between Claude and the memory vault.
- **Scheduled Tasks MCP** — Triggers `/decide-review` automatically on each decision's `review_date`.

### MCP Servers Optional

- **Google Drive MCP** — Pull in meeting notes, strategy docs, and board presentations as additional context for the debate engine.
- **Gmail MCP** — Surface relevant email threads as supporting context when framing a decision.

### Memory Architecture Upgrade Path

| Stage | When | Stack |
|---|---|---|
| **Stage 1 — Start here** | 0–75 decisions | Obsidian + Dataview + Smart Connections + MCP |
| **Stage 2 — Semantic scale** | 75–200 decisions, queries getting noisy | Add local Chroma or SQLite-vec pointed at vault directory |
| **Stage 3 — Team scale** | Multi-user, fast-growing vault | GraphRAG layer over vault for dependency traversal at scale |

---

## Open Questions / Design Decisions

1. **Multi-user vs. solo?** Should the vault support team decision records, with multiple human stakeholders able to add their actual perspective to each Council voice? Or is this always a solo practitioner tool?

2. **How opinionated should the Council be?** The devil's advocate is more effective when it genuinely believes its arguments. Should the voices have persistent "personalities" tuned to this organization's context, or be fresh each time?

3. **Where does decision quality get scored?** Is there value in a numeric "decision quality score" per record, or does that create false precision that undermines the tool?

4. **Integration with `/brand-territories` and `/brand-building-blocks`?** Brand decisions are a distinct decision category — the Decision Engine should probably have a brand-specific Council voice (e.g., "The Brand Steward") when inputs come from the Brand Strategy track.

5. **Hallucination discipline:** The engine will generate debate arguments, second-order effects, and dependency suggestions. These must be clearly flagged as *generated reasoning*, not evidence — and the structured evidence tagging system from kstack must be extended to cover this.

---

## Guiding Principles

**The engine is an adversary, not an assistant.** It is designed to challenge the decision, not validate it. A good session feels slightly uncomfortable.

**Memory compounds.** A decision engine with one entry is useful. With 50 entries, it becomes indispensable. The design should optimize for consistency of capture, not sophistication of individual records.

**Decisions are hypotheses.** Every decision record is a prediction about the future. The review loop is how hypotheses get tested. Without it, the engine is just a fancy journal.

**Process quality ≠ outcome quality.** A good decision made with bad information and rushed judgment can get lucky. A rigorous decision process should be rewarded even when outcomes disappoint. The engine tracks both.

---

*This document is a living requirements artifact. It should be run through `/decide-debate` before any implementation begins.*

---

## Research References

The Decision Engine draws on published research across decision science, AI, and knowledge management. These references are the intellectual foundation for specific design choices and should be surfaced in the README and any future front-end documentation.

### Decision Science & Strategy Frameworks

**Bezos's Type 1 / Type 2 Decision Framework**
The reversibility classification in `/decide-frame` is based on Jeff Bezos's 2015 Amazon shareholder letter, which distinguishes one-way-door (Type 1) decisions from two-way-door (Type 2) decisions. The framework argues that Type 2 decisions are being made too slowly by most organisations because they apply Type 1 processes to them.

**The Cynefin Framework — Snowden & Boone (HBR, 2007)**
The complexity domain classification in `/decide-frame` draws on David Snowden and Mary Boone's Cynefin framework, which defines five decision contexts (Clear, Complicated, Complex, Chaotic, Confused) and argues that misidentifying the domain is the root cause of most strategic decision failures.
[A Leader's Framework for Decision Making — HBR](https://hbr.org/2007/11/a-leaders-framework-for-decision-making)

**Integrative Thinking — Jennifer Riel (HBR, 2025)**
The forced integrative thinking prompt at the end of `/decide-debate` ("What would a solution look like that doesn't require making this trade-off at all?") is grounded in Riel's work on moving beyond either-or decision framing, building on Roger Martin's original model.
[Moving Beyond Either-Or Decision-Making — HBR On Leadership Podcast](https://hbr.org/podcast/2025/09/moving-beyond-either-or-decision-making)

**How to Make a Seemingly Impossible Leadership Decision (HBR, 2025)**
Informs the `/decide-tradeoffs` protocol — specifically the four guidelines: map the trade-offs, pressure-test the plan, use principles not just policies, and name the change.
[How to Make a Seemingly Impossible Leadership Decision — HBR](https://hbr.org/2025/11/how-to-make-a-seemingly-impossible-leadership-decision)

**Lean Strategy Making — Bain & Company / HBR (2025)**
The structured, repeatable approach to `/decide-frame` is informed by Bain's research showing that inconsistent, ad-hoc decision processes are the primary cause of strategic underperformance — and that leading companies standardise their decision protocols without sacrificing nuance.
[Lean Strategy Making — HBR](https://hbr.org/2025/05/lean-strategy-making)

**Second-Order Thinking — Shane Parrish / Farnam Street**
The three-ring consequence architecture in `/decide-tradeoffs` (direct effects → second-order effects → third-order signals) is adapted from Parrish's work on second-order thinking, which argues that most poor decisions result from optimising for first-order effects while ignoring what changes downstream.
[How a Decision Journal Changed the Way I Make Decisions — Farnam Street](https://fs.blog/decision-journal/)

**Pre-Mortem Methodology — Gary Klein**
The Pre-Mortem Ghost council voice in `/decide-debate` is drawn from Gary Klein's prospective hindsight technique: imagining a future failure in vivid detail before a decision is made dramatically improves the identification of risks that forward-looking analysis misses. Originally published in HBR.

**Wardley Mapping — Simon Wardley**
The optional Wardley axis in `/decide-tradeoffs` draws on Simon Wardley's strategy mapping methodology, which positions capabilities on an evolution spectrum (Genesis → Custom → Product → Commodity) to reveal whether strategic moves are working with or against market evolution.

### AI & Decision Intelligence

**Decision Intelligence — The Decision Lab**
Foundational framing for the Decision Engine as a system that models the entire decision-making process end-to-end, including goals, constraints, risks, and trade-offs, while incorporating real-time data and contextual awareness.
[Decision Intelligence — The Decision Lab](https://thedecisionlab.com/reference-guide/computer-science/decision-intelligence)

**Intelligent Choices Reshape Decision-Making — MIT Sloan Management Review**
Research on AI-augmented decision-making, covering how dynamic intelligent choice architectures embed AI insights into decision frameworks to deliver choices that are personalised, predictive, and ethically aware.
[Intelligent Choices Reshape Decision-Making — MIT Sloan](https://sloanreview.mit.edu/article/intelligent-choices-reshape-decision-making-and-productivity/)

**Decision Intelligence Platform Review — NexStrat AI (2025)**
Market landscape overview covering leading enterprise decision intelligence platforms and their approaches to agentic AI, real-time insights, and strategic frameworks for senior leadership.
[Decision Intelligence Platform Review — NexStrat AI](https://www.nexstrat.ai/blog/decision-intelligence-platform-review/)

### Knowledge Management & Memory Architecture

**AI-Native Second Brain — Remio (2026)**
The memory vault architecture — ingesting decision outputs into a living, AI-backed knowledge base queryable with citations via RAG — draws on the emerging second brain design pattern.
[AI Native Second Brain — Remio](https://www.remio.ai/post/ai-native-second-brain-ultimate-guide)

**Obsidian Memory MCP Server — Skywork AI**
Technical reference for the Obsidian MCP server integration, covering how AI memory maps to markdown files to improve Claude's ability to read, write, and traverse the decision vault.
[Unlocking Your AI's Brain: Obsidian Memory MCP Server — Skywork AI](https://skywork.ai/skypage/en/ai-obsidian-memory-server/1978331309583015936)

**Creating a Decision Log in Obsidian — Obsidian Forum**
Community-sourced reference for decision logging patterns in Obsidian, informing the vault structure and the three-field decision table approach.
[Creating a Decision Log in Obsidian — Obsidian Forum](https://forum.obsidian.md/t/creating-a-decision-log-in-obsidian/51077)

**Thinking Partners: Building AI-Powered Knowledge Management Systems — LessWrong**
Research on the limits of naive RAG (20–40% performance degradation as context grows) and the case for structured prompt construction over raw document retrieval — informing the decision to use Obsidian's structured YAML frontmatter as the primary retrieval layer rather than unstructured semantic search.
[Thinking Partners: Building AI-Powered KMS — LessWrong](https://www.greaterwrong.com/posts/6EJ6hcWQv5FgqtEFs/thinking-partners-building-ai-powered-knowledge-management)
