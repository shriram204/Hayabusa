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

