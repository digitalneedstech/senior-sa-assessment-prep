---
name: competency-self-check
description: Use this skill when the user wants to self-assess or get feedback against Senior Solution Architect competencies — either before the assessment (gap analysis) or after a rehearsal/mock session (scored feedback) — covering technical depth, communication, stakeholder management, business acumen, and leadership signals.
---

# Senior Solution Architect — Competency Self-Check

## Purpose
Assessments for "Senior" (vs. regular) SA levels are rarely graded on technical correctness alone. Use this rubric to self-score honestly, and to ask Claude to score a rehearsal transcript or your described approach against it.

## Competency dimensions (typical for Senior SA bar, adapt to your org's actual rubric if published)

### 1. Business & Commercial Acumen
- Connects every technical recommendation to a business outcome (revenue, risk, cost, speed-to-market), not just technical elegance
- Understands budget/commercial trade-offs (CapEx/OpEx, TCO, not just sticker price)
- Reads between the lines of what the sponsor actually needs vs. what they literally asked for

### 2. Technical Breadth & Depth
- Comfortable across the full stack implied by the case (web/app layer, cloud infra, data, AI/ML if relevant, security, integration)
- Goes deep on the 1-2 hardest parts rather than shallow everywhere
- Current on patterns (event-driven, serverless, well-architected frameworks) without cargo-culting them

### 3. Requirements & Ambiguity Handling
- Extracts the real constraints from a noisy case study
- Asks decision-driving questions, not checklist questions (see `twenty-questions-strategist`)
- Comfortable stating and defending assumptions when information is unavailable

### 4. Trade-off Reasoning & Decision Ownership
- Names alternatives considered, not just the chosen path
- Owns the downside of their own decision unprompted
- Changes position when given new information, without ego

### 5. Communication & Facilitation
- Structures the session (not just answers questions reactively)
- Uses the diagram as a shared artifact, adapts it live
- Explains technical concepts in business language when the audience needs it, and in technical depth when probed

### 6. Risk & Resilience Thinking
- Identifies single points of failure, security gaps, and operational risk unprompted
- Has a coherent DR/HA story mapped to actual stated or reasonably-assumed RTO/RPO
- Thinks about "day 2" operations, not just go-live

### 7. Leadership & Stakeholder Management Signals
- Manages competing stakeholder interests visibly (e.g., security vs. speed, cost vs. reliability) rather than picking one silently
- Demonstrates mentorship/influence framing ("I'd bring the platform team into this decision because...") — Senior SAs are graded partly on organizational maturity, not just personal technical output
- Comfortable saying "I don't know, here's how I'd find out" — confidence without bluffing

## How to use this for self-scoring
For each dimension, score yourself 1-5 against a rehearsal or real past engagement:
1 = Didn't demonstrate / actively weak
3 = Solid, competent, expected-level
5 = Clearly differentiated, senior-level signal

Be honest — the goal is to find your 2-3 lowest-scoring dimensions and deliberately drill them in remaining prep time, not to feel good about the exercise.

## Prompting Claude for feedback
After a rehearsal (paste your responses, or a transcript, or describe your approach to a scenario), ask:

> "Score my response against the 7 Senior SA competency dimensions in this rubric, 1-5 each, with one specific piece of evidence for each score and one specific suggestion to move it up a point."

Push for specificity — reject vague praise ("good job") and insist on evidence-linked scoring, the same way a real calibrated panel would.

## Common reasons candidates get scored "SA" instead of "Senior SA" (watch for these)
- Jumps to solutioning before fully interrogating the problem
- Technically correct but can't connect decisions to business impact
- Defends decisions defensively instead of provisionally
- Misses second-order risks (operational, organizational) while nailing first-order technical design
- Doesn't visibly manage the room/session — answers questions but doesn't facilitate
