---
name: workshop-facilitator
description: Use this skill when the user is rehearsing for or actively running a live solution architecture assessment workshop — needs help structuring the session, generating likely panel questions/scenarios/curveballs, practicing trade-off defense under pressure, or role-playing as a skeptical stakeholder panel.
---

# Workshop Facilitation (Assessment Day)

## Purpose
The live workshop is where "knowing the answer" is separated from "running the room like a Senior SA." This skill covers both: (1) how to structure and facilitate the session yourself, and (2) how to use Claude as a rehearsal partner/panel simulator beforehand.

## Part A — Structuring the workshop you run

### Suggested flow (adapt to time given, typically 45-90 min)
1. **Opening framing (2-3 min)** — restate the business problem in your own words, confirm scope/out-of-scope, state your key assumptions out loud and ask for correction. This anchors the whole session and shows you didn't just memorize the case study.
2. **Present v1 architecture at Context level (5 min)** — zoomed out, narrate the "why," invite immediate reaction before going deeper.
3. **Drill into 2-3 hardest decisions (15-20 min)** — don't walk every box; pick your riskiest/most interesting decisions and go deep, using the ADR technique from `adr-trade-off`.
4. **Scenario stress-testing (15-20 min)** — invite or propose "what if" scenarios (traffic spike, region outage, compliance audit, new integration) and reason live through how the architecture responds.
5. **Live refinement (10-15 min)** — visibly update the diagram based on panel input (see `architecture-diagramming` discipline).
6. **Costing walkthrough (5-10 min)** — present the cost band tied to the refined diagram, name the top optimization lever.
7. **Close (2-3 min)** — summarize key decisions, open risks, and next steps if this were a real engagement. Ending with "if I had another week, I'd validate X" shows self-awareness.

### Facilitation behaviors that read as "senior," not just "correct"
- Ask clarifying questions back to the panel before answering ambiguous scenario prompts — real SAs don't guess at requirements.
- Use the whiteboard/diagram as the shared object of discussion — point at it, update it, don't just talk over it.
- Time-box yourself out loud ("let's park that and come back if we have time") — signals facilitation skill, not just technical knowledge.
- When you don't know something, say what you'd do to find out (spike, POC, ask a specialist) rather than bluffing.
- Summarize periodically in your own words what's been agreed — a real facilitator checks understanding continuously.

## Part B — Using Claude to rehearse beforehand

Ask Claude to role-play the assessment panel. Effective prompts:

> "Act as a skeptical panel of a CTO, a security lead, and a cost-conscious CFO. I'll present my architecture for [case study]. Interrupt me with challenging questions the way a real assessment panel would — mix technical depth, business-impact, and 'what if this fails' scenarios. Don't go easy on me."

> "Give me 10 curveball scenarios for this architecture — things like sudden 10x traffic, a key vendor going down, a new compliance requirement mid-project, a stakeholder demanding a cheaper option. I'll respond to each and you critique my answer like a Senior SA assessor would."

> "I'm about to defend [specific decision]. Play devil's advocate as hard as you can for the alternative, then tell me honestly whether my defense held up."

### Categories of curveballs to specifically request/expect
- **Scale shock**: sudden multiplier on load, users, or data volume
- **Failure injection**: a specific component goes down — what's the blast radius, what's the user-facing impact
- **Compliance/regulatory change mid-flight**
- **Budget cut**: "the CFO just halved the budget — what do you cut first and why?"
- **Team constraint**: "you lose your platform team, ops now sits with 2 generalists — does your design still hold?"
- **Vendor/technology reversal**: "the CIO has a strong existing relationship with [alternate cloud/vendor] — how does that change your recommendation?"
- **Timeline compression**: "leadership wants this live in half the time — what's your phased/MVP cut?"

## Part C — Self-rehearsal checklist before the real day
- Can I state my architecture's single biggest risk unprompted?
- Can I defend my 3 riskiest decisions using the ADR technique without notes?
- Do I have a cost range memorized (not exact figures, but the band and its main driver)?
- Have I rehearsed at least one "I don't know, here's how I'd find out" answer?
- Can I redraw my context diagram from memory in under 2 minutes?
