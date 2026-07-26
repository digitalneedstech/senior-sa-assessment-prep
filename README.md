# Senior Solution Architect — Assessment Prep Kit

This is a Claude Skills package built around the actual lifecycle of your assessment:

```
Case Study Received (Day 0)
   ↓
[Skill: case-study-intake]        → structured understanding of the business/technical problem
   ↓
[Skill: twenty-questions-strategist] → craft & prioritize your 20 email questions
   ↓
Answers arrive → you strategize your approach (Day 1-3)
   ↓
[Skill: architecture-diagramming]  → draft v1 architecture before the workshop
[Skill: costing-estimator]        → rough-order-of-magnitude cost model
[Skill: adr-trade-off]            → pre-empt trade-offs you'll be probed on
   ↓
ASSESSMENT DAY — live workshop
[Skill: workshop-facilitator]     → run it like a real SA-led workshop
   ↓
Refine diagram + costing live, present final architecture
   ↓
[Skill: competency-self-check]    → self-grade against Senior SA competencies
```

## What's inside

```
senior-sa-assessment-prep/
├── README.md                          (this file)
├── skills/
│   ├── case-study-intake/SKILL.md
│   ├── twenty-questions-strategist/SKILL.md
│   ├── architecture-diagramming/SKILL.md
│   ├── costing-estimator/SKILL.md
│   ├── adr-trade-off/SKILL.md
│   ├── workshop-facilitator/SKILL.md
│   └── competency-self-check/SKILL.md
├── templates/
│   ├── case-study-analysis-template.md
│   ├── 20-questions-email-template.md
│   ├── workshop-agenda-template.md
│   ├── adr-template.md
│   ├── architecture-diagram-checklist.md
│   └── costing-worksheet-template.md
└── tools-and-resources.md             (tooling for whiteboarding, diagramming, costing)
```

## How to use this with Claude

**Claude.ai / Claude Desktop / Cowork (Skills feature):**
Zip the `skills/` folder contents (or the whole project) and upload it as a Skill/Capability if your workspace has Skills enabled under Settings. Claude will auto-load the relevant `SKILL.md` when your conversation matches its trigger conditions (e.g., paste your case study and the `case-study-intake` skill activates).

**Claude Code / Claude Cowork (as a project):**
Drop this whole folder into your project directory. Reference skills directly, e.g.:
> "Use the case-study-intake skill on this business case: [paste case study]"

**Any other LLM tool:**
These are plain markdown files — copy-paste the relevant `SKILL.md` content as a system/context prompt, or feed the whole file as an attachment when you start that phase of prep.

## Suggested prep sequence (your 3 days)

| Day | Activity | Skill/Template to use |
|---|---|---|
| Day 0 (case study received) | Deep-read, extract entities, goals, constraints | `case-study-intake` + `case-study-analysis-template.md` |
| Day 0 (same day, email due) | Draft, rank, and finalize your 20 questions | `twenty-questions-strategist` + `20-questions-email-template.md` |
| Day 1 (answers arrive) | Re-baseline assumptions, pick your architecture pattern | `case-study-intake` (revisit) + `adr-trade-off` |
| Day 1-2 | Draft architecture v1 (context, container, component views) | `architecture-diagramming` + `architecture-diagram-checklist.md` |
| Day 2 | Build a rough cost model | `costing-estimator` + `costing-worksheet-template.md` |
| Day 2-3 | Pressure-test: rehearse being asked "why", "what if", "what breaks" | `workshop-facilitator` (use it against yourself) |
| Day 3 / pre-assessment | Dry run, agenda, opening statement | `workshop-facilitator` + `workshop-agenda-template.md` |
| Assessment day | Live workshop, live diagram/costing refinement | all of the above, in real time |
| Post-assessment | Reflect and identify growth areas | `competency-self-check` |

Good luck — treat this like a real engagement, not an exam. That mindset alone is most of what separates "SA" from "Senior SA."
