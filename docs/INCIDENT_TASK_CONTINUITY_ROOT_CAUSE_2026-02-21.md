# Incident: Task Continuity Drop During Progress Query (2026-02-21)

## Summary
A continuity failure occurred when a progress check was interpreted using only sub-agent runtime state. The assistant incorrectly concluded there was no active work, even though a manual-document task was still in progress in-session.

## Impact
- Incorrect status response to user
- Loss of trust in continuity
- Delay in continuing `OpenRook/docs/PLANNED_AGENT_CAPABILITY_EXPANSION_2026-02-20.md`

## Investigation scope
Checked:
- Session transcript flow (`~/.openclaw/agents/main/sessions/*.jsonl`)
- Runtime/session state (`openclaw status`, `sessions_list`, `subagents list`)
- Gateway logs (`openclaw logs`)
- Process table (`ps`)
- Config (`gateway config.get`)
- Workspace task/memory files

## Root causes

### RC1 — Status heuristic bug (primary)
Progress logic over-weighted `subagents list` and under-weighted in-session/manual tasks.

Evidence:
- Sub-agents were inactive, but transcript showed active manual task context.
- User-referenced doc existed at `OpenRook/docs/...`, not root `docs/...`.

### RC2 — Path anchoring failure
Initial lookup assumed root-relative `docs/...` instead of resolving possible repo subpaths.

### RC3 — Missing explicit active-task ledger
No required single source of truth file for current objective before responding to "progress/status" prompts.

### RC4 — Platform noise (contributing operational risk)
A stale long-running `openclaw-onboard` process repeatedly attempted gateway starts, flooding logs every ~10s with "gateway already running" errors.

Evidence:
- `openclaw logs` repeated start/port conflict errors.
- `ps` showed `openclaw-onboard` running for ~2 days.

## Fixes applied
1. **Killed stale onboarding loop processes** (`openclaw-onboard` / parent `openclaw`) to stop repeated gateway-start attempts.
2. Added **`ACTIVE_TASK.md`** at workspace root as continuity source-of-truth.
3. Updated **`AGENTS.md`**:
   - Every-session routine now includes reading `ACTIVE_TASK.md`.
   - Added "Progress Continuity Guard" protocol.

## Additional findings
- `sessions_list` exposed a transcript path pointing to workspace root that did not exist, while the actual transcript is under `~/.openclaw/agents/main/sessions/`. This mismatch can mislead diagnostics.
- `openclaw status` reports `memory-core` as enabled but unavailable (non-blocking for this incident, but worth follow-up).

## Preventive controls
- Never declare "nothing in progress" from sub-agent inactivity alone.
- On progress prompts, verify:
  1) `ACTIVE_TASK.md`
  2) referenced file path(s) with `find`
  3) current session transcript/context
- Keep gateway logs low-noise; investigate any recurring daemon restart loops quickly.

## Next recommended follow-up
- Create a small health check that alerts if `openclaw-onboard` runs >10 minutes.
- Investigate/fix `sessions_list.transcriptPath` mismatch in platform code.
