# SOC Lab 01 – Kali Failed Login Investigation

## Objective

Investigate multiple failed authentication attempts generated on a Kali Linux endpoint and validate that Wazuh successfully detects, logs, and classifies the activity.

---

## Lab Environment

- Wazuh SIEM v4.14.6
- Kali Linux
- Windows Server 2022 Domain Controller
- Windows 10 Workstation
- VirtualBox
- Syslog
- MITRE ATT&CK Framework

---

## Attack Scenario

As part of a simulated SOC investigation, multiple failed login attempts were intentionally generated on the Kali Linux endpoint by entering an incorrect password several times at the login screen. A successful login was then performed to compare authentication events and verify Wazuh's visibility into the attack sequence.

---

## Investigation Process

The investigation followed these steps:

1. Verified all Wazuh agents were online.
2. Confirmed the Kali endpoint was healthy and actively reporting.
3. Generated multiple failed login attempts.
4. Located the authentication events in Wazuh Threat Hunting.
5. Reviewed event details and MITRE ATT&CK mappings.
6. Correlated failed logins with the subsequent successful login.

---

## Findings

- Multiple failed PAM authentication events were detected.
- Wazuh successfully ingested and parsed the logs.
- Event details included severity, timestamps, authentication information, and MITRE ATT&CK mappings.
- A successful login immediately followed the failed attempts, allowing comparison between failed and successful authentication events.

---

## MITRE ATT&CK

**Technique**
- T1110.001 – Password Guessing

**Tactic**
- Credential Access

---

## Screenshots

1. Wazuh Agents Active
2. Endpoint Health Check
3. Failed Login Generated
4. Kali Failed Login Events
5. Event Details
6. Failed-to-Successful Login Timeline

---

## Skills Demonstrated

- SIEM Investigation
- Wazuh Threat Hunting
- Linux Authentication Analysis
- Log Correlation
- MITRE ATT&CK Mapping
- Security Event Analysis
- Incident Documentation

---

## Outcome

Successfully generated, detected, investigated, and documented failed authentication events using Wazuh SIEM in a home SOC lab environment. This exercise demonstrates the ability to identify authentication failures, analyze security telemetry, correlate related events, and document findings using industry-standard methodologies.
