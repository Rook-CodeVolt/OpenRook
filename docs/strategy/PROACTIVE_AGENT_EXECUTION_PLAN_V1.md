# Proactive Agent Execution Plan v1 (Public Summary)

This document describes **what** OpenRook is implementing to move from reactive assistance to proactive, continuously improving agent operations.

> Public-safe by design: this explains operating model, governance, and outcomes, without exposing sensitive internals.

## 1) Objectives

- Run agents as proactive operators, not request-only responders.
- Keep operations local-model-first to reduce external model spend.
- Improve agent competency over time through managed learning loops.
- Maintain safety via risk tiers, approval gates, and auditability.
- Prove value through measurable dashboard evidence.

## 2) Operating model

### 2.0 Inter-agent communication layer (mandatory)
A managed communication layer is required between active agents so handoffs are explicit, auditable, and role-aligned.

Required capabilities:
- structured handoff packets (objective, context, constraints, risk, expected output),
- role-aware routing (pass to best-fit agent when out-of-scope),
- ownership transfer tracking (who owns delivery at each stage),
- discussion trace for relevant inter-agent reasoning,
- escalation path when no suitable role is available.

This prevents dropped work and ensures "not my task" results in managed delegation, not dead ends.

### 2.1 Work lanes
- **Hot lane:** incidents/security/high-priority reliability issues.
- **Warm lane:** routine maintenance and operational drift correction.
- **Cold lane:** optimisation, learning, and continuous improvement tasks.

### 2.2 Trigger model
- **Event-driven triggers** (preferred): failures, anomalies, drift, state transitions.
- **Scheduled triggers** (fallback): periodic health and posture checks.
- **Human-triggered overrides** for exceptional handling.

### 2.3 Role-fit routing
Tasks are routed by role suitability. Agents must hand off proactively when another role is better aligned.

## 3) Local-model-first policy

- Default execution target for autonomous agent work: **local LM Studio models**.
- External model usage is treated as escalation and requires explicit policy conditions.
- Model usage decisions are logged at outcome level for review.

## 4) Skill-gap governance (extend vs create new agent)

When a capability gap is detected, OpenRook follows a standard decision process:
1. Classify the gap (impact, recurrence, urgency, domain).
2. Attempt closure using existing agents (skills, routing, pairing, playbooks).
3. Create a new agent only when the gap is persistent, distinct, and economically justified.
4. Record decision rationale and planned evidence.

## 5) Continuous learning loop

Every closed task/incident feeds an improvement loop:
1. Outcome capture
2. Insight extraction
3. Promotion into reusable artefacts (skills/rules/playbooks)
4. Validation against future occurrences
5. Keep/refine/retire decisions

## 6) Concurrency and resource governance

To avoid model contention and queue collapse:
- global concurrency caps,
- per-agent run caps,
- priority scheduling,
- cooldown/backoff,
- circuit-breaker behaviour when latency/error thresholds are crossed.

## 7) Internet research policy (read-only intelligence)

Agents may use internet sources for research under strict controls:
- read-only access,
- source citation and confidence labels,
- no external posting/actions by default,
- policy-bound domain allowlists by role.

## 8) Dashboard evidence model

OpenRook will evidence effectiveness through:
- **Agents view:** lane activity, autonomy actions, queue metrics, success/failure trends.
- **Learning view:** insights promoted, reuse rates, reduction in repeat issues.
- **Value view:** MTTD/MTTR movement, auto-resolution rates, cost per resolved issue.

## 9) Standardised onboarding for future agents

A reusable blueprint ensures new agents (e.g., secretary, SEO specialist) integrate consistently:
- role charter,
- trigger map,
- autonomy tier,
- controls/budget profile,
- KPI mapping,
- validation and shadow-mode criteria.

## 10) Delivery phases

### Phase 1 — Governance spine
- role contracts, lane scheduler, autonomy policy, KPI definitions.

### Phase 2 — Proactive activation
- trigger matrix, watcher/thinker pattern, controlled autonomous actions.

### Phase 3 — Learning and optimisation
- promotion pipeline for reusable capability, performance tuning, drift controls.

### Phase 4 — Agent factory
- standard blueprint onboarding and certification for new agent types.


## What this gives us immediately

As Phase 1 artifacts are introduced, organisations get immediate practical benefits:

- **Consistent agent design:** each agent follows a standard operating contract.
- **Clear accountability:** mission, scope boundaries, and ownership transfer are explicit.
- **Safer autonomy:** role-level action limits and approval requirements are documented up front.
- **Managed handoffs:** out-of-scope work is delegated in a structured, auditable way rather than dropped.
- **Local-model efficiency:** role runtime defaults can be pinned to local models for cost control.
- **Built-in learning expectations:** each role is required to produce learning evidence and improvement signals.
- **Comparable performance measurement:** KPI definitions are standardised, enabling cross-role benchmarking.
- **Future-ready onboarding:** new agent types can be introduced using the same contract template and governance flow.

### Publication pattern (ongoing)
OpenRook will continue to publish this style of update:
- what capability was added,
- what immediate operational value it unlocks,
- what governance/safety outcomes it improves,
- and how it supports future agent expansion.

## 11) Success criteria

- Reduced repeat incident rate
- Improved MTTD/MTTR
- Increased low-risk autonomous resolution rate
- Improved agent competency scores by role
- Clear evidence of value in dashboard reporting
