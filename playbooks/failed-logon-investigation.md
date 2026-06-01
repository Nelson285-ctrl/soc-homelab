# Failed Logon Investigation Playbook

## Objective

Investigate multiple failed authentication attempts to determine whether activity is malicious or expected.

## Detection

- Event ID: 4625
- Alert: Multiple Failed Logons

## Investigation Steps

1. Identify affected account.
2. Review source host.
3. Determine frequency of failed attempts.
4. Check for successful logons after failures.
5. Verify whether the user was entering incorrect credentials.
6. Determine if brute-force activity is occurring.

## Escalation Criteria

Escalate if:

- Multiple accounts are targeted.
- Failed logons originate from unusual systems.
- Successful logons occur immediately after failures.
- Brute-force activity is suspected.

## Containment Actions

- Disable affected account if necessary.
- Reset credentials.
- Review endpoint activity.
- Review Sysmon logs for suspicious processes.
