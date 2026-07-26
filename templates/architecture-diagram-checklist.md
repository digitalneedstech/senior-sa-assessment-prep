# Architecture Diagram Checklist

## Coverage
- [ ] System context view (actors + system as one box)
- [ ] Container view (major runtime/deployable units)
- [ ] Component view for the 1-2 hardest containers
- [ ] Deployment/infra view (region, AZ, network boundaries)

## Senior-level signals
- [ ] Trust boundaries / security zones explicit
- [ ] Data flow direction + rough data classification shown
- [ ] Redundancy / failure domains visible
- [ ] Scaling mechanism labeled per component (not just "scales")
- [ ] Integration arrows labeled with protocol/pattern
- [ ] Cost-relevant boundaries identifiable (usage-billed vs fixed)
- [ ] (If AI/ML) inference path separated from training/fine-tuning path

## Traceability
- [ ] Every functional requirement traces to at least one component
- [ ] Every NFR traces to a specific visible design decision
- [ ] No unacknowledged single point of failure
- [ ] Scaling and recovery are shown, not just claimed

## Notation consistency
- [ ] Legend included if diagram will be viewed without narration
- [ ] Consistent shape conventions (rectangle=service, cylinder=data store, dashed=async)
- [ ] Consistent color coding by concern
