# PowerShell Execution Detection

## Objective

Detect PowerShell execution on monitored endpoints using Sysmon process creation events.

## MITRE ATT&CK

- T1059.001 - PowerShell

## Data Source

- Sysmon Event ID 1 (Process Creation)

## SPL Query

```spl
index=main Sysmon EventCode=1 Image="*powershell.exe"
| table _time host User Image CommandLine ParentImage
'''


## Purpose

Detect execution of PowerShell on monitored endpoints. PowerShell is commonly used for system administration but is also frequently abused by attackers for execution, persistence, and post-exploitation activities.

## Investigation Steps

1. Identify the user who launched PowerShell.
2. Review the CommandLine field for suspicious arguments.
3. Determine the parent process.
4. Verify whether execution was expected.
5. Review surrounding Sysmon activity.

## Escalation Criteria

- Encoded PowerShell commands detected.
- Download or web request activity observed.
- Unusual parent process.
- Execution by unauthorized users.
- Multiple PowerShell executions in a short timeframe.

## MITRE Mapping

| Technique | Description |
|------------|------------|
| T1059.001 | PowerShell |
