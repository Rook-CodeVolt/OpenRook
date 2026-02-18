# Security Considerations and Recommended Controls

## 1) Threat categories
- Unauthorized access and privilege misuse
- Data leakage/exfiltration
- Prompt/tool abuse and unsafe automation
- Dependency/supply-chain compromise
- Availability disruption and resilience failures

## 2) Security control framework

### 2.1 Governance controls
- security ownership for each AI/agent system
- risk assessments before production deployment
- formal exception handling with expiry

### 2.2 Identity and access controls
- RBAC + least privilege
- MFA for privileged operators
- just-in-time access for high-risk operations
- periodic access recertification

### 2.3 Data security controls
- data classification and handling rules
- encryption in transit/at rest
- masking/redaction for sensitive attributes
- retention and disposal controls

### 2.4 Application/agent safety controls
- tool allowlist and denylist by role
- autonomy tier enforcement
- approval gates for higher-risk actions
- safe defaults + explicit user intent checks

### 2.5 Infrastructure controls
- environment isolation
- hardened runtime configuration
- patch/vulnerability management
- secret lifecycle management

### 2.6 Detection and response controls
- centralized telemetry and SIEM integration (where available)
- anomaly detection and alert routing
- incident triage and response runbooks
- post-incident review and control updates

### 2.7 Resilience controls
- tested backup/restore
- disaster recovery objectives (RTO/RPO)
- graceful degradation and fail-safe behavior
- kill switch for autonomous workflows

## 3) Control testing approach
- pre-deploy checks,
- periodic control effectiveness tests,
- tabletop scenarios,
- red-team style adversarial testing where appropriate.

## 4) Minimum recommended baseline
- MFA + least privilege
- approval gates for medium/high risk actions
- immutable audit logs
- regular patching and vuln scans
- tested recovery runbooks
