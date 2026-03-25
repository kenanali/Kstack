# KStack Changelog

## v2.0 — Journey Map Visual HTML Output (2026-03-25)

`/journey-map` — New final step generates two output files automatically after every session: a structured JSON of the full journey data and a self-contained HTML file with a visual horizontal journey map. The HTML renders stages as columns with six rows (Stage, Narrative, Channels, Feeling, Problems, Opportunities). Emotion is represented as a single emoji per stage (😣→😊) derived from the average touchpoint score. No external dependencies — the HTML file opens directly in any browser.

---

## v1.9 — Porter's Five Forces in Biz Context (2026-03-25)

`/biz-context` — Porter's Five Forces assessment added to Domain 4 (Market Position). Structured table rating each force (Competitive Rivalry, Threat of New Entrants, Threat of Substitutes, Buyer Power, Supplier Power) by current intensity, trend direction, and CX implication. Evidence-grounded — forces rated [UNASSESSED] if data is insufficient. Includes a named "CX-critical forces" callout identifying which combination (rivalry + buyer power + substitutes) creates the most urgency, connected directly to the strategic "So What" in Step 3.

---

## v1.8 — Brand Strategy Track (2026-03-24)

Two new skills extending KStack into brand strategy. The track chains with the existing CX intelligence skills — `/persona-build` feeds the Audience force, `/biz-context` feeds the Company force, `/trend-scan` feeds the Moment force.

### brand-building-blocks (new)

- Synthesizes research across three forces (Audience, Company, Moment) into 5-8 named building blocks
- Each block has full anatomy: name + category + fact + new understanding + proof points
- Mandatory Step 0.5 Force Inventory gate before synthesis — confirms what evidence exists per force and flags thin or absent inputs
- Quality test for each block: relevant, actionable, unrealized, and evidenced
- Output includes Building Block Summary Grid, full anatomy per block, Unexpected Tensions (creative conflicts between blocks), and How to Use guidance for `/brand-territories`

### brand-territories (new)

- Develops 3 distinct territory directions, each anchored by a different leading emotional benefit
- Mandatory Step 0.5 Emotional Space Mapping gate — maps which building blocks orbit which emotional spaces before territories are built; prevents variations on the same idea
- Full territory anatomy: name + leading emotional benefit + concept statement + key characteristics + personality traits + why it works + why it's hard
- "What if we..." scenarios for each territory (2-3 specific activations only this territory would produce)
- Step 1.5 Territory Distinctiveness Check — verifies emotional benefits are genuinely different and each territory makes a different organizational demand

---

## v1.7 — Persona Design Principles (2026-03-24)

Improved `/persona-build` with three additions drawn from research on persona design failures and best practices.

### persona-build

- **Purpose-calibrated scope:** The use case declared in Step 0 now explicitly shapes which sections carry the most weight in the output. Journey mapping → trigger events, anxieties, channel behavior. Workshop/ideation → emotional language and key quote. Design brief → behavioral patterns and technology comfort. Stakeholder alignment → motivational goals and contextual narrative. Previously the use case was noted but didn't change what the persona prioritized.
- **Explicit exclusion guidance:** Step 0 now names what not to include: personality spectrum bars and trait sliders (suggest false precision), hobbies and lifestyle details unrelated to the strategic challenge, demographics-heavy framing that attributes behaviors to age/income rather than motivation, and anything invented to fill a template. "A gap is more honest than a fabrication."
- **"A Day With [Name]" contextual narrative:** New persona card section — 3-5 sentences of grounded context showing how the person's day-to-day creates the conditions for their JTBD, triggers, and anxieties. Drawn only from research; omitted rather than fabricated when data is thin. Makes the JTBD and unmet needs feel inevitable rather than abstract.
- **Beyond-the-product unmet needs:** Step 5 now requires at least one unmet need that connects to context transcending the specific product — something in the customer's broader life or situation the category could address but doesn't. Needs beyond the product reveal innovation opportunities; needs within the product describe incremental improvements.

---

## v1.6 — Live Data Integration (2026-03-23)

Added web search and live data retrieval capabilities to three skills where public information meaningfully supplements what users provide. All web-sourced findings are labeled `[SOURCE: Web search — verify before presenting]` to maintain evidence discipline. Search is conditional — triggered only when the user has not provided the relevant data, not as a replacement for user-supplied materials.

### biz-context

- **New Step 0.5 — Public Data Search:** If financial data, customer sentiment, or competitive intelligence is missing, Claude automatically searches for: annual reports and investor relations pages (WebFetch), review site sentiment (Trustpilot/G2), competitor announcements, and WebFetch of the company homepage to assess digital presence. Results labeled `[SOURCE: Web search — verify before presenting]`
- **Step 1.5 (Data Gap Check):** Now explicitly offers to search public sources when the user cannot provide additional materials
- **Domain 2 — Unfiltered Sentiment:** If no sentiment data provided and Step 0.5 hasn't already retrieved it, skill now runs targeted WebSearch and WebFetch for review site results
- **Domain 4 — Competitive News Velocity:** If no competitor intelligence provided, skill now searches for `"[Competitor name]" announcement OR launch OR partnership [current year]`

### trend-scan

- **New Step 0.5 — Signal Data Search:** If no external signal data (Google Trends, news monitoring, social data, competitive benchmarking) was provided, Claude automatically runs searches across PESTLE dimensions: industry CX trends, regulatory changes, technology signals, Reddit community sentiment, and competitor announcements. Results feed directly into Multi-Source Confirmed validation in Step 2
- **Step 2 — Signal Scoring:** Multi-Source Confirmed definition is now operational — signals corroborated by Step 0.5 search results are marked Multi-Source Confirmed; signals with no detectable public footprint are marked Analyst-Led
- **Step 3 — Competitor Actions:** Before asserting competitor movement, skill now verifies via WebSearch and labels source. Only stated if a specific announcement or news article confirms it

### biz-case

- **Step 1 — Problem Statement "Why Now":** If no competitor analysis provided, skill now searches for competitor capability announcements to validate competitive urgency
- **Step 4 — Value Drivers:** After reading value-driver-library.md, skill now runs targeted WebSearch for industry benchmarks (NPS ranges, churn rates, cost-per-call, FCR rates by industry). Benchmark label extended to `[BENCHMARKED — SOURCE: Web search — verify source before presenting]` with publication and date

### Skills NOT changed

`scan-blockers`, `persona-build`, `journey-map`, `service-map`, `synthesize`, `prioritize` — these skills operate on internal/proprietary data that web search cannot surface. Adding search to these would introduce noise without improving analytical quality.

---

## v1.5 — Interview Synthesis (2026-03-23)

Advanced multi-interview analysis methodology across three skills.

### persona-build

- **Learning Agenda:** Step 0 now asks for 3-5 specific questions the persona research must answer — focuses analysis on what the organization needs to decide, not just what the research contains
- **Dominant Themes vs. Outliers:** When multiple interviews are provided, patterns are now explicitly distinguished by frequency. Outliers (1-2 interviews) are named separately, not dropped — an outlier may be a segment signal or the most strategically important finding
- **Emergent subgroups:** If interview data suggests two distinct customer patterns, the skill now flags this before completing the persona rather than silently flattening variation into false consensus

### synthesize

- **Learning Agenda:** Step 0 now asks for the specific questions the synthesis must answer
- **Between-group segment question:** Step 0 now asks whether distinct segments or stakeholder groups are present and whether analysis should be per-segment or cross-group
- **Section 1 (Affinity Clusters):** Added impact classification per theme — High (blocks key task/shapes trust/core motivation/business outcome risk), Moderate (friction without blocking/influences attitudes/subgroup-specific), Low (cosmetic/individual preference/minimal business consequence)
- **Section 1.5 (Outlier Analysis) — new:** Explicit section for findings that appeared rarely but warrant naming. For each: what it is, where it appeared, why it's worth flagging, and what follow-up would determine significance
- **Section 1.75 (Between-Group Analysis) — new, conditional:** When multiple segments or stakeholder groups are in the data, explicitly surfaces shared patterns, divergences, and group-specific findings. Gap between how groups describe the same situation is often the highest-value insight

### scan-blockers

- **Severity guidance:** Expanded with business-outcome framing (High = blocks key task or threatens major business outcome; Medium = friction without blocking; Low = manageable within existing structure) and context-calibration note (severity is industry and program-stage dependent)

---

## v1.4 — Evidence Scaffolding (2026-03-23)

### All skills — What to Upload

Every skill's Step 0 now includes an explicit **"What to Upload"** table listing specific file types, why each helps, and the priority order. Previously, intake questions said "upload anything relevant" — now each skill names exactly what to bring.

| Skill | Primary inputs named |
|---|---|
| `/trend-scan` | Analyst reports, strategy decks, competitor intelligence, Google Trends exports, news monitoring, social listening, competitive benchmarking |
| `/biz-context` | Annual reports, board papers, financial summaries, NPS/VOC reports, org charts, operational dashboards, competitor analysis, website analytics, review site analysis |
| `/scan-blockers` | Stakeholder interview transcripts, post-mortems, org charts, process docs, employee engagement surveys, complaint data, strategy roadmaps, prior audit reports |
| `/persona-build` | Client audience research files, interview transcripts, call recordings, survey verbatim, CRM profiles, complaint analysis, review site exports, community data, search behavior data |
| `/journey-map` | persona-build output, interview transcripts, complaint data, existing journey maps, session recordings, customer survey data, social listening exports |
| `/service-map` | journey-map output, process documentation, workflow diagrams, org charts, system architecture, SLA docs, stakeholder interview transcripts, case management data, incident logs |
| `/synthesize` | All KStack skill outputs, customer research reports, business performance data, stakeholder interview notes, complaint analysis, workshop outputs |
| `/biz-case` | biz-context output, synthesize output, financial data, operational metrics, benchmark reports, competitor analysis, prior investment memos |
| `/prioritize` | synthesize output, biz-case summaries, biz-context output, scan-blockers output, budget constraints, technology roadmap, org capability assessment |

### scan-blockers

- **Step 0 intake:** Added four specific diagnostic probe questions drawn from organizational assessment research: vision cascade (can working teams describe CX success?), decision rights (where do decisions stall?), execution culture (does the org prototype or conceptualize?), goal alignment (do team metrics compete?)
- **Step 2 fallback categories:** Added Decision Rights & Autonomy and Goal & Incentive Misalignment as named categories alongside the standard eight
- **Step 2 (interview protocol):** When stakeholder transcripts are provided, now instructs analysis per interview before synthesis — inter-stakeholder contradictions are named as a blocker signal type, not smoothed over
- **Step 3 (compound system):** Added "Goal Misalignment Compound" as a named compound pattern — when each team performs well on their own metrics while collectively producing a broken customer experience
- **Step 5 (Landmines):** Added two named landmine types: Competing Team Metrics (polite in workshops, unresponsive when it matters) and Decision Rights Vacuum (steering group makes decisions that frontline managers re-litigate)
- **blocker-taxonomy.md:** Added four new blockers: Vision Cascade Failure and Execution-Ideation Imbalance (to Culture & Leadership); Decision Rights Ambiguity and Competing Team KPIs (to Organizational Structure)

### service-map

- **Layer 3 (Backstage):** Added Decision Points guidance — explicitly call out where backstage decisions are made, who has the authority, and what happens when the decision-maker is unavailable. Decision rights failures are distinct from process failures and require different fixes
- **Stage blueprint:** Added Clock Stops field — where in each stage does a request sit waiting? What is it waiting for? Idle time between process steps is where customer frustration accumulates and is typically invisible in process documentation
- **Failure Point Register:** Added Type column with five named failure point types: Process failure, Decision rights failure, Capability gap, System failure, Incentive misalignment. Naming the type determines the fix
- **Handoff Risk Register:** Added Competing Metrics column — explicitly surfaces whether sending and receiving teams have different success metrics. Handoffs that fail because of incentive misalignment are not fixed by better process documentation
- **Step 5 (Systemic Design Opportunities):** Added Incentive Architecture Check — redesigned backstage won't stick if the teams delivering it are measured on things that conflict with the new design. Incentive change named as a prerequisite, not a nice-to-have

### persona-build, scan-blockers, synthesize — Interview analysis methodology

Applied to all three skills that use interview transcripts as primary inputs:

- **persona-build:** Individual transcript analysis before cross-interview synthesis; structured quote attribution (source + context + reveals); evidence hierarchy noting frequency and segment coverage; Research Gaps as a named output section
- **scan-blockers:** Per-interview extraction before blocker table synthesis; inter-stakeholder contradiction named as a blocker signal
- **synthesize:** Evidence hierarchy in theme evidence (source count + source type diversity); inter-source contradictions flagged as findings, not omissions

---

## v1.3 — Journey Architecture (2026-03-23)

### journey-map

Structural improvements to journey architecture, informed by analysis of how stage-based journeys differ across short transactional cycles and long multi-phase engagement cycles.

- **Step 0 intake:** Added linear vs. cyclical journey question — cyclical journeys require explicit cycle-over-cycle modeling because post-resolution emotional state is the entry state for the next cycle
- **Step 2 (Stage definition):** Stages now include timeframe (how long the stage lasts) and business goal (what the organization is trying to achieve) alongside the customer-perspective name. Timeframe shapes touchpoint design entirely — a "Weeks to Months" planning stage requires different interventions than a "Hours to Days" troubleshooting stage
- **Step 2.5 (Stage check-in):** Now explicitly asks the user to flag stages where business goal and customer emotional state are in conflict — these goal-experience tensions are where the most important design work lives
- **Step 3 (Per-stage header block):** Each stage now opens with a structured header before the touchpoint table: name / timeframe / business goal / customer entry state / **user need** (a synthesized statement of what the customer genuinely needs to succeed at this stage, functional not emotional) / goal-experience tension. User need field is directly brief-ready for product/service designers.
- **Step 3.5 (Stage insight cards — new):** After each touchpoint table, 2-4 named behavioral observations with ALL-CAPS memorable title + details + sourced evidence. Evidence requires source attribution (Customer Interviews, Analytics, Benchmark — named). These are the workshop-sticky, presentation-quotable outputs the table doesn't produce. Includes per-stage HMW questions (2-4 per stage) embedded at the stage level, not just globally at the end — makes the map workshop-usable phase-by-phase.
- **Section 5.5 (Post-resolution / cyclical):** Expanded to explicitly model cycle-over-cycle dynamics for cyclical journeys. Names whether the experience builds or erodes trust with each repetition, and identifies the cycle-seam re-engagement opportunity.
- **Output format:** Updated to reflect the full stage output structure: header block → touchpoint table → insight cards → per-stage HMWs.

---

## v1.2 — Signal Grounding (2026-03-23)

Skills grounded in real-world data signals across web, news, community, and competitive sources.

### persona-build

- **Step 0 intake expanded:** Now explicitly asks for client-provided audience research files (brand studies, segmentation decks, ICP documents, survey data — anything the client has already done on their audience). Also welcomes community/social data exports, search behavior data, and review site analysis alongside traditional qualitative research
- **Emotional jobs:** When community or review data is available, grounds emotional jobs in actual customer language rather than inferred sentiment. Verbatim phrases from community sources tagged [COMMUNITY VERBATIM] — higher evidentiary weight than composite inferences
- **Social jobs:** Added community affinity lens — what adjacent communities this audience participates in often reveals identity signals that demographic research misses
- **Step 2 (Trigger Events):** Added timing/seasonality dimension — when community or search data is available, surfaces when trigger events peak, not just what they are
- **Step 3 (Decision Factors):** Added switch reasons sourced from community/review data — "I switched because X" patterns are more reliable than survey-stated decision factors
- **Step 4 (Channel Preferences):** Added Research Channels as a distinct dimension — where this persona researches before deciding (Reddit, review platforms, forums, peer networks) vs. where they transact. Company visibility in research channels is a distinct CX consideration from transactional channel design
- **Persona card:** Added "WHERE THEY RESEARCH" section to the standard persona card output

### trend-scan

- **Step 0 intake expanded:** Now explicitly asks for search behavior data (Google Trends exports), news monitoring reports, community/social listening data, and competitive benchmarking as optional signal sources that sharpen implications beyond inference
- **S dimension (PESTLE):** Added community affinity signal — what adjacent communities the target audience participates in, and what values appear in peer discussions
- **Step 2 (Scoring):** Added Signal Validation concept — flags when a trend is Multi-Source Confirmed (analytical signal + search volume + news coverage + community discussion) vs. Analyst-Led (identified analytically but no detectable market signal footprint). Multi-Source Confirmed signals carry higher urgency
- **Step 3 (Trend Radar):** CX implications now include competitor adoption status where known — a trend competitors are already acting on carries different urgency than one everyone is watching

### biz-context

- **Step 0 intake expanded:** Now explicitly welcomes digital and market signal data (website analytics, search trend exports, social listening reports, competitive benchmarking, review site analysis) alongside traditional business documents
- **Domain 2 (Customer Metrics):** Added "Unfiltered Sentiment" sub-dimension — when community or review data is available, compares formal NPS/survey picture against real-world sentiment. Divergence between formal scores and unfiltered sentiment is itself a finding and flagged explicitly
- **Domain 4 (Market Position):** Added "Digital Presence and Competitive Parity" — website clarity, self-service capability, and visibility in customer research channels as market position indicators. Added "Competitive News Velocity" — recent competitor announcements flagged as benchmark-shift signals
- **Summary table:** Now includes a "Key Signal Source" column to surface the evidence basis for each domain health rating
- **Step 2.5 (Cross-Domain Pattern Check):** Added three explicit named patterns: (1) divergence between formal metrics and unfiltered sentiment, (2) messaging-execution gap (brand positioning vs. operational reality), (3) multi-domain deterioration at growth stage

---

## v1.1 — Portfolio Refinement (2026-03-23)

### workshop-prep

- **Removed** — `/workshop-prep` skill and companion `activity-library.md` deleted from the project. Focus narrowed to strategic intelligence, customer understanding, synthesis, and activation (business case + prioritization).
- `setup`, `CLAUDE.md`, and `README.md` updated to reflect 9-skill portfolio.

---

## v1.0 — Initial Release (2026-03-23)

### Process
Ran the full skill-creator evaluation cycle: 20 test cases (2 per skill) across all 10 skills, 6 parallel evaluation agents, grading notes per skill, improvements applied, reinstalled.

---

### All Skills

- **Removed `allowed-tools` from frontmatter** — this attribute is not supported in skill files and was generating warnings across all 10 skills
- **Descriptions made "pushier"** — all descriptions now include explicit trigger contexts (specific phrases, user situations, and proactive trigger conditions) to reduce undertriggering

---

### trend-scan

- Added competitor context to Step 0 intake questions
- Added CX Disruption Potential scoring anchors (1 / 3 / 5 definitions) to prevent arbitrary scores across runs
- Added Tech Waves dimension structure (2-4 signals with same format as PESTLE)
- Added async/batch fallback to Step 2.5 mandatory check-in
- Added guidance for handling user's pre-stated focus area ("I'm mainly thinking about AI")
- Strengthened specificity mandate with a "genericity test" (would this apply to a competitor in a different sector?)
- Added trigger quality guidance to Signals on Watch (concrete triggers only — no "when this becomes mainstream")
- Clarified Section 4 tone: write for a senior leader briefing a steering committee, not for the analyst
- Added no-documents path: proceed with context, mark signals as [INFERRED FROM CONTEXT]

---

### biz-context

- Added no-documents verbal intake path with domain-by-domain question sequence
- Added competitive landscape to Step 0 intake questions
- Added 5th health rating: **Unassessed** (insufficient data — treat as potential risk, not neutral)
- Added mandatory five-row summary table at the top of Section 1 before domain detail
- Added Step 2.5: Cross-Domain Pattern Check — surfaces systemic patterns across domains before tensions
- Added specificity test to Key Tensions: "would this tension apply to any company in any industry?"
- Tightened Step 1.5 data gap check with threshold trigger and stronger check-in template
- Changed "success looks like" prompt to require specific, measurable outcomes with timeframes
- Added explicit pause instruction at Step 0 (was only at Step 1.5 before)

---

### scan-blockers

- Added Severity Rationale column to the blocker table
- Added program history question to Step 0: if running >12 months with minimal progress, ask what was tried
- Added sparse-input hypothesis framing: demonstrate analytical credibility before requesting materials
- Added file-not-found fallback for blocker-taxonomy.md (8 categories listed inline)
- Redefined leverage in Where to Start: upstream blockers that unblock multiple others, not just high severity
- Added blocker compound-system callout after Step 3 grouping
- Added program-window note: distinguish blockers solvable within the program timeline vs. outside it

---

### persona-build

- Added no-research refusal path with three explicit options (desk research / rapid interviews / provisional with all-ASSUMED tags)
- Added social jobs tension-probing instruction (don't accept the most obvious social reading)
- Added channel-behaviour vs. channel-preference distinction to Step 4
- Strengthened Step 6.5 mandatory evidence review with structured summary format (evidenced / inferred / assumed)
- Added evidence quality threshold: if >40% of claims are [ASSUMED], flag as a data quality risk
- Added motivational goal requirement to the Goals section in the persona card output format
- Strengthened Designer's Note with 3-part structure: assumption most likely to be smuggled in, emotional truth data doesn't capture, non-obvious channel implication

---

### journey-map

- Added no-persona handling path: get minimum customer description before mapping; explain why it matters
- Added file-not-found fallback for touchpoint-taxonomy.md (standard channel vocabulary listed inline)
- Added instruction to map absence of touchpoints (silence during waiting stages)
- Added emotion score examples for 1, 2, 4, 5 with calibration note (complaint/claims journeys average 1.5–2.5)
- Strengthened Step 2.5 stage check-in as a hard gate with async/batch protocol
- Added decline/unhappy path requirement: map at least the key touchpoints on the failure outcome
- Strengthened Design Provocations guidance: must challenge assumptions the team will arrive with
- Added Section 5.5: Post-Resolution Implications (relief vs. delight; advocacy vs. churn risk)
- Added backstage constraint note option: flag when customer-facing failures are caused by internal constraints

---

### service-map

- Added journey map dependency note to Step 0: ask for journey map or flag its absence
- Added known failure points handling: if none provided, mark all failure points as Inferred or Hypothesised
- Added Confidence column to Failure Point Register: Confirmed / Inferred / Hypothesised
- Added Frequency column to Handoff Risk Register
- Added provisional blueprint option to Step 0.5: offer assumed-system patterns when user can't provide systems list
- Added backstage specificity example (what a good vs. bad Layer 3 description looks like)
- Added prominence note to Systemic Design Opportunities ordering: customer impact, not ease of implementation

---

### synthesize

- Added theme overlap check before finalizing clusters: merge if two themes share >2 evidence points
- Added non-obvious requirement to theme naming: if everyone already knew it, it's not synthesis
- Added provisional theme marking for document/batch output with explicit confirmation invitation
- Added "genericity test" to tension mapping
- Added strategic leverage definitions for High / Medium / Low HMW ranking
- Added HMW falsifiability test: if any idea could answer the HMW, it's too broad
- Added minimum viable input guidance: at least two distinct evidence source types
- Added purpose-tailored output guidance (workshop brief / board paper / design team brief)
- Added time-dimension quality check for Burning Platform: assert timeframes only with basis
- Strengthened Step 1.5 mandatory theme check-in as a hard gate with document-mode protocol

---

### workshop-prep

- Made Step 0.5 objective confirmation a visible formatted statement in output (auditable in all modes)
- Added time-calibration guidance: 2hr / half-day / full-day / multi-day arc structures
- Added pre-read tone calibration: exec vs. practitioner vs. mixed audiences
- Added Section 8: Post-Session Documentation Plan (who captures what, in what format, by when)
- Added "what if one executive dials in" as a standard watch-out for in-person sessions
- Added energy management note as a required Facilitator Watch-Out item

---

### biz-case

- Strengthened "why now" requirement: must connect to competitive, growth, or regulatory urgency — not just operational trend
- Added alternative comparison requirement to Solution Hypothesis: name the most likely CFO-proposed alternative and why this approach outperforms it
- Added phased commitment option to Implementation Roadmap for high root-cause-uncertainty programs
- Improved Step 4.5 mandatory numbers check template with structured table format
- Clarified output sequence: write all seven sections first, then write executive summary and place it at top
- Added CFO standalone test to executive summary: can a CFO read only the summary and know the full ROI?
- Added regulatory risk prompt for regulated-industry contexts
- Strengthened risk register specificity guidance with generic vs. specific example

---

### prioritize

- Added weight calibration guidance: adjust defaults for growth / cost-reduction / short-horizon contexts
- Added enabling vs. delivering initiative handling: score enabling initiatives on indirect impact they unlock
- Added explicit 6-month test output: name which initiatives produce demonstrable results within the stated time constraint
- Added dependency contingency requirement for large-system programs (CRM, platform migrations)
- Added Section 6: Team Composition Check
- Added deprioritization example to Section 5 to anchor output quality
- Added mandatory scoring review check-in as explicit gate (not just a table)

---

### Infrastructure

- Created `evals/evals.json` — 20 test cases (2 per skill) for future evaluation runs
- Created `kstack-workspace/iteration-1/` — full eval outputs and grading notes from iteration 1
