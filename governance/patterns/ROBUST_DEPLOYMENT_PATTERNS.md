# Robust Deployment Patterns for AI + Agents

This document turns high-level pattern descriptions into reusable, generic implementation patterns.

---

## Pattern 1: Tiered Autonomy Rollout

### Goal
Increase autonomy safely without losing control.

### Use when
You are moving from manual/assistive AI to proactive autonomous agents.

### Generic pattern
1. **Stage A — Observe only**
   - Agent collects signals and produces recommendations.
   - No external or state-changing actions.
2. **Stage B — Suggest + pre-checks**
   - Agent can prepare actions but requires approval.
   - Attach impact/risk summary with each suggestion.
3. **Stage C — Auto low-risk**
   - Agent executes pre-approved low-risk actions.
   - Mandatory logging + rollback reference.
4. **Stage D — Guarded medium/high-risk**
   - Medium/high-risk actions require explicit approval.
   - Break-glass path is controlled and audited.

### Required controls
- Risk-tier taxonomy
- Approval workflow
- Action logs and audit trail
- Kill switch

### Evidence of compliance
- % actions by risk tier
- Approval records for tiered actions
- Incident rate before/after each stage

---

## Pattern 2: Environment Segregation (Dev/Test/Prod)

### Goal
Prevent uncontrolled promotion of unsafe AI/agent behaviour.

### Use when
Deploying AI/agent capabilities in production-like systems.

### Generic pattern
- **Dev:** rapid iteration, synthetic/non-sensitive data preferred
- **Test/Staging:** production-like config with non-production credentials
- **Prod:** strict change control, least privilege, monitored runtime

### Required controls
- Separate credentials and secrets per environment
- Separate model endpoints/keys where applicable
- Promotion gates (test + security + approval)
- Immutable deployment artefacts

### Evidence of compliance
- Promotion checklist artefacts
- Change tickets with approvals
- Segregated access review records

---

## Pattern 3: Policy-Enforced Action Boundaries

### Goal
Ensure agents act only within explicitly authorised limits.

### Use when
Agents can access tools, integrations, or execution environments.

### Generic pattern
- Define **allowlist-first** action policy per role.
- Define explicit denylist for prohibited operations.
- Bind each action to a risk tier and approval rule.
- Enforce runtime policy checks before execution.

### Required controls
- Role-to-action matrix
- Tool permission policy
- Approval gate for non-low-risk operations
- Exception handling and expiry for temporary overrides

### Evidence of compliance
- Policy versions and change history
- Blocked-action logs
- Exception register with expiry and owners

---

## Pattern 4: Event-Driven Orchestration (Not Constant Polling)

### Goal
Reduce cost/latency while improving responsiveness.

### Use when
You need continuous operations without continuous token burn.

### Generic pattern
- Trigger agents from signals/events:
  - failed jobs
  - threshold breaches
  - error-pattern recurrence
  - security advisories
- Use scheduled sweeps only for low-frequency integrity checks.
- Use deduplication and cooldown windows to prevent alert storms.

### Required controls
- Event taxonomy and severity model
- De-duplication rules
- Cooldown/backoff policy
- Priority queue (P0/P1/P2)

### Evidence of compliance
- event-to-action latency
- duplicate event suppression stats
- cost per resolved incident

---

## Pattern 5: Local-Model-First with Escalation

### Goal
Control token cost while preserving quality on complex tasks.

### Use when
Running frequent AI/agent operations where cloud usage is expensive.

### Generic pattern
- Default all routine tasks to local model(s).
- Define escalation triggers (complexity/risk/low confidence).
- Route only escalated tasks to stronger or external models.
- Record model selection rationale for each escalation.

### Required controls
- Model routing policy
- Confidence/quality thresholds
- Budget caps and per-agent quotas
- Fallback policy for local model outages

### Evidence of compliance
- % tasks served locally
- escalation rate by use case
- cost trend vs resolution quality

---

## Pattern 6: Continuous Control Verification

### Goal
Verify controls remain effective over time.

### Use when
Operating AI/agent systems in live environments.

### Generic pattern
- Schedule recurring control checks:
  - access reviews
  - policy enforcement tests
  - incident response drills
  - backup/recovery tests
- Run periodic tabletop exercises.
- Track findings to closure with owner + due date.

### Required controls
- Verification schedule
- Test scripts/checklists
- Findings tracker with SLA
- Management review cadence

### Evidence of compliance
- control test pass rates
- open findings aging
- drill outcomes and remediation completion

---

## Pattern 7: Managed Learning Loop (Observe → Codify → Reuse)

### Goal
Turn repeated operational work into reusable capability.

### Use when
The same classes of incidents/tasks repeat.

### Generic pattern
1. Observe repeated issue class
2. Extract stable resolution pattern
3. Convert into reusable skill/playbook/check
4. Validate on future occurrences
5. Promote to standard operating practice

### Required controls
- Learning promotion criteria (e.g., repeat threshold)
- Review/approval of new reusable artefacts
- Versioning and rollback for learned automations

### Evidence of compliance
- # patterns promoted per month
- repeat incident reduction rate
- mean time to resolve improvement

---

## Pattern 8: Read-Only External Intelligence

### Goal
Leverage web research safely without external action risk.

### Use when
Agents need current external information to improve decisions.

### Generic pattern
- Permit read-only search/fetch on allowlisted sources.
- Require source citation and confidence label.
- Prohibit posting/transactions/account actions by default.
- Route high-impact recommendations to human approval.

### Required controls
- Domain allowlists by role
- Prohibited action policy
- Citation requirement
- Review gates for externally sourced recommendations

### Evidence of compliance
- cited recommendation ratio
- blocked prohibited-action attempts
- decision quality improvements from external intelligence

---

## Pattern 9: Multi-Agent Concurrency Governor

### Goal
Prevent model endpoint contention and cascading failures.

### Use when
Multiple agents share one or limited model runtime.

### Generic pattern
- Global concurrency cap (e.g., max active generations)
- Per-agent concurrency cap
- Priority scheduling (incident > maintenance > learning)
- Queue timeout + retry with jittered backoff

### Required controls
- Scheduler policy
- Queue observability
- Starvation prevention rules
- Circuit breaker when latency/error exceeds threshold

### Evidence of compliance
- queue wait times
- timeout/error rates under load
- SLA adherence by priority class

---

## Pattern 10: Safe Change + Rollback by Design

### Goal
Ensure autonomous changes are reversible and auditable.

### Use when
Agents can modify code/config/runtime state.

### Generic pattern
- Require pre-change snapshot/checkpoint.
- Attach rollback plan before execution.
- Validate post-change success criteria.
- Auto-rollback on failed validation where appropriate.

### Required controls
- Backup/checkpoint mechanism
- Rollback procedure ownership
- Post-change validation checklist
- Change evidence retention

### Evidence of compliance
- successful rollback test rate
- change failure rate
- time to restore service baseline

---

## Implementation note
Start with Patterns **1, 3, 4, 5, 9** as your minimum viable governance baseline. Add others as maturity increases.
