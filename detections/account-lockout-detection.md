# Account Lockout Detection

## Objective

Detect user account lockout events that may result from brute-force activity or repeated authentication failures.

## MITRE ATT&CK

- T1110 - Brute Force

## Data Source

- Windows Security Logs
- Event ID 4740 (Account Lockout)

## SPL Query

```spl
index=main EventCode=4740
```

## Purpose

Identify account lockout events and provide visibility into authentication-related security incidents.

## Investigation Steps

1. Identify the locked account.
2. Review recent failed logon activity.
3. Determine the source workstation.
4. Verify whether the lockout was expected.
5. Check for repeated lockouts.
6. Investigate potential malicious activity.

## Escalation Criteria

- Multiple accounts become locked.
- Lockouts originate from unexpected systems.
- Privileged accounts are affected.
- Evidence of brute-force activity exists.

## Validation Results

The detection was validated using account lockout events generated within the lab environment.

Observed Results:

- Event ID 4740 collected by Splunk.
- Lockout events detected successfully.
- Alert triggered and recorded in Splunk.
- Trigger history confirmed successful execution.

Outcome:

Detection successfully identifies account lockout activity for security monitoring and investigation.
