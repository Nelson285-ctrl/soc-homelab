# Account Lockout Investigation Playbook

## Objective

Investigate account lockout events and determine whether they are caused by user error or malicious activity.

## Detection

- Event ID: 4740
- Alert: Account Lockout Detected

## Investigation Steps

1. Identify locked account.
2. Review preceding failed logon events.
3. Identify source workstation.
4. Determine whether lockout was expected.
5. Review authentication activity before lockout.
6. Determine whether brute-force activity occurred.

## Escalation Criteria

Escalate if:

- Multiple lockouts occur.
- Lockouts originate from unexpected hosts.
- High-value accounts are affected.
- Malicious authentication activity is suspected.

## Containment Actions

- Unlock account.
- Reset password.
- Review endpoint activity.
- Review authentication logs.
