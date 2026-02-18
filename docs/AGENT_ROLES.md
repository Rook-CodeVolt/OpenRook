# Agent Roles (OpenRook)

This page summarizes the role-specialized model used in OpenRook-style OpenClaw operations.

## Role matrix

| Agent | Primary mission | Typical triggers | Main outputs |
|---|---|---|---|
| architect-2.0 | System design and decomposition | repeated incidents, major feature changes | architecture specs, implementation plans |
| builder-2.0 | Implementation and delivery | approved work items, remediation tasks | code changes, integration updates |
| validator-2.0 | Quality and verification | post-implementation, pre-release gates | test evidence, validation reports |
| guardian-2.0 | Security and compliance | vulnerability alerts, policy drift | risk findings, hardening recommendations |
| sentinel-2.0 | Monitoring and incident detection | health degradation, telemetry anomalies | incident alerts, health summaries |
| analyst-2.0 | Requirement and option analysis | ambiguous requests, planning phases | option analysis, feasibility notes |
| researcher-2.0 | Deep research and innovation | unknown domains, strategic exploration | comparative research, recommendations |
| critic-2.0 | Code quality and standards | code review events, quality sweeps | review feedback, refactor priorities |
| evolutionist-2.0 | Refactoring and optimization | performance debt, maintainability issues | optimization plans, modernization changes |
| mentor-2.0 | Documentation and knowledge transfer | handoffs, onboarding, repeatable patterns | docs, runbooks, skill definitions |
| ml-specialist-2.0 | ML/AI implementation | model tasks, inference/training design | ML architecture and delivery guidance |
| data-specialist-2.0 | Data pipelines and analytics | ETL/reporting/data quality work | pipelines, metrics/reporting artifacts |
| api-specialist-2.0 | API design and integration | integration projects, API lifecycle tasks | API contracts, integration implementations |

## Operating principles

- **Specialization first:** work should be routed by role-fit, not by a generic single agent.
- **Auditable handoffs:** each role contributes explicit outputs that can be validated by downstream roles.
- **Safety tiers:** low-risk actions can be automated, high-risk actions require approval.
- **Continuous improvement:** recurring work should be promoted into reusable skills/playbooks.

## Notes for adopters

Start with 4–5 core roles (`sentinel`, `guardian`, `builder`, `validator`, `mentor`) and expand once governance, observability, and cost controls are stable.
