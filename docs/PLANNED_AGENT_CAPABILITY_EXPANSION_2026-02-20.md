# Planned Agent Capability Expansion (Public, 2026-02-20)

This note summarizes upcoming capability direction at a **what-level** (not sensitive implementation detail).

## Priority expansion areas

1. **Proactive objective execution**
- Agents work from explicit objectives and milestones, not only reactive prompts.
- Progress is tracked with auditable completion evidence.

2. **Structured inter-agent collaboration**
- Standardized assist lifecycle between agents (request, acknowledgement, progress, result).
- Better handoff quality and reduced context loss.

3. **Operational memory maturity**
- Tiered memory model for short-term context, active-work memory, and durable knowledge.
- Confidence/freshness-aware reuse to reduce stale-decision risk.

4. **Model-runtime queue governance**
- Fair and observable local-model access under multi-agent load.
- Priority-aware scheduling with anti-starvation behavior.

5. **Learning-to-capability promotion**
- Validated lessons promoted into reusable checks, playbooks, and role-specific patterns.
- Measurable quality and reliability gains over time.

6. **Reliability and recovery assurance**
- Regular readiness checks, drift detection, and restore rehearsals.
- Emphasis on low-friction operations with strong guardrails.

## Public boundary
OpenRook publishes **capability intent and governance patterns** only.
It does not publish secrets, private infrastructure details, or exploitable internals.
