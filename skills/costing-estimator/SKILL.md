---
name: costing-estimator
description: Use this skill when the user needs to produce a rough-order-of-magnitude or detailed cost estimate for a cloud/solution architecture, including cost breakdown by component, cost drivers, and cost-optimization trade-offs, typically to present alongside an architecture diagram in an assessment or client workshop.
---

# Costing & TCO Estimation

## Purpose
Produce a cost narrative that's defensible in real time — assessors rarely expect penny-accurate numbers, but they do expect you to know **what drives cost**, **which levers reduce it**, and **what you traded for what**.

## Step 1 — Establish the cost model shape before any numbers
Break the architecture into cost categories:
- **Compute** (VMs/containers/serverless — usage pattern matters: steady-state vs. spiky)
- **Storage** (hot/cold tiers, data volume growth over time)
- **Data transfer/egress** (often the most underestimated line item — cross-region, cross-cloud, internet egress)
- **Managed services premium** (DB-as-a-service, managed Kafka/queues, managed AI/ML endpoints)
- **AI/ML-specific costs** if relevant: token/inference costs, GPU/accelerator costs for training, vector DB storage
- **Networking** (load balancers, NAT gateways, VPN/interconnect, CDN)
- **Security & governance tooling** (WAF, secrets management, monitoring/observability stack, compliance tooling)
- **Human/operational cost** (ops headcount, managed service premium vs. self-managed trade-off) — mention even if not quantified, it's part of TCO

## Step 2 — Pick your estimation method based on time available
- **Rough Order of Magnitude (ROM)**: use provider pricing calculators with round-number assumptions (e.g., "~500 API req/sec average, autoscaling 3-10 instances") — good enough for workshop-day estimates.
- **Parametric**: cost-per-unit × expected-unit-volume (e.g., cost per 1000 API calls, cost per GB stored) — use when volume is the case study's main variable.
- **Comparative/benchmark**: "similar workloads of this shape typically run $X-Y/month" — use as a sanity check, never as the only method.

## Step 3 — Always present a range, not a false-precision number
State a low/expected/high band and name the swing factors (e.g., "$8k-14k/month; the range depends mainly on data egress volume, which we flagged as an open question").

## Step 4 — Show cost vs. NFR trade-offs explicitly
This is the senior-level differentiator. For at least 2-3 major decisions, show the alternative and its cost delta:
| Decision | Option A | Option B | Cost Delta | Why chosen |
|---|---|---|---|---|
| Compute | Reserved/committed instances | On-demand/serverless | A ~30-40% cheaper at steady load | Predictable baseline load favors reservation |
| DR | Active-passive | Active-active multi-region | B ~1.8-2x cost | Only justify B if RTO/RPO in case study demands it |

## Step 5 — Cost optimization levers to mention proactively (even if not asked)
- Right-sizing / autoscaling policies
- Reserved/committed-use discounts for predictable baseline
- Spot/preemptible instances for fault-tolerant batch workloads
- Storage lifecycle policies (hot → cool → archive tiering)
- Caching/CDN to reduce compute and egress
- Serverless for spiky/low-baseline workloads vs. containers for steady-state
- Multi-tenancy vs. dedicated infra trade-off if applicable

## Tools to actually use live or in prep
- **AWS Pricing Calculator**, **Azure Pricing Calculator**, **Google Cloud Pricing Calculator** — for provider-specific ROM estimates
- **Infracost** — if you have or can sketch Terraform, gives cost diffs per resource
- **Vantage.sh** cost comparison pages — quick cross-provider instance/service comparison
- A simple spreadsheet (see `costing-worksheet-template.md`) is often faster and more presentable live than any tool — panels respond well to a clean, editable table you build in front of them

## Presentation discipline
- Tie every cost line back to a box on the architecture diagram — never present cost as a disconnected number.
- Lead with the total, then break down — don't make them wait through 10 line items to know the headline.
- Be ready to answer "what's the single biggest lever to cut this by 30%?" — always have an answer prepared.
