# Direction Change Alignment — 2026-02-24

## Purpose
Record the current execution-direction changes so OpenRook mirrors the active source-of-truth trajectory and operator intent.

## Confirmed direction updates

1. **Autonomy execution mandate (operator-level)**
   - When path is clear and safe/internal, execute without waiting for nudges.
   - Resolve blockers via fix-forward and auto-pivot to better-defined paths.
   - Keep progress/docs/DR artifacts synchronized with execution.

2. **Learning quality over volume**
   - Repetition loop detection now treated as first-class blocker signal.
   - Automatic remediation is triggered for over-threshold repetition patterns.
   - Learning status messaging now must explicitly state: action required vs system-managed.

3. **Dashboard UX operating standard**
   - Summary cards must be glanceable and plain-language.
   - Detail views must remain human-readable in dashboard style (no raw JSON as operator UX).
   - Every critical panel should include explicit action guidance.

4. **Learning activity visibility**
   - 10-minute-window learning activity badge is now required style:
     - `ACTIVE`, `WORKING`, `MAINTENANCE`, `STALLED`
   - If not active, provide explicit reason + suggested action.

5. **Agent communication observability refresh**
   - Deprecated synthetic/legacy “understanding score” presentation.
   - Prefer real telemetry indicators (messages/events/handoffs/mentorship/task outcomes).
   - Ongoing redesign target: unified conversation stream over fragmented panels.

6. **Skill management scale gap recognized**
   - Existing skills fabric is foundational but not sufficient for 100s/1000s of skills.
   - New required capability track: scale-ready skill management
     - taxonomy/hierarchy
     - dedupe/merge
     - lifecycle/versioning
     - ownership/review governance
     - archive/retire flow

## Operator impact
- Operator should increasingly see clear “no action needed” vs “attention recommended” guidance.
- Persistent degraded states should include reason and ownership of remediation path.

## Mirror note
- Source-of-truth remains in `rook-core-v2`.
- This OpenRook note reflects current direction and should be kept in sync as implementation advances.
