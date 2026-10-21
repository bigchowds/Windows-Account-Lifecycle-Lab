# Windows Account Lifecycle Lab

A guided lab using Windows 11 and PowerShell to practise
joiner, mover and leaver account administration.

## Objective

Manage a temporary local account through three employment stages,
verify its status and group memberships, and save evidence as CSV files.

## Tools

- Windows 11
- Windows PowerShell running as Administrator
- Microsoft.PowerShell.LocalAccounts module

## What I did

1. Joiner: created the standard local account LabEmployee01,
   added it to Users and the custom Lab-Sales group.
2. Mover: removed its Lab-Sales membership and added it to Lab-Support.
3. Leaver: disabled the account and removed its Lab-Support membership.
4. Cleanup: deleted the temporary account and both custom lab groups,
   then verified that they no longer existed.

At each employment stage, I checked the account's enabled status
and compared its SID against the members of each lab group.
Each CSV snapshot includes a UTC timestamp.

## Results

| Stage | Account enabled | Sales member | Support member |
| --- | --- | --- | --- |
| Joiner | True | True | False |
| Mover | True | False | True |
| Leaver | False | False | False |

Cleanup checks confirmed that the account and both lab groups were removed.

## Evidence files

- 01-joiner.csv
- 02-mover.csv
- 03-leaver.csv
- 04-cleanup.csv

## What I learned

- How to create, disable and remove a local Windows account.
- How to change group membership when someone's role changes.
- Why old memberships should be removed during a role change.
- How to verify changes and export timestamped evidence.
- The difference between disabling an account and deleting it.

## Scope

This was a local Windows practice exercise using a temporary account.
The custom groups represented departments; no folder permissions
were assigned or tested. The lab did not use Active Directory,
Microsoft Entra ID or Microsoft 365.
