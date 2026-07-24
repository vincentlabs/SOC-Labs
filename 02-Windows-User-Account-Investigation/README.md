# Windows User Account Investigation

## Objective
Investigate a Windows Security Event (Event ID 4720) in Wazuh to determine whether a newly created user account was legitimate or suspicious.

## Environment
- Wazuh SIEM
- Windows Server 2022 Domain Controller
- Active Directory
- Windows Security Logs

## Alert Information
- Event ID: 4720
- Computer: DC01.cysa.local

## Investigation Summary
A new user account named **lab.user** was created by the **Administrator** account. The event was reviewed in Wazuh, and the account was verified in Active Directory. Since the account was intentionally created during this lab, the activity was determined to be **authorized** and **not malicious**.

## Outcome
- False Positive (Expected Administrative Activity)

## Skills Demonstrated
- Wazuh Investigation
- Windows Event Log Analysis
- Active Directory Verification
- Security Event Correlation
