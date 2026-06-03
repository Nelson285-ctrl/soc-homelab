# Multiple Failed Logons Detection

## Objective

Detect repeated failed authentication attempts that may indicate password guessing or brute-force activity.

## MITRE ATT&CK

- T1110 - Brute Force

## Data Source

- Windows Security Logs
- Event ID 4625 (Failed Logon)

## SPL Query

```spl
index=main EventCode=4625
| bucket span=5m _time
| stats count by _time Account_Name host
| where count >= 5
```

## Purpose

Identify accounts experiencing multiple failed authentication attempts within a short period of time. Repeated failures may indicate brute-force attacks, password spraying, or user credential issues.

## Investigation Steps

1. Identify the targeted account.
2. Review the source host generating the failed logons.
3. Determine the frequency and duration of failed attempts.
4. Check for successful logons after the failures.
5. Verify whether the activity was expected.
6. Investigate possible brute-force behavior.

## Escalation Criteria

- Multiple accounts targeted.
- High volume of failed authentication attempts.
- Failed logons originating from unusual hosts.
- Successful logon immediately following repeated failures.

## Validation Results

The detection was validated using generated failed logon events within the lab environment.

Observed Results:

- Event ID 4625 collected by Splunk.
- Detection identified multiple failures within a 5-minute period.
- Alert successfully triggered.
- Triggered alerts visible in Splunk.

Outcome:

Detection successfully identifies repeated failed authentication attempts for analyst investigation.
