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

## External reuse scan: openclaw-mission-control (2026-02-21)
Reference reviewed: `abhi1693/openclaw-mission-control`.

### Reusable capabilities to adopt (reuse, not recreate)
1. **Operations control-plane model**
- Organizations → board groups → boards → tasks/tags as first-class operational objects.
- Useful for turning ad-hoc agent work into governable queued work.

2. **Approval-first governance pattern**
- Explicit approval workflows for sensitive actions.
- Aligns with our compensating-controls direction and audit requirements.

3. **Gateway-aware orchestration surface**
- Dedicated treatment of gateway lifecycle and connected runtime management.
- Relevant to our instability history around gateway state drift.

4. **Health/readiness discipline**
- Clear split for `healthz`/`readyz` style checks and API-first operations.
- Reusable for automated readiness gates before execution.

5. **Auth-mode split for self-hosting**
- Local token mode vs external auth provider mode.
- Useful blueprint for predictable self-host deployments and reduced auth drift.

6. **Installer/bootstrap ergonomics**
- Interactive install flow + env scaffolding + compose defaults.
- Reusable pattern for reducing misconfiguration and onboarding friction.

### Directly relevant to current pain points
- **Configuration drift**: baseline docs emphasize strict required fields and startup validation.
- **Operational noise**: central health and service supervision patterns reduce hidden background failures.
- **Auditability gaps**: activity timeline + approval traces support post-incident reconstruction.

### Adoption plan (incremental)
- **Phase 1 (immediate):** import governance patterns (approval gates, readiness checks, activity evidence format).
- **Phase 2:** map current execution queue/task objects to board/board-group abstractions.
- **Phase 3:** consolidate gateway operations into a single control-plane workflow with explicit state checks.
- **Phase 4:** adopt installer/bootstrap validation patterns for local reliability.

### Non-adoption / caution
- Do not copy repo-specific stack choices blindly (FastAPI/Next/Redis/Postgres) unless they fit our runtime and ops cost constraints.
- Reuse concepts and control patterns first; implement in our existing platform architecture.

## Execution tracking
Detailed execution checklist and acceptance evidence plan:
- `OpenRook/docs/MISSION_CONTROL_REUSE_EXECUTION_CHECKLIST_2026-02-21.md`
