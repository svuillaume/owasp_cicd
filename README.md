### OWASP Top 10 CI/CD Security Risks Mapped to Fortinet Cloud Solutions 

| **Risk** | **What It’s About** | **Example** | **FortiWeb** | **FortiGate** | **FortiCNAPP** |
|----------|----------------------|-------------|--------------|---------------|----------------|
| **SEC-1**<br>Insufficient Flow Control | Pipeline too open, no proper checks on triggers or steps | Unapproved PR triggers GitHub Actions deploy | ✅ | ✅ | ✅ |
| **SEC-2**<br>Inadequate IAM | Weak access control or account sprawl | Leaked credentials used to modify pipelines | ❌ | ✅ | ✅ |
| **SEC-3**<br>Dependency Chain Abuse | Malicious code hidden in dependencies | Event-Stream npm package compromised | ❌ | ✅ | ✅ |
| **SEC-4**<br>Poisoned Pipeline Execution | Injecting or modifying scripts during CI | SolarWinds malware added in build step | ✅ | ✅ | ✅ |
| **SEC-5**<br>Insufficient PBAC | Too much power to users/tools | Service account misused to access prod | ✅ | ✅ | ✅ |
| **SEC-6**<br>Credential Hygiene | Hardcoded secrets or unrotated keys | Uber’s AWS keys leaked via GitHub | ✅ | ✅ | ✅ |
| **SEC-7**<br>Insecure Config | Bad defaults or missing best practices | CI exposed via open ports or weak perms | ✅ | ✅ | ✅ |
| **SEC-8**<br>Ungoverned 3rd-Party Services | Blindly trusting plugins/tools | Tool exfiltrates secrets during builds | ✅ | ✅ | ✅ |
| **SEC-9**<br>Improper Artifact Validation | No signing/checking of builds | Tampered binary sent to production | ✅ | ✅ | ✅ |
| **SEC-10**<br>Insufficient Visibility | Can’t see or audit what’s happening | Attack went undetected for weeks | ✅ | ✅ | ✅ |


# OWASP CI/CD Risk Matrix — Fortinet Product Functional Coverage

This document maps the OWASP Top 10 CI/CD Security Risks to Fortinet solutions: **FortiWeb**, **FortiGate VM**, and **FortiCNAPP (Lacework)**, explaining how each product helps mitigate these risks.

---

| **OWASP CI/CD Risk** | **FortiWeb** | **FortiGate VM** | **FortiCNAPP** |
|----------------------|--------------|------------------|----------------|
| **CICD-SEC-1: Insufficient Flow Control** | Enforces API schema validation, blocks unauthorized requests, detects anomalies in request flow, and integrates with CI/CD to halt malicious payloads. | Monitors and restricts network flows between CI/CD components, enforces segmentation, and blocks suspicious connections. | Monitors pipeline workflows for policy violations and enforces security gates during build and deploy stages. |
| **CICD-SEC-2: Inadequate Identity and Access Management (IAM)** | Supports RBAC, session validation, and API key enforcement to prevent privilege escalation and unauthorized access. | Enforces network-level authentication, VPN, and segmentation to restrict access to critical CI/CD resources. | Assesses IAM policies in cloud and CI/CD platforms, flags misconfigurations, and visualizes privilege risks. |
| **CICD-SEC-3: Dependency Chain Abuse** | Inspects inbound/outbound traffic for malicious packages, blocks known attack signatures, and detects suspicious API calls. | Scans network traffic for malware and C2 communications from compromised dependencies. | Scans container images and code repositories for vulnerable or malicious dependencies before deployment. |
| **CICD-SEC-4: Poisoned Pipeline Execution** | Validates API payloads, blocks code injection attempts, and applies virtual patching to vulnerable CI/CD interfaces. | Detects and blocks lateral movement attempts and command/control traffic. | Monitors runtime behavior of pipeline containers, flags suspicious execution, and enforces runtime policies. |
| **CICD-SEC-5: Insufficient Pipeline-Based Access Controls (PBAC)** | Enforces role-based access at the application/API layer, blocks unauthorized requests, and logs access attempts. | Restricts network access to pipeline components via firewall policies. | Audits and enforces least-privilege access policies across pipeline resources. |
| **CICD-SEC-6: Insufficient Credential Hygiene** | Protects against credential stuffing, enforces strong authentication for APIs, and masks sensitive data in logs. | Detects and blocks brute-force or credential reuse attacks at the network edge. | Scans for secrets in code, containers, and environment variables, and alerts on exposed credentials. |
| **CICD-SEC-7: Insecure System Configuration** | Provides pre-defined and custom security policies, blocks misconfigured endpoints, and applies virtual patching. | Enforces secure network configurations and blocks insecure protocols. | Continuously scans for misconfigurations in cloud and CI/CD environments, providing remediation guidance. |
| **CICD-SEC-8: Ungoverned 3rd Party Services** | Validates and restricts API calls to third-party services, enforces API allowlists, and monitors for abnormal usage. | Controls outbound network traffic to unapproved third-party services. | Assesses third-party integrations for risk and enforces governance policies. |
| **CICD-SEC-9: Improper Artifact Validation** | Scans file uploads for malware, enforces content validation, and blocks suspicious artifacts at the application/API layer. | Filters and inspects network-transferred artifacts for threats. | Scans build artifacts for vulnerabilities and blocks promotion of unsafe images. |
| **CICD-SEC-10: Insufficient Visibility** | Provides detailed analytics, logging, and dashboards for application/API activity and threat events. | Offers network traffic visibility, logs, and security event monitoring. | Aggregates cloud and pipeline activity logs, visualizes attack paths, and correlates security events. |

---

## How Each Product Helps

### FortiWeb
- Protects web apps and APIs from OWASP Top 10 threats using multi-layered detection, machine learning, and real-time traffic analysis.
- Enforces API schema validation, RBAC, anomaly detection, and virtual patching to block unauthorized or malicious activity in CI/CD flows.
- Provides advanced bot mitigation, detailed analytics, and seamless CI/CD integration for automated security enforcement.

### FortiGate VM
- Secures network traffic between CI/CD components, enforces segmentation, and blocks lateral movement or unauthorized access.
- Provides network-level authentication, malware scanning, and logging for comprehensive visibility and control.

### FortiCNAPP (Lacework)
- Offers cloud-native security for CI/CD environments, including container image scanning, IAM risk assessment, and continuous monitoring of pipeline workflows.
- Detects misconfigurations, secrets exposure, and policy violations, and visualizes attack paths across cloud and CI/CD assets.

---

This matrix helps organizations understand how Fortinet’s layered security solutions protect CI/CD pipelines from the most critical risks identified by OWASP.
