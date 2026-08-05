# Lab 09: PowerShell Execution Investigation (Windows Event ID 4688)

## Objective

Investigate a PowerShell process creation event detected by Wazuh. Review the process details, analyze the associated detection rule, and determine whether the activity represents legitimate administrative behavior or malicious activity.

---

## Technologies Used

- Wazuh SIEM
- Windows Security Logs
- Windows 10
- Windows Server 2022
- Active Directory

---

## Investigation Steps

### Step 1 – Detect the PowerShell Process

Generated a PowerShell process on WKSTN01 and confirmed Wazuh detected the process creation event.

**Screenshot**

![01-PowerShell-Process-Creation-Alert](01-PowerShell-Process-Creation-Alert.png)

---

### Step 2 – Review Event Details

Reviewed the process creation event and identified the endpoint, parent process, user account, and process information.

**Findings**

- Event ID: **4688**
- Computer: `WKSTN01.cysa.local`
- Agent: `WKSTN01`
- Parent Process: `powershell.exe`
- Child Process: `conhost.exe`
- User: `CYSA\socanalyst`

**Screenshot**

![02-PowerShell-Process-Details](02-PowerShell-Process-Details.png)

---

### Step 3 – Review Detection Rule

Reviewed the Wazuh detection rule associated with the event.

**Findings**

- Rule ID: **67027**
- Rule Level: **3**
- Description: **A process was created.**
- Event Source: Windows Security Logs

**Screenshot**

![03-PowerShell-Rule-Details](03-PowerShell-Rule-Details.png)

---

## Investigation Findings

The investigation confirmed that Wazuh successfully detected a Windows Security Event ID 4688 generated on WKSTN01. Analysis showed the PowerShell process launched `conhost.exe`, which is expected behavior during normal PowerShell execution. The activity originated from the `CYSA\socanalyst` account and was intentionally performed as part of this SOC home lab.

No suspicious command-line arguments, unauthorized user activity, or indicators of compromise were identified.

---

## Conclusion

This investigation determined that the PowerShell process creation event represented legitimate administrative activity. The event was intentionally generated to validate Windows Security logging and Wazuh detection capabilities. No malicious behavior was observed, and the investigation was closed as expected administrative activity.

---

## Skills Demonstrated

- Wazuh SIEM Investigation
- Windows Security Event Analysis
- Windows Process Analysis
- PowerShell Investigation
- Event ID 4688 Analysis
- Blue Team Investigation
- Security Monitoring
