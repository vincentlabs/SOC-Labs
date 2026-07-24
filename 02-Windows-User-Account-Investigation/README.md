# SOC Lab 02 – Windows User Account Investigation

## Objective

Investigate a Windows Security Event (Event ID 4720) generated when a new Active Directory user account was created and verify whether the activity was legitimate or suspicious.

---

## Lab Environment

- Wazuh SIEM v4.14.6
- Windows Server 2022 Domain Controller
- Active Directory
- Windows 10 Workstation
- VirtualBox
- MITRE ATT&CK Framework

---

## Attack Scenario

As part of a simulated SOC investigation, a new Active Directory user account was intentionally created on the domain controller. Wazuh detected Windows Security Event ID 4720, and the investigation focused on identifying who created the account, verifying the account in Active Directory, and determining whether the activity was authorized.

---

## Investigation Process

1. Searched Wazuh for Event ID 4720.
2. Opened the event details.
3. Identified the Subject User Name (Administrator).
4. Verified the Target User Name (lab.user).
5. Confirmed the account existed in Active Directory.
6. Reviewed the event source, computer name, and timestamp.

---

## Findings

- Windows Security Event ID 4720 was detected.
- Administrator created the account **lab.user**.
- The account was successfully verified in Active Directory.
- The activity matched the expected lab scenario and was authorized.

---

## MITRE ATT&CK

**Technique**

- T1136 – Create Account

**Tactic**

- Persistence

---

## Investigation Screenshots

### 1. Wazuh Search Results
![Wazuh Search](01-Wazuh-Search-EventID-4720.png)

### 2. Event Details
![Event Details](02-Wazuh-EventID-4720-Details.png)

### 3. User Creation Fields
![User Creation](03-User-Creation-Fields.png)

### 4. Active Directory Verification
![Active Directory](04-Active-Directory-User-Verified.png)

### 5. Event Source
![Event Source](05-Event-Source.png)

### 6. Event Timestamp
![Event Timestamp](06-Event-Timestamp.png)

---

## Skills Demonstrated

- SIEM Investigation
- Windows Event Log Analysis
- Active Directory Investigation
- Log Correlation
- MITRE ATT&CK Mapping
- Incident Documentation

---

## Outcome

Successfully investigated and documented a Windows user account creation event using Wazuh and Active Directory. The investigation confirmed the activity was legitimate administrative behavior and demonstrated the process of validating Windows security events in a SOC environment.
