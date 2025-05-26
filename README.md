### OWASP CI/CD Risk Matrix — Fortinet Product Coverage

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