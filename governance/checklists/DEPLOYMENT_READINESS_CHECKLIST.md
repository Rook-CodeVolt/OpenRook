# Deployment Readiness Checklist

## A. Governance and ownership
- [ ] Use case documented and approved
- [ ] System owner and technical owner assigned
- [ ] Risk classification completed
- [ ] Policies acknowledged by operators

## B. Architecture and security
- [ ] Environment separation verified (dev/test/prod)
- [ ] RBAC and least privilege configured
- [ ] Secrets stored and rotated securely
- [ ] Logging/monitoring/alerts enabled
- [ ] Backup and restore test passed

## C. AI/agent controls
- [ ] Model evaluation passed acceptance criteria
- [ ] Agent role charter approved
- [ ] Autonomy tier assigned
- [ ] Approval gates configured for higher-risk actions
- [ ] Tool permissions constrained by role
- [ ] Budget and concurrency limits configured

## D. Validation and resilience
- [ ] Functional validation passed
- [ ] Security validation passed
- [ ] Rollback plan tested
- [ ] Incident runbook validated

## E. Launch authorization
- [ ] Go-live approval recorded
- [ ] Post-launch monitoring window defined
- [ ] Owner on-call coverage confirmed
