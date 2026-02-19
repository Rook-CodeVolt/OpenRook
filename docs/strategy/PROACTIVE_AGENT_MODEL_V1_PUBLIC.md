# Proactive Agent Model v1 (Public)

## Purpose
Provide one clear public model for how proactive agents are developed and deployed safely, without exposing sensitive implementation details.

## Why this model
- Turn reactive assistants into proactive operators.
- Keep humans in control through explicit governance.
- Improve reliability, learning, and measurable value over time.
- Maintain local-model-first efficiency for autonomous workloads.

## Public operating model

### 1) Safety-first autonomy
- Risk-tiered actions
- Approval gates for non-trivial changes
- Structured escalation paths
- Auditability for autonomous decisions

### 2) Proactive operations
- Event-driven triggers first
- Scheduled health/drift checks as fallback
- Priority lanes (hot/warm/cold)
- Managed handoffs between role-specialised agents

### 3) Learning and improvement lifecycle
- Capture outcomes from completed tasks/incidents
- Distill reusable lessons
- Validate before reuse
- Retire stale or low-value patterns

### 4) Resource governance
- Global and per-agent concurrency controls
- Budget and contention controls
- Backoff/circuit-breaker behavior under load

### 5) Evidence-led operations
- Agents evidence (activity, queue, outcomes)
- Learning evidence (promoted insights, reuse)
- Value evidence (resolution speed, reliability impact)

### 6) Standard agent onboarding (“Agent Factory”)
Each new agent should include:
- role charter and boundaries,
- trigger map,
- action/risk policy,
- runtime profile,
- learning obligations,
- KPI and evidence mapping,
- shadow-mode promotion criteria.

## Delivery intent
This model is delivered in phases:
1. Governance and policy baseline
2. Proactive runtime activation
3. Learning and optimisation loop
4. Repeatable new-agent onboarding

## Security/privacy boundary
OpenRook shares architecture and control patterns only.
It does not publish secrets, sensitive infrastructure, or exploit-level implementation details.
