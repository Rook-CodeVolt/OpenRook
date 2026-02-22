# Specialization-First Proactive Learning Direction — 2026-02-22

## Direction update
OpenRook is moving from generic, activity-led learning toward **specialization-first proactive learning**.

Core principle:
- Agents must not drift into generalized behavior.
- Each agent should deepen role-specific capability and proactively identify learning needs relevant to its specialization.

## Target operating behavior
Agents should explicitly reason:
- "This signal/task/failure pattern is relevant to my specialization."
- "I need to learn/improve this capability."
- "I will propose and execute a validated learning loop with measurable impact."

This changes agent posture from primarily reactive to proactively specialist.

## Implementation direction
1. **Role specialization charters for all active agents**
   - Define role domains, adjacent domains, and boundaries.
   - Define required evidence for skill promotion per role.

2. **Specialization relevance trigger in runtime loops**
   - Classify work/events as role-relevant, adjacent, or out-of-scope.
   - Auto-create learning objectives when relevant gaps are detected.

3. **Self-initiated learning objective flow**
   - Agent-generated learning tasks include hypothesis, expected impact, validation method, and promotion gate.

4. **Specialization-weighted skill accounting**
   - Prioritize role-aligned skill growth; cap generic-only skill inflation.

5. **Role-specific validation gates**
   - Skill promotion requires passing role-specific checks (not just task completion).

6. **Specialization mastery observability**
   - Dashboard should show per-agent specialization map, covered/uncovered critical skill areas, and self-initiated learning count.

## Example focus areas
- **sentinel-2.0:** prompt injection detection, AI misuse patterns, trust-boundary anomalies, threat triage quality.
- **api-1:** contract validation, auth/authz robustness, version compatibility, failure-mode and resilience diagnostics.
- **data-1:** schema drift, data integrity/lineage, evidence fidelity.
- **validator-2.0:** acceptance criteria rigor, false-green prevention.
- **builder-2.0:** reliability-centric implementation patterns and regression containment.

## Governance note
Success is defined by:
- measurable specialization depth,
- validated role-relevant capability gains,
- reduced boundary drift,
- and sustained proactive learning behavior.

This update is public-safe and excludes sensitive infrastructure details.
