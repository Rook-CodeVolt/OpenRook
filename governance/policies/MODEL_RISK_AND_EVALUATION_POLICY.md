# Model Risk and Evaluation Policy (Template)

## 1) Purpose
Define how models are selected, validated, monitored, and retired.

## 2) Scope
Applies to all local and external models used by AI/agent systems.

## 3) Model onboarding requirements
- Documented use-case fit and intended boundaries.
- Risk classification (low/medium/high) by use case.
- Baseline evaluation against defined quality/safety metrics.
- Security/privacy review for data handling implications.
- Approval record before production use.

## 4) Evaluation dimensions
- task quality and accuracy,
- robustness under edge cases,
- safety policy adherence,
- latency and throughput,
- cost efficiency,
- failure-mode behaviour.

## 5) Minimum acceptance criteria (example)
- quality >= target threshold for primary tasks,
- safety test pass rate >= target,
- no critical failure modes unresolved,
- operational performance within SLO/SLA bounds.

## 6) Ongoing monitoring requirements
- drift and degradation monitoring,
- periodic re-evaluation (e.g., monthly/quarterly),
- incident-triggered immediate revalidation,
- logging of model/provider usage by workflow.

## 7) Change management
Model/version changes require:
- change ticket,
- regression evidence,
- rollback plan,
- staged rollout (canary where possible).

## 8) Retirement criteria
Retire or demote model when:
- repeated policy/safety failures,
- sustained performance regression,
- unacceptable risk/cost profile,
- unsupported or insecure dependency chain.

## 9) Documentation artefacts
- model card/system card,
- evaluation report,
- risk register linkage,
- approval records,
- retirement decision logs.
