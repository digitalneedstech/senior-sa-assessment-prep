---
name: case-study-intake
description: Use this skill when the user pastes or uploads a business/technical case study for a Solution Architecture assessment and needs it broken down into a structured problem statement — stakeholders, goals, constraints, NFRs, unknowns, and risks — before questions or architecture work begins.
---

# Case Study Intake & Requirements Extraction

## Purpose
Turn a messy, narrative business case study into a structured architectural brief within the first hour of receiving it — the same discipline a real client engagement demands before you can ask a single good question.

## How to run this skill

When given a case study, produce the following structured output. Do not skip sections even if the case study is silent on them — mark silent areas explicitly as "Not stated — candidate for question list."

### 1. Business Context Summary (3-5 sentences)
Who is the client, what industry, what's the trigger for this initiative (growth, cost pressure, compliance, modernization, M&A, new product)?

### 2. Stakeholder Map
List every explicit and implicit stakeholder with their likely concern:
| Stakeholder | Role | Primary Concern |
|---|---|---|
| e.g. CFO | Sponsor | Cost predictability |
| e.g. Head of Security | Governance | Data residency, compliance |

Always include roles that are usually implicit but matter in assessments: Security/Compliance officer, Operations/SRE, End users, Existing platform team (if migrating), Finance/procurement.

### 3. Business Goals vs. Technical Goals
Separate these explicitly — assessors often plant a business goal that conflicts with an obvious technical shortcut (e.g., "go live in 6 weeks" vs. "must be multi-region HA"). Flag such tensions.

### 4. Functional Requirements (extracted, not invented)
Bullet list, traced back to a phrase in the case study.

### 5. Non-Functional Requirements (NFRs)
Explicitly score what's stated vs. assumed, across:
- Availability / SLA target
- Performance / latency / throughput
- Scalability (users, data volume, growth curve)
- Security & compliance (data classification, regulatory regime — GDPR/HIPAA/PCI/local law)
- Data residency / sovereignty
- Disaster recovery (RTO/RPO)
- Observability & operability
- Cost sensitivity
- Maintainability / team skill constraints

For each, tag: **Stated | Implied | Unstated (must ask)**.

### 6. Constraints
- Budget ceiling (stated or inferable from company size/industry)
- Timeline
- Existing technology landscape / legacy systems to integrate or retire
- Team skills / vendor preferences / cloud provider lock-in signals
- Regulatory/legal constraints

### 7. Assumptions Register (seed list)
Every case study has gaps. List the assumptions you'd need to make to move forward *if you got zero answers to your questions*. This is your fallback list, and later becomes part of your ADRs.

### 8. Ambiguities & Contradictions
Explicitly call out anything in the case study that is vague, missing, or self-contradictory. This is your richest source for the 20-questions phase — hand this list directly to the `twenty-questions-strategist` skill.

### 9. Candidate Architecture Patterns (early hypothesis only)
1-2 sentence gut hypothesis of the likely shape (e.g., "event-driven microservices with CQRS", "modular monolith on managed PaaS", "data platform with lakehouse pattern"). Label clearly as a *hypothesis to validate*, not a decision — a Senior SA should be visibly willing to discard this if answers point elsewhere.

## Output discipline
- Be blunt about gaps — a senior architect is graded on what they *notice is missing*, not just what they can build.
- Keep the whole output scannable (tables, short bullets) — you'll be re-reading this under time pressure.
- End with a one-line "biggest single risk to this engagement" statement — assessors love candidates who can compress to the one thing that matters most.
