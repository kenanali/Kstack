# KStack — CX Transformation Skill System

KStack is a set of Claude Code slash-command skills for CX transformation and innovation work. Each skill encodes a distinct expert cognitive mode — the way a senior service designer, organizational consultant, strategic synthesizer, or workshop facilitator actually thinks — rather than a generic AI assistant mode.

## The Four-Phase Workflow

```
PHASE 1: INTELLIGENCE          PHASE 2: CUSTOMER UNDERSTANDING
  /trend-scan                    /persona-build
  /biz-context                   /journey-map
  /scan-blockers                 /service-map
       │                               │
       └──────────── both feed ────────┘
                          │
                    PHASE 3: SYNTHESIS
                      /synthesize
                          │
                    PHASE 4: ACTIVATION
                      /biz-case
                      /prioritize
```

## Skills

| Skill | Mode | What it produces |
|---|---|---|
| `/trend-scan` | Macro trend intelligence | Trend radar with CX implications |
| `/biz-context` | Business performance analysis | Situation analysis + key tensions |
| `/scan-blockers` | Organizational blocker detection | Blocker map with severity + addressability |
| `/persona-build` | Customer persona architecture | Rich persona with JTBD + emotional drivers |
| `/journey-map` | Customer journey mapping | Full journey map with emotional arc + opportunities |
| `/service-map` | Service blueprint | 5-layer blueprint with failure points |
| `/synthesize` | Strategic synthesis | Insight clusters + tensions + HMW opportunities |
| `/biz-case` | Business case building | Executive-ready 7-section business case |
| `/prioritize` | Initiative prioritization | Scored portfolio with sequencing recommendation |
| `/brand-building-blocks` | Brand research synthesis | 5-8 named building blocks across Audience, Company, Moment |
| `/brand-territories` | Brand territory exploration | 3 distinct territory directions with "What if we..." scenarios |
| `/name-check` | Naming strategist + clearance analyst | Name generation from creative brief + multi-source clearance sweep (trademark, app stores, domains, social handles, web presence) with interactive refinement loop |

## How Skills Chain

- `/synthesize` is designed to consume outputs from Phase 1 and Phase 2 skills. Paste or upload the outputs of `/trend-scan`, `/biz-context`, `/scan-blockers`, `/journey-map`, and/or `/service-map` into the `/synthesize` session.
- `/biz-case` is designed to consume outputs from `/biz-context`, `/scan-blockers`, and `/synthesize`.
- `/prioritize` is designed to consume a list of initiatives, which can come from `/synthesize` or `/biz-case` outputs.
- `/journey-map` is designed to consume output from `/persona-build`.
- `/brand-building-blocks` is designed to consume outputs from `/persona-build` (Audience force), `/biz-context` (Company force), and `/trend-scan` (Moment force).
- `/brand-territories` is designed to consume output from `/brand-building-blocks`.
- `/name-check` can consume output from `/brand-territories` (for naming direction) but can also run standalone with a freeform creative brief. Feeds into legal trademark review and final name decision.

## Input Conventions

- **Paste text directly** into the chat for short content (notes, quotes, bullet summaries).
- **Upload documents** (PDF, Word, decks) for long-form research reports, transcripts, NPS data, financial summaries. After uploading, reference the document by name and the skill will read it.
- **Describe context verbally** when you don't have a document — the skill will ask structured intake questions.

## Output Conventions

All skill outputs are structured markdown designed to be copy-pasted directly into:
- Presentations and decks (Keynote, Google Slides, PowerPoint)
- Notion / Confluence pages
- Word documents or PDFs
- Future skill inputs (chain the outputs)

## Installation

```bash
./setup
```

This installs all skills into `~/.claude/skills/` so they're available as slash commands in any Claude Code session.

## Project Structure

```
KStack/
├── CLAUDE.md                         ← this file
├── package.json
├── setup                             ← install script
│
├── trend-scan/SKILL.md
├── biz-context/SKILL.md
├── scan-blockers/
│   ├── SKILL.md
│   └── blocker-taxonomy.md
├── persona-build/SKILL.md
├── journey-map/
│   ├── SKILL.md
│   └── touchpoint-taxonomy.md
├── service-map/SKILL.md
├── synthesize/SKILL.md
├── biz-case/
│   ├── SKILL.md
│   └── value-driver-library.md
├── prioritize/SKILL.md
├── brand-building-blocks/SKILL.md
├── brand-territories/SKILL.md
└── name-check/SKILL.md
```
