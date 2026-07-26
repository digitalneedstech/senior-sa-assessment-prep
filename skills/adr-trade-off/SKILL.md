---
name: adr-trade-off
description: Use this skill when the user needs to document, articulate, or defend an architecture decision and its trade-offs (Architecture Decision Records), or when preparing likely "why did you choose X over Y" defenses ahead of a solution architecture assessment workshop.
---

# Architecture Decision Records (ADR) & Trade-off Articulation

## Purpose
Senior-level assessments rarely fail candidates for picking the "wrong" technology — they fail candidates who can't articulate *why* they picked it and *what they gave up*. This skill builds that muscle and produces artifacts you can literally hand across the table.

## ADR format to use (keep it lightweight — 1 per major decision, half a page each)

```
## ADR-<n>: <short decision title>

**Status:** Proposed (pre-workshop) / Confirmed (post-workshop)

**Context:** What forces are at play — business goal, constraint, NFR — that make this decision necessary?

**Decision:** What did you choose, stated in one clear sentence.

**Alternatives considered:**
- Option A — pros / cons
- Option B — pros / cons

**Consequences:**
- What you gain
- What you give up / new risk introduced
- What this decision constrains for the future (lock-in, coupling)

**Revisit trigger:** What future condition would make you reconsider this decision?
```

## Pre-build ADRs for the decisions almost every assessment probes
Draft these ahead of time in skeleton form, then fill in specifics once you know the case study:

1. **Monolith vs. microservices / modular monolith** — justify by team size, deployment cadence needs, and actual coupling in the domain, not by trend.
2. **Synchronous vs. event-driven communication** between core components.
3. **SQL vs. NoSQL / polyglot persistence** — justify by access patterns and consistency needs, not by familiarity.
4. **Build vs. buy** for any non-differentiating capability (auth, search, notifications, payments).
5. **Single cloud vs. multi-cloud vs. cloud-agnostic** — almost always justify single-cloud unless the case study explicitly demands portability/regulatory multi-cloud; multi-cloud "for flexibility" alone is a weak, commonly-flagged answer.
6. **Managed service vs. self-hosted** for data stores, queues, orchestration.
7. **Active-active vs. active-passive DR**, and how it maps to stated/assumed RTO-RPO.
8. **Centralized vs. federated data platform**, if data is a major theme.
9. **API gateway/BFF pattern vs. direct client-to-service calls.**
10. If AI is involved: **build/fine-tune vs. use foundation model API**, and **RAG vs. fine-tuning vs. prompt engineering** for grounding — justify by data freshness needs, cost, and latency, not novelty.

## How to defend a decision live (the actual technique)
When challenged with "why not X instead?":
1. **Acknowledge X's merit first** — "X would genuinely be the better choice if [condition]..."
2. **State the specific condition in this case study that tips it the other way** — tie back to a stated requirement, not a general preference.
3. **Name the cost of your choice honestly** — don't pretend your decision is free of trade-offs; naming the trade-off yourself is more credible than having it extracted from you.
4. **Name the revisit trigger** — "if [X] changes, I'd revisit this."

This is the single highest-signal behavior in a Senior SA assessment: showing you hold decisions provisionally, backed by reasoning, not as personal preferences to be defended at all costs.

## Anti-patterns to avoid saying out loud
- "Because it's industry standard / everyone uses it" (no reasoning)
- "Because it's more scalable" without specifying the scale dimension and target
- "Because it's more secure" without naming the specific threat it mitigates
- Defending a choice by attacking the alternative rather than justifying your own on the stated requirements
