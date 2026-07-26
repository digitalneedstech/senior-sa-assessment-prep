---
name: architecture-diagramming
description: Use this skill when the user needs to design, structure, describe, or critique a solution architecture diagram (context/container/component views, C4 model, cloud reference architecture) ahead of or during a live architecture workshop.
---

# Architecture Diagramming

## Purpose
Get you to a diagram that survives live questioning — not just one that looks good, but one where every box and arrow has a reason you can defend on the spot.

## Layered approach (use C4-style thinking even if you don't draw it literally)

**Level 1 — System Context**: your system as one box, surrounded by actors (users, admin, external systems). This is what you show first in the workshop — always start zoomed out.

**Level 2 — Container view**: the major deployable/runtime units (web app, API layer, services, databases, queues, third-party integrations, batch/AI pipeline if relevant). Show synchronous vs. asynchronous flows differently (solid vs. dashed arrows).

**Level 3 — Component view** (only for the 1-2 most architecturally interesting containers): internal structure — this is where you demonstrate depth, so pick the container with the hardest trade-off (e.g., the event-driven core, the AI inference path, the multi-tenant data layer) rather than a trivial one.

**Level 4 — Deployment/infrastructure view**: map containers to actual cloud services (region, AZ layout, network boundaries — VPC/VNet, subnets, security groups), and to the NFRs they satisfy (HA, DR, scaling).

## What a senior-level diagram must show that a mid-level one often skips
- **Trust boundaries / security zones** (public internet, DMZ, private subnet, data zone) — draw these as explicit boxes, not implied.
- **Data flow direction and data classification** (PII, sensitive, public) at least at a high level.
- **Failure/resilience posture** — where's the redundancy, what's the DR strategy, what's the blast radius of each component failing.
- **Scaling mechanism per component** — not just "it scales," but how (horizontal autoscaling, read replicas, sharding, queue-based leveling).
- **Integration contracts** — label arrows with protocol/pattern (REST, gRPC, event, batch/ETL, webhook) not just a plain line.
- **Cost-relevant boundaries** — components that are usage-billed vs. fixed-cost, since this feeds the costing skill directly.
- If AI/ML is involved: separate the **inference path** (latency-sensitive, often synchronous) from the **training/fine-tuning path** (batch, resource-heavy), and show where human review/guardrails sit if relevant.

## Workshop diagramming discipline
- Start with a deliberately incomplete v1 (from your pre-work) and **visibly evolve it live** as the panel gives input — this is what they're actually assessing, not the polish of your pre-drawn diagram.
- Narrate while you draw: state the decision, the alternative you rejected, and why, as you add each element.
- Keep a "parking lot" area on the board for things raised that you're deliberately deferring — shows prioritization skill instead of scope creep.
- When challenged, be willing to redraw a box rather than defend a sunk-cost design — the panel is often testing for flexibility, not just for round 1 quality.

## Notation conventions to stay consistent with
- Rectangles = deployable units/services. Cylinders = data stores. Diamonds/hexagons = external actors or systems. Solid arrows = synchronous calls. Dashed arrows = async/event-driven.
- Color-code by concern if your tool supports it (e.g., blue = compute, green = data, orange = external/third-party, red-outline = security-sensitive boundary).
- Always include a small legend if the diagram will be viewed without narration.

## Self-check before presenting
- Can I trace every functional requirement to at least one component?
- Can I trace every NFR to a specific design decision visible on the diagram (not just asserted in prose)?
- Is there a single point of failure I haven't acknowledged?
- Have I shown, not just claimed, how this scales and recovers?
