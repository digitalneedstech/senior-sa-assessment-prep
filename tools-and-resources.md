# Tools & Resources

## Whiteboarding / live diagramming (for the workshop itself)
- **Miro / Mural** — best for a live, collaborative, panel-facing workshop; good for parking-lot areas and sticky-note-style scenario capture.
- **draw.io / diagrams.net** — free, fast, has AWS/Azure/GCP shape libraries built in; good balance of speed and polish, works offline too.
- **Excalidraw** — fastest for a rough, hand-drawn-feel live sketch that visibly evolves — useful if you want to look like you're genuinely thinking live rather than presenting a finished asset.
- **Lucidchart** — more polished, better for a pre-built v1 diagram you bring in, less ideal for fast live edits.
- **Mermaid / PlantUML** (text-to-diagram) — useful in prep if you're comfortable with Claude generating/updating diagrams as code; less ideal live in front of a panel unless you're fast with the syntax.

## Architecture modeling frameworks worth referencing by name
- **C4 Model** (Context, Container, Component, Code) — the structure this kit's diagramming skill is built around; naming it explicitly in the workshop signals structured thinking.
- **AWS/Azure/GCP Well-Architected Frameworks** — reference the relevant pillars (reliability, security, cost optimization, performance, operational excellence, sustainability) when justifying decisions — assessors recognize this vocabulary.
- **TOGAF ADM** — useful vocabulary (Business/Data/Application/Technology architecture layers) if your org's assessment leans enterprise-architecture-flavored.

## Costing tools
- **AWS Pricing Calculator**, **Azure Pricing Calculator**, **Google Cloud Pricing Calculator** — official ROM estimators, fastest credible source in a time-boxed prep window.
- **Infracost** — cost estimates directly from Terraform if you have/can sketch IaC.
- **Vantage.sh** — quick cross-provider instance/service price comparisons.
- A clean spreadsheet (see `templates/costing-worksheet-template.md`) — often the most presentable live artifact; a panel can follow a table faster than a calculator screen-share.

## Decision-record & documentation
- **ADR format** (this kit's `adr-trade-off` skill) — lightweight, half-page-per-decision, widely recognized format.
- **Notion / Confluence** — if you want a polished, shareable version of your case-study-intake and ADR outputs post-workshop.

## AI-assisted prep
- Use **Claude** itself (via this skills kit) as your:
  - case study analyzer (`case-study-intake`)
  - question-list co-author and prioritizer (`twenty-questions-strategist`)
  - rehearsal panel / devil's advocate (`workshop-facilitator`)
  - cost-model sanity checker (`costing-estimator`)
- If available in your environment, Claude's diagram/artifact generation can produce a first-draft SVG/HTML architecture diagram in seconds to seed your manual refinement — useful for the pre-workshop v1, not for live panel drawing (do that live, by hand, on the whiteboard tool, so the panel sees you think).

## General reading worth a refresher pass (not required, but commonly assumed knowledge at Senior SA level)
- AWS/Azure/GCP Well-Architected Framework whitepapers (skim the pillar summaries, not full depth)
- Martin Fowler's writing on microservices trade-offs and the "monolith first" argument
- Basics of event-driven architecture patterns (choreography vs. orchestration, outbox pattern, CQRS at a conceptual level)
- If AI is in scope: RAG vs. fine-tuning trade-offs, and basic LLM cost/latency mental model (tokens, context window, inference vs. training cost)
