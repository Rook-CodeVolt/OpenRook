# OpenRook Roadmap

This roadmap is intentionally practical and operator-oriented.

## Phase 1 — Publish and baseline (Now)
- [x] Public overview of implementation improvements
- [x] Agent role breakdown and scope
- [x] Before/after improvement matrix
- [x] Unified proactive model published (`docs/strategy/PROACTIVE_AGENT_MODEL_V1_PUBLIC.md`)
- [ ] Add examples of safe automation boundaries
- [ ] Add baseline observability checklist for adopters

## Phase 2 — Operational playbooks
- [ ] Agent trigger matrix (incident, drift, maintenance, research)
- [ ] Escalation policy examples (risk-tiered automation)
- [ ] Budget and concurrency control templates
- [ ] Continuous-improvement loop template (learn → codify → reuse)


## Phase 2.5 — Proactive autonomy and managed learning
- [~] Autonomous skill development system (idle-to-training + validation gates) — in active implementation
- [~] Define proactive agent operating contract (from reactive-only to mixed proactive/reactive) — in progress
- [~] Implement managed self-learning lifecycle (observe → codify → validate → reuse) — in progress
- [~] Add read-only web research policy with allowlisted sources per agent role — initial controls in place
- [ ] Add autonomy risk tiers and approval gates for non-trivial actions
- [~] Add per-agent budget/concurrency governors for local-model efficiency — in progress

## Phase 3 — Community adoption support
- [ ] Example deployment blueprints (small team / larger team)
- [ ] Starter governance profile for production-like use
- [ ] Contribution-driven role and policy refinements

## Phase 3.5 — Collaboration, memory, and queue governance
- [ ] Publish inter-agent communication lifecycle (public protocol view)
- [ ] Publish tiered memory model (episode / working / durable knowledge)
- [ ] Publish confidence/freshness memory governance guidance
- [ ] Publish local-model queue governance and fairness guidance
- [ ] Publish collaboration KPI starter set (assist latency/success/risk-prevention)

## Non-goals
- Publishing secrets, sensitive infrastructure details, or exploit-level implementation specifics.
