# Security Considerations and Recommended Controls

## Core threats
- unauthorized data access/exfiltration
- prompt/tool abuse and unsafe actions
- model misuse/hallucination-driven actions
- privilege escalation through integrations
- supply-chain and dependency risks

## Recommended controls

### Access and identity
- SSO/MFA for operator/admin roles
- least-privilege RBAC for tools and integrations
- scoped service credentials and key rotation

### Data protection
- data classification and minimization
- encryption in transit and at rest
- DLP controls for sensitive outputs

### Agent/action safety
- risk-tiered autonomy with approval gates
- action allowlists/denylists
- outbound channel restrictions
- read-only web mode for research agents

### Monitoring and assurance
- centralized logs with tamper-evident retention
- anomaly detection and alerting
- regular control effectiveness testing
- incident response with post-mortems

### Resilience
- tested backups and recovery runbooks
- dependency monitoring and patching
- fail-safe defaults and kill switches

## Enforcement patterns
- policy-as-code where possible
- mandatory pre-deploy security checklist
- periodic attestation by system owners
