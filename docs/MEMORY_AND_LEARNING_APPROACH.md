# Memory and Learning Approach (Public Summary)

This document describes the **intent and operating philosophy** for memory and learning in OpenRook-style agent systems.

## Design intent

We want agents that improve over time without becoming noisy, brittle, or unsafe.

### Principles
1. **Useful over exhaustive**
   - Keep what improves future decisions and delivery quality.
   - Avoid storing low-value repetition.

2. **Operational memory, not diary memory**
   - Prioritize decisions, outcomes, constraints, and validated patterns.
   - Emphasize what helps agents perform better in real workflows.

3. **Progressive codification**
   - Repeated patterns should be promoted into reusable skills/checklists/playbooks.
   - Learning should reduce future effort and error rates.

4. **Role-aware retrieval**
   - Different agent roles need different context slices.
   - Retrieval should be targeted and concise, not bulk replay.

5. **Privacy and safety by default**
   - Sensitive data handling is minimized and policy-bound.
   - Public artifacts describe outcomes and patterns, not private internals.

## Learning lifecycle (public model)

1. **Observe** — collect outcomes, incidents, and task evidence.
2. **Extract** — identify what changed performance or reliability.
3. **Codify** — convert repeatable insights into reusable operational assets.
4. **Validate** — test whether codified learning actually improves results.
5. **Evolve** — keep, refine, or retire learning artifacts based on evidence.

## What this enables

- Better continuity across tasks and handoffs.
- Less repeated troubleshooting.
- Higher quality autonomous day-to-day operations.
- Safer proactive behavior under governance.

## What we do not publish

To protect users and systems, we do **not** publish private implementation details such as:
- sensitive memory schemas tied to private infrastructure,
- internal prompting mechanics that could be abused,
- secret thresholds/controls that would reduce defensive effectiveness.

We publish outcomes, principles, and safe adoption guidance instead.
