# MITRE ATT&CK Mapping

This document maps SOC detections in the homelab environment to the MITRE ATT&CK framework.

---

# Detection Mapping

| Detection | Event ID | ATT&CK Technique | Description |
|------------|----------|-----------------|-------------|
| Multiple Failed Logons | 4625 | T1110 - Brute Force | Detects repeated failed authentication attempts |
| Account Lockout Detected | 4740 | T1110 - Brute Force | Detects account lockouts caused by repeated failed logons |
| Successful Logons | 4624 | T1078 - Valid Accounts | Detects successful authentication activity |

---

# MITRE ATT&CK Techniques

## T1110 - Brute Force

Adversaries may attempt to gain access to accounts through repeated password attempts.

### Related Detections

- Multiple Failed Logons
- Account Lockout Detection

### Data Sources

- Windows Security Logs
- Event ID 4625
- Event ID 4740

---

## T1078 - Valid Accounts

Adversaries may use legitimate credentials to maintain persistence or gain access.

### Related Detections

- Successful Logons

### Data Sources

- Windows Security Logs
- Event ID 4624

---

# Security Value

Mapping detections to MITRE ATT&CK helps:

- Standardize detection engineering
- Improve threat visibility
- Align detections with adversary behavior
- Improve SOC documentation
- Support incident response workflows
