# Proactive Learning Controls + DR Update — 2026-02-22

## Summary
Platform controls were upgraded from activity-based signals to evidence-gated learning controls, with compensating controls for legacy gaps and DR updates to preserve these guarantees after restore.

## What changed
- Enforced validated-learning-artifact gate for learning credit.
- Added automatic artifact generation + schema validation on task completion.
- Added legacy backfill compensating control for pre-gate completed tasks.
- Added stall-threshold alert when validated artifacts remain zero while tasks continue.
- Added brain proactive assessment artifact (risks, mitigations, unresolved blockers).
- Expanded managed learning cohort from 10 to 13 agents by including:
  - `api-1`
  - `data-1`
  - `ml-specialist-2.0`

## Operational impact
- Dashboard now shows hard-evidence learning health, blocker state, and per-agent proof drilldown.
- “Green” status now requires evidence quality, not just task throughput.
- Recurrence risk reduced via compensating control loops and stall alerts.

## DR impact
DR validation scope now includes proactive-learning controls:
- scoreboards/alerts/proactive assessment artifacts
- training artifact store
- state required by stall monitor
- cohort integrity check (managed set must remain 13)

## Public-safe note
This update intentionally excludes credentials and private infrastructure details.
