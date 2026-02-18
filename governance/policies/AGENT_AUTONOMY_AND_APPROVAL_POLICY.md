# Agent Autonomy and Approval Policy (Template)

## 1) Purpose
Define autonomy boundaries, approval gates, and runtime constraints for agent actions.

## 2) Autonomy tiers
- **Tier 0 — Observe:** detect/analyze only, no state change.
- **Tier 1 — Suggest:** recommend actions, no execution.
- **Tier 2 — Auto Low-Risk:** execute pre-approved low-risk actions.
- **Tier 3 — Guarded:** medium/high-risk actions require explicit approval.

## 3) Risk classification
Minimum dimensions:
- business impact,
- security/privacy impact,
- availability/reliability impact,
- legal/compliance impact,
- reversibility.

## 4) Approval matrix (example)
| Action class | Tier | Approval required |
|---|---:|---|
| Read-only diagnostics | 0/1 | No |
| Non-prod low-risk maintenance | 2 | Pre-approved policy |
| Prod config changes | 3 | Service owner + security |
| External/public communications | 3 | Business owner |
| Access/credential changes | 3 | Security owner |

## 5) Mandatory runtime constraints
- per-agent concurrency cap,
- global concurrency cap,
- daily/weekly budget quotas,
- tool allowlist per role,
- kill switch (global + per-agent),
- full action/audit logging.

## 6) Escalation requirements
Escalate to human when:
- confidence below threshold,
- conflicting evidence,
- potential customer/legal impact,
- repeated failed auto-remediation,
- action exceeds Tier 2 boundary.

## 7) Safe execution requirements
Before autonomous action:
- verify preconditions,
- capture checkpoint/backup when relevant,
- define rollback path,
- define success/failure criteria.

After action:
- run validation checks,
- emit structured evidence,
- rollback or escalate on validation failure.

## 8) Exceptions
Temporary exceptions require:
- documented justification,
- compensating controls,
- expiry date,
- post-expiry review.

## 9) Metrics and review
Track:
- auto-resolution rate,
- approval turnaround,
- rollback frequency,
- incident rate by tier,
- budget utilization.

Review cadence: monthly operations review + quarterly governance review.
