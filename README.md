# 🔐 Windows Threat Hunting & Security Event Analysis Using Hayabusa

A practical cybersecurity project focused on **Windows Security Event Log analysis and threat hunting** using **Hayabusa**, a Sigma-based detection tool.

The project analyzes Windows `.evtx` logs to identify security-relevant activities such as **administrator group changes, password reset attempts, successful logons, credential activity, and process execution**.

Hayabusa was used to generate a **DFIR timeline, CSV results, and HTML security report** for investigation.

---

## 🎯 Objectives

* Analyze Windows Security Event Logs
* Perform Sigma-based threat hunting
* Identify suspicious security events
* Investigate important Windows Event IDs
* Generate DFIR timelines and security reports
* Document findings for further investigation

---

## 🧰 Technologies & Tools

| Technology / Tool | Purpose |
|---|---|
| Hayabusa 4.0.0 | Windows event log analysis and threat hunting |
| Sigma Rules | Detection logic |
| Windows 10 | Investigation environment |
| Windows Security Event Logs | Primary forensic data source |
| Windows Event Viewer | Event log review |
| Command Prompt | Log collection and tool execution |
| Oracle VirtualBox | Virtualized Windows environment |
| CSV | Detection and timeline output |
| HTML | Security investigation report |
| GitHub | Project documentation and version control |

---
## 🔍 Project Workflow

```text
Windows 10 Virtual Machine
          ↓
Collect Windows Security Event Logs
          ↓
Export Security.evtx
          ↓
Hayabusa Analysis
          ↓
Sigma-Based Detection Rules
          ↓
Identify Security Events
          ↓
Severity Classification
          ↓
DFIR Timeline Generation
          ↓
CSV & HTML Security Reports
          ↓
Threat Investigation & Analysis
```
## 🔍 Project Workflow Explanation

### 1. Windows 10 Virtual Machine
A Windows 10 virtual machine was created using Oracle VirtualBox to provide a controlled environment for security event analysis.

### 2. Collect Windows Security Event Logs
Windows Security Event Logs were collected to capture activities such as logons, password changes, account modifications, and process execution.

### 3. Export Security.evtx
The Security Event Log was exported as an `.evtx` file using `wevtutil` for forensic analysis.

```cmd
wevtutil epl Security C:\Hayabusa\logs\Security.evtx
```
### 4. Hayabusa Analysis

The exported .evtx file was analyzed using Hayabusa to identify security-relevant events and suspicious activity.

### 5. Sigma-Based Detection Rules

Hayabusa uses Sigma-based detection rules to identify patterns associated with potentially suspicious Windows activities.

### 6. Identify Security Events

Relevant events such as successful logons, administrator group changes, password reset attempts, credential activity, and process execution were identified.

### 7. Severity Classification

Detected events were categorized into High, Medium, Low, and Informational severity levels to prioritize investigation.

### 8. DFIR Timeline Generation

A DFIR timeline was generated to organize detected events chronologically and understand the sequence of activities.

### 9. CSV & HTML Security Reports

The analysis results were exported into CSV and HTML formats for detailed investigation and reporting.

### 10. Threat Investigation & Analysis

Important alerts were reviewed and correlated with other events to determine whether the activity was legitimate, suspicious, or required further investigation.

---

## 🚨 Key Findings

| Severity  | Detection                     | Alerts |
| --------- | ----------------------------- | -----: |
| 🔴 High   | User Added To Local Admin Grp |      2 |
| 🟠 Medium | Password Reset By Admin       |      4 |
| 🟡 Low    | Credential Manager Enumerated |     11 |
| 🔵 Info   | Proc Exec                     |     34 |

### Important Event IDs

* **4624** — Successful Logon
* **4732** — User Added to Security-Enabled Local Group
* **4724** — Password Reset Attempt

> Detection severity indicates investigation priority and does not automatically confirm malicious activity.

---
## 🛡️ Security Recommendations

Based on the event log analysis, the following security recommendations are suggested:

- Regularly monitor Windows Security Event Logs for suspicious activities.
- Investigate unauthorized additions to local administrator groups.
- Monitor password reset and account modification events.
- Enable and monitor **Sysmon** for enhanced endpoint visibility.
- Use a **SIEM such as Wazuh** for centralized log collection and alerting.
- Apply the principle of **least privilege** to user accounts.
- Enable **Multi-Factor Authentication (MFA)** where applicable.
- Regularly review privileged accounts and remove unnecessary access.
- Correlate authentication, process, and network events to identify potential threats.
- Keep Windows systems and security tools regularly updated.

  ---
