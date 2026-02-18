# Inter-Agent Collaboration Pattern (Public-Safe)

This pattern defines how role-specialised agents collaborate to improve outcomes, without exposing private implementation mechanics.

## 1) Intent
Agents should not operate as isolated silos. They should collaborate to:
- hand off work to the best-suited role,
- share relevant operational learning,
- reduce repeated effort,
- improve quality and response speed.

## 2) Core collaboration principles

### 2.1 Role-fit first
If a task is better suited to another role, the current agent should proactively hand off rather than continue suboptimal execution.

### 2.2 Context-preserving handoff
Each handoff should include a concise context package:
- objective,
- current status,
- constraints and risks,
- evidence/references,
- requested outcome from receiving agent.

### 2.3 Clear ownership
Only one role should be accountable for final delivery at any point in time, even when multiple agents contribute.

### 2.4 Auditability
Inter-agent collaboration should be traceable at outcome level:
- who handed off,
- to whom,
- why,
- what changed,
- resulting outcome.

## 3) Proactive handoff triggers
Handoff should happen automatically when:
- confidence drops below policy threshold,
- specialist knowledge is required,
- risk classification changes,
- repeated retries indicate role mismatch,
- independent validation is required.

## 4) Learning exchange model (without secret internals)

Agents should share high-value lessons as structured operational insights:
1. identify repeatable pattern,
2. summarise what worked/failed,
3. route insight to relevant roles,
4. convert mature patterns into reusable skills/playbooks,
5. re-validate over time.

The emphasis is practical capability growth, not raw transcript sharing.

## 5) Governance guardrails
- Collaboration is policy-bound and role-scoped.
- Sensitive data handling must follow data governance rules.
- High-risk actions remain subject to approval gates.
- Inter-agent exchanges must not bypass control boundaries.

## 6) Generic operating flow
1. Agent A receives trigger/task.
2. Agent A performs initial triage and risk classification.
3. If specialist fit needed, Agent A hands off to Agent B with context package.
4. Agent B executes within its scope and returns evidence/outcome.
5. Originating flow records outcome and promotes reusable learning where appropriate.

## 7) Evidence of healthy collaboration
- reduced rework rate,
- improved time to resolution,
- higher first-pass quality,
- increased number of reusable patterns promoted from cross-agent work.

## 8) What this document intentionally excludes
To preserve safety and operational integrity, this document does not disclose:
- private orchestration mechanics,
- internal prompt/control internals,
- sensitive routing thresholds or defensive tactics.
