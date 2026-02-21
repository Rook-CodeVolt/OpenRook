# Mission Control Reuse Execution Checklist (2026-02-21)

Scope: Reuse relevant ideas from `abhi1693/openclaw-mission-control` without recreating full stack.

## Reused ideas (copied into OpenRook operating model)
1. Approval-first execution for sensitive actions.
2. Health vs readiness split before run admission.
3. Control-plane object model (board group → board → task).
4. Activity timeline evidence as first-class output.
5. Bootstrap validation checklist before runtime start.
6. Local/self-host auth mode clarity (cost and security aware).

## Dashboard ideas considered (and selected for reuse)
From Mission Control frontend (`/dashboard`, `/activity`, `/approvals`, sidebar/nav model):

1. **KPI strip with operational primitives** — adopt
- Active agents, tasks-in-progress, error-rate, cycle-time style headline cards.

2. **Time-range + scope filters** — adopt
- Global range selector plus group/board scope filter model.

3. **Multi-chart operational panel** — adopt
- Throughput, cycle-time, error trend, status-distribution views.

4. **Live activity feed panel** — adopt
- Real-time event timeline with loading/empty/error states.

5. **Global approvals queue page** — adopt
- Cross-board pending approvals list with approve/reject actions.

6. **Sidebar information architecture** — adopt
- Overview / Boards / Skills / Admin split with role-based visibility.

7. **System health badge in shell** — adopt
- Always-visible status indicator (`operational/degraded/unknown`).

8. **Do not copy visual stack details verbatim** — not adopted
- Keep existing OpenRook UI framework choices; reuse UX patterns + object model only.

## Phase plan with acceptance evidence

### Phase 1 — Governance + evidence (Priority: P0)
- [ ] Add approval gate policy for risky actions (delete/reset/network/security changes).
- [ ] Add standard evidence record template per completed task.
- [ ] Add mandatory readiness precheck before launching agent workflows.

Acceptance evidence:
- At least 3 completed tasks include full evidence block.
- At least 1 risky action blocked pending approval.
- Readiness precheck logged with pass/fail result.

### Phase 2 — Queue/object model alignment (Priority: P1)
- [ ] Map current task runner entities to board/queue model.
- [ ] Define canonical states: `queued`, `running`, `blocked`, `done`, `failed`.
- [ ] Add owner + SLA metadata to each task.

Acceptance evidence:
- Sample backlog export showing all canonical states.
- SLA watchdog reports against mapped queue objects.

### Phase 3 — Gateway control-plane stabilization (Priority: P1)
- [ ] Add single-source gateway lifecycle checks (start/stop/restart/status).
- [ ] Add stale-process detection (`openclaw-onboard`, duplicate gateway, stale tunnel).
- [ ] Add noisy-log detector with auto-alert for repeated auth mismatch.

Acceptance evidence:
- 24h run with no duplicate gateway start loop.
- Auto-alert sample for induced noisy-loop test.

### Phase 4 — Bootstrap/installer reliability (Priority: P2)
- [ ] Add preflight checklist script (env, auth mode, required files, workspace write).
- [ ] Add one-command "safe start" path for local operators.
- [ ] Add rollback notes for config migration changes.

Acceptance evidence:
- Preflight report generated before startup.
- Rollback tested and documented.

## Reuse boundaries
- Reuse patterns and governance only.
- Do not force adoption of upstream stack components if misaligned to local ops/cost constraints.

## Immediate next 3 tasks
1. Implement readiness precheck script and log format.
2. Implement stale-process/noise detector script with thresholds.
3. Add evidence block template to completion flow.

## Dashboard physicalization of capability proof (added)
- Add a Capability Proof Scorecard panel (readiness score + gate status).
- Add Learning/Independence/Collaboration proof panels sourced from evidence files.
- Add Governance & Release Gate panel with blocker reasons.
- Add Approval Queue + proof activity timeline panel for operator workflow.
