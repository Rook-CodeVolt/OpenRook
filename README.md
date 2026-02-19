# OpenRook

A public overview of how we evolved an OpenClaw deployment into a robust, agent-first operating platform.

> This repository intentionally shares **what** was improved, not sensitive internals, credentials, private infrastructure, or exploit details.

## Why OpenRook

OpenRook is a practical blueprint for teams who want dependable agent support in real operations:
- clearer agent roles,
- safer automation,
- stronger reliability and observability,
- lower run cost via local-model-first execution,
- better operator experience.

## What Was Improved

### 1) Agent Architecture and Role Specialization
We moved from generic assistant behaviour to a specialized multi-agent model with explicit responsibilities.

Core roles include:
- **architect-2.0** — system design and technical decomposition
- **builder-2.0** — implementation and delivery
- **validator-2.0** — test design and quality validation
- **guardian-2.0** — security and compliance posture
- **sentinel-2.0** — monitoring, alerting, and incident detection
- **analyst-2.0** — requirements and option analysis
- **researcher-2.0** — deep research and innovation scans
- **critic-2.0** — code quality and standards review
- **evolutionist-2.0** — refactoring and optimisation
- **mentor-2.0** — documentation and knowledge transfer
- **ml-specialist-2.0** — ML/AI implementation patterns
- **data-specialist-2.0** — data pipelines and analytics
- **api-specialist-2.0** — integration and API lifecycle

### 2) Auditable Agent Learning and Feedback Use
We established a fail-closed standard for agent outputs so learning is verifiable:
- explicit feedback usage markers,
- applied-learning traces,
- structured handoff context,
- improved accountability between agent turns.

### 3) Local-Model-First Heavy Lifting
We aligned agent execution toward local infrastructure (LM Studio first) to reduce external token dependence while keeping quality high.

### 4) Pipeline and Orchestration Maturity
We introduced stronger task orchestration and execution flow discipline:
- unified project/task pipeline patterns,
- cleaner delegation/handoff behaviours,
- better sub-agent usage boundaries,
- stronger operational controls.

### 5) Reliability and Safety Hardening
Key reliability and risk-control improvements include:
- safer environment-aware API handling,
- reduction of brittle localhost assumptions,
- durability improvements for stored assets,
- better drift and availability handling,
- stronger operational recovery posture.

### 6) Memory and Context Efficiency
Memory and context flow was improved to reduce waste and improve continuity:
- compact recall patterns,
- memory optimisation loops,
- cleaner context gating for higher-signal agent decisions.

### 7) Skills and Reuse Foundation
We started a reusable skills fabric so repeated high-value work can be converted into sharable, repeatable capability rather than re-solved ad hoc.

### 8) Operator-Facing Reporting and Decision Clarity
Daily briefing/reporting quality was upgraded to include clearer sections on:
- what was completed,
- what is currently true,
- what remains outstanding,
- what should happen next.

## Security and Privacy Principles
OpenRook publishes **capability and architecture patterns**, not sensitive details.

Not included:
- secrets/tokens/keys,
- private hostnames or credential paths,
- exploitable low-level hardening specifics,
- private logs or personal data.

## Who This Is For
- teams deploying OpenClaw in production-like environments,
- builders exploring role-specialized agent operations,
- operators seeking safer automation with strong oversight,
- contributors interested in practical multi-agent governance.

## Contributing
Open to issues and discussion from teams working on real-world agent operations.

Suggested contribution themes:
- role design patterns,
- observability and auditability,
- safe autonomy controls,
- cost/performance optimisation,
- maintenance automation and continuous improvement loops.

## Status
Initial public documentation drop. More structured docs and examples will follow.


## Explore Next

- [Agent Operating Contracts Overview](docs/architecture/AGENT_OPERATING_CONTRACTS_OVERVIEW.md)

- [Proactive Agent Model v1 (Public)](docs/strategy/PROACTIVE_AGENT_MODEL_V1_PUBLIC.md)
- [Proactive Agent Execution Plan v1](docs/strategy/PROACTIVE_AGENT_EXECUTION_PLAN_V1.md)
- [Skill Gap Decision Template](docs/templates/SKILL_GAP_DECISION_TEMPLATE.md)
- [Agent Roles](docs/AGENT_ROLES.md)
- [Before vs After Improvement Matrix](docs/IMPROVEMENT_MATRIX.md)
- [Roadmap](docs/ROADMAP.md)
- [Operations Reliability Note (2026-02-19)](docs/operations/OPS_RELIABILITY_NOTE_2026-02-19.md)
- [AI Risk Monitoring Note (2026-02-19)](docs/security/AI_RISK_MONITORING_NOTE_2026-02-19.md)
- [Drift Guard Value Note (2026-02-19)](docs/operations/DRIFT_GUARD_VALUE_NOTE_2026-02-19.md)
- [Delivery Discipline Note (2026-02-19)](docs/operations/DELIVERY_DISCIPLINE_NOTE_2026-02-19.md)
- [Autonomy Policy Template](docs/templates/AUTONOMY_POLICY_TEMPLATE.md)
- [Memory & Learning Approach (Public Summary)](docs/MEMORY_AND_LEARNING_APPROACH.md)

## Community Input

If you are looking for agent support patterns, open an issue with context and goals:
- `Agent support request`
- `Feature request`


## Proactive Autonomy Vision

OpenRook is not only about responding to prompts. The intent is to operate agents as **proactive, managed-autonomy workers** for day-to-day platform operations.

### Direction
- Move from request-only operation to **continuous operational stewardship**.
- Keep humans in control with explicit policy, risk tiers, and approval gates.
- Prioritize local-model execution for routine/high-frequency tasks.

### Managed self-learning loop
Agents should continuously improve through a controlled loop:
1. Observe outcomes and operational signals.
2. Extract reusable lessons.
3. Convert repeat patterns into skills/playbooks/checks.
4. Validate improvements and keep audit evidence.

### Browser/web intelligence policy (read-only)
Internet access can be used for research and learning **in read-only mode**:
- search/fetch for evidence and best practices,
- no external posting or account actions,
- source citation and confidence labeling,
- policy-scoped domain allowlists.

### Cost and safety constraints
- local LLM-first for continual tasks,
- bounded budgets and concurrency limits,
- escalation to heavier reasoning only on threshold/risk triggers.


## Memory, Learning, and Improvement (High-Level)

Our approach treats memory as an operational capability, not a transcript dump.

### What we optimise for
- **Continuity:** agents should remember enough to avoid repeating work.
- **Signal quality:** promote durable, high-value facts over noisy one-off chatter.
- **Actionability:** memory should improve decision quality and task execution.

### How learning works (without exposing internals)
- Capture outcomes from completed work and incidents.
- Distill reusable lessons into concise operational knowledge.
- Route those lessons into role-appropriate skills, checks, and playbooks.
- Re-validate over time so learning stays useful and current.

### Guardrails
- Memory is policy-scoped and privacy-aware.
- Sensitive details are minimized/redacted in public-facing artefacts.
- Learning is auditable at the behaviour level (what improved), without disclosing private implementation mechanics.

In short: we focus on compounding practical capability while keeping security and privacy boundaries intact.


## Governance and Standards Pack

- [Standards Set Index](governance/reference/STANDARDS_SET_INDEX.md)
- [Governance Pack](governance/README.md)
- [OpenRook Inter-Agent Collaboration Model](docs/architecture/INTER_AGENT_COLLABORATION_MODEL.md)
