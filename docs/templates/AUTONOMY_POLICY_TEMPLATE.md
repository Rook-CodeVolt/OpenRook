# Autonomy Policy Template (v1)

Use this template to run proactive agents safely, efficiently, and with clear human oversight.

## 1) Purpose
Define what proactive autonomy should achieve in your environment.

- Primary outcomes:
- In-scope systems:
- Out-of-scope systems:

## 2) Agent scope and responsibilities
List each agent role with explicit boundaries.

| Agent | Core scope | Allowed autonomous actions | Requires approval |
|---|---|---|---|
| sentinel | monitoring + anomaly detection | collect evidence, raise alerts | service-affecting changes |
| guardian | security posture + drift checks | low-risk config checks, advisory generation | policy changes, privileged remediations |
| builder | implementation tasks | pre-approved low-risk maintenance | architecture/security-significant changes |
| validator | validation and regression checks | run tests, produce evidence | release overrides |
| mentor | documentation + skill codification | create/update runbooks and skill drafts | policy publication changes |

## 3) Autonomy risk tiers
Define what can run automatically.

- **Tier 0 (Observe):** detect/report only
- **Tier 1 (Suggest):** suggest actions, no execution
- **Tier 2 (Auto low-risk):** execute pre-approved low-risk actions
- **Tier 3 (Guarded):** execution requires explicit human approval

## 4) Trigger model (proactive + reactive)
Use event/signal-driven triggers first, then scheduled sweeps.

- Event triggers:
  - failed jobs
  - repeated error signatures
  - security advisories
  - service health degradation
- Scheduled triggers:
  - light checks: every N minutes
  - deep checks: every N hours

## 5) LLM execution policy
Default to local models for routine operations.

- Local model default:
- Escalation model(s):
- Escalation conditions:
- Max concurrent local generations:
- Per-agent concurrency cap:

## 6) Budget and rate limits
Prevent uncontrolled token/compute growth.

- Per-agent daily token budget:
- Global daily token budget:
- Per-hour call limits:
- Cooldown/backoff policy:

## 7) Browser/web research policy (read-only)
Allow research while preventing external side effects.

- Allowed tools: web_search, web_fetch, browser (read-only workflows)
- Prohibited actions: posting, account actions, writes/submissions to third-party services
- Domain allowlist by role:
- Citation requirement: yes/no

## 8) Continuous learning loop
Enforce repeatable improvement.

1. Observe outcomes
2. Extract insight
3. Convert repeated patterns to skills/playbooks/rules
4. Validate impact with evidence
5. Promote or rollback

Promotion threshold example:
- If a pattern repeats >= 3 times in 14 days, create a reusable skill/check.

## 9) Evidence and auditability
Require auditable output from autonomous runs.

- Required run metadata:
  - trigger source
  - model/provider used
  - action class/risk tier
  - outcome + evidence links
- Retention period:
- Review cadence:

## 10) Human control and safeguards
Keep operator authority explicit.

- Global kill switch:
- Per-agent kill switch:
- Approval channels:
- Incident escalation path:

## 11) Success metrics (weekly)
Measure both capability and cost discipline.

- incidents detected early
- mean time to detect (MTTD)
- mean time to resolve (MTTR)
- % low-risk actions auto-resolved
- token/compute per resolved issue
- # patterns promoted into reusable skills

## 12) Rollout plan
Adopt safely in phases.

1. Observe-only baseline
2. Suggest-only mode
3. Auto low-risk on allowlisted actions
4. Expand gradually with weekly review

---

## Change log
- v1: initial template
