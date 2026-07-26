---
name: twenty-questions-strategist
description: Use this skill when the user needs to draft, prioritize, or trim a fixed-size list (e.g. 20) of clarifying questions to email before a solution architecture assessment or workshop, and wants to make sure every question is a genuine decision-driver rather than a generic checklist item.
---

# 20-Questions Strategist

## Purpose
You get exactly 20 questions, asked once, answered asynchronously, with no follow-up. Every question must earn its place by changing what you *build* or how you *approach* the workshop. This skill turns your ambiguity list (from `case-study-intake`) into a ranked, deduplicated, high-leverage question set.

## The core test for every candidate question
Before a question makes the final 20, it must pass:
> **"If I get either possible answer to this, does my architecture, approach, or risk posture actually change?"**

If the answer is the same regardless of their response, cut it. If you could reasonably default/assume the answer without materially changing your design, cut it — note it in your Assumptions Register instead.

## Question categories to sweep (don't let all 20 cluster in one area)
Assessors design case studies with deliberate gaps across categories. Aim for coverage, weighted toward whichever categories the case study left vaguest:

1. **Business/strategic intent** — what does success look like in 12/24 months? What's the real driver behind this initiative?
2. **Scale & growth** — current vs. projected users/data/transactions; growth curve shape (linear vs. spiky vs. seasonal)
3. **NFRs that weren't stated** — availability target, RTO/RPO, latency SLAs
4. **Compliance/regulatory/data residency**
5. **Existing landscape** — legacy systems to integrate, retire, or coexist with; technical debt
6. **Team & operating model** — in-house vs. outsourced ops, skill sets, DevOps maturity, on-call model
7. **Budget & commercial constraints** — CapEx vs. OpEx preference, existing vendor contracts/discounts, cloud provider preference or lock-in
8. **Timeline & phased delivery appetite** — big-bang vs. incremental, MVP definition
9. **Security posture** — existing IAM/identity provider, threat model concerns, data classification
10. **Integration boundaries** — what's in scope vs. explicitly out of scope; third-party/partner systems

## Prioritization method
1. Draft freely — aim for 30-35 raw candidate questions from your ambiguity list.
2. Score each 1-3 on: **Decision Impact** (does it change the architecture) × **Blast Radius** (how many downstream decisions depend on it) × **Unknowability** (could you make a defensible assumption instead?).
3. Rank by combined score. Take the top ~16-17.
4. Reserve 3-4 slots deliberately for **trap-detection questions** — ones that surface contradictions you noticed in the case study (e.g., "The brief mentions both a 6-week go-live and a full multi-region DR requirement — which takes priority if they conflict?"). These signal seniority: you're not just collecting facts, you're testing the coherence of the ask itself.
5. Sequence the final list logically: business context → scale/NFRs → compliance → existing landscape → team/ops → budget/timeline. A well-ordered question list itself signals structured thinking to whoever reads your email.

## Writing style for the actual email
- One question per line, numbered, no compound questions ("what's your DR requirement and who owns ops" is two questions — split or cut one).
- Precise and closed enough to get an answerable response, but not so closed you can't learn anything (avoid pure yes/no unless that's genuinely all you need).
- No jargon overload — write like you're talking to a business sponsor who will forward this to multiple technical/business people.
- Group with subheadings (Business / Scale & NFRs / Compliance / Landscape / Delivery & Budget) so it reads as structured thinking, not a brain-dump.

## Output format for this skill
Produce:
1. The ranked shortlist of 20 (grouped under subheadings, numbered 1-20)
2. A short "why this made the cut" note for the 3-4 trap-detection questions specifically
3. The 10-15 cut questions moved into an **Assumptions Register** with your default assumption for each — so nothing is lost, it's just resolved by assumption instead of by asking
