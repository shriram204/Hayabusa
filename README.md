# 🔐 Windows Threat Hunting and Security Event Analysis Using Hayabusa

## 📌 Project Overview

This project demonstrates Windows security event log analysis and threat hunting using **Hayabusa**, a Sigma-based Windows event log analysis tool.

The project analyzes Windows Security Event Logs to identify security-relevant activities such as local administrator group changes, password reset attempts, successful logons, and credential-related events.

The analysis generates a DFIR timeline, CSV results, and an HTML security report for investigation.

---

## 🎯 Objectives

- Analyze Windows Security Event Logs.
- Perform threat hunting using Hayabusa.
- Detect security-relevant Windows events.
- Generate a DFIR timeline from Windows Event Logs.
- Identify high, medium, low, and informational alerts.
- Investigate important Windows Event IDs.
- Generate an HTML security report.
- Organize evidence for further investigation.
- Document the complete analysis process.

---

## 🛠️ Technologies Used

- Windows 10
- Hayabusa 4.0.0
- Windows Event Viewer
- Windows Security Event Logs
- Sigma Detection Rules
- Command Prompt
- CSV
- HTML
- Oracle VirtualBox
- GitHub

---

## 💻 Environment Setup

### Windows 10 Virtual Machine

The project was performed in a Windows 10 virtual machine using **Oracle VirtualBox**.

The Windows Security Event Log was used as the primary data source for the investigation.

---

## 🔧 Hayabusa Setup

### Step 1 — Download and Extract Hayabusa

Hayabusa 4.0.0 Windows x64 was downloaded and extracted to:

`C:\Hayabusa`

The main executable used was:

`Hayabusa-4.0.0-win-x64.exe`

### Step 2 — Verify Hayabusa

The Hayabusa help and version commands were used to verify that the tool was working correctly.

---

## 📁 Windows Security Event Log Collection
🔍 Security Event Log Analysis

Hayabusa was used to analyze the exported Windows Security Event Log.

Step 3 — Generate DFIR Timeline
Hayabusa-4.0.0-win-x64.exe dfir-timeline -f C:\Hayabusa\logs\Security.evtx -w -o C:\Hayabusa\results\security-timeline.csv

This generated a CSV-based DFIR timeline containing security event detections.

📊 HTML Security Report
Step 4 — Generate HTML Report
Hayabusa-4.0.0-win-x64.exe dfir-timeline -f C:\Hayabusa\logs\Security.evtx -w -o C:\Hayabusa\results\security-timeline.csv -H C:\Hayabusa\results\security-report.html

The HTML report provides a summarized view of the detected security events and their severity levels.

🚨 Key Findings
🔴 High Severity

User Added To Local Admin Grp

Alerts: 2
Indicates activity involving addition of a user to a local administrator/security-enabled group.
The activity should be investigated to determine whether it was authorized.
🟠 Medium Severity

Password Reset By Admin

Alerts: 4
Indicates password reset activity.
The activity should be investigated to determine whether it was legitimate.
🟡 Low Severity

Credential Manager Enumerated

Alerts: 11
🔵 Informational

Proc Exec

Alerts: 34

Detection severity indicates that an event should be investigated; it does not by itself prove that malware or an attack occurred.

🔑 Important Windows Event IDs
Event ID	Description
4624	Successful Logon
4732	User Added to a Security-Enabled Local Group
4724	Password Reset Attempt

These Event IDs were used as important investigation points during the analysis.

📄 Generated Output Files

The following output files were generated during the project:

results.csv
security-timeline-final.csv
security-report.html
README.txt

📂PROJECT STRUCTURE


Hayabusa/
│
├── commands/
│   └── hayabusa-commands.txt
│
├── documentation/
│   └── README.txt
│
├── evidence/
│   ├── README.txt
│   ├── results.csv
│   ├── security-report.html
│   └── security-timeline-final.csv
│
├── results/
│   └── security-timeline-final.csv
│
├── reports/
│   └── security-report.html
│
├── screenshots/
│
├── logs/
│
├── rules/
│
└── .gitignore

🔐 Security Considerations

The original Windows Security Event Log may contain sensitive system and user information.

Therefore:

Raw .evtx files should not be uploaded to a public repository.
Sensitive logs are excluded using .gitignore.
Only suitable reports, screenshots, documentation, and sanitized results should be shared publicly.

📝 Conclusion

Hayabusa was successfully used to analyze Windows Security Event Logs and generate a DFIR timeline and HTML security report.

The analysis identified high, medium, low, and informational security events that can be further investigated by a security analyst.

This project demonstrates practical knowledge of:

Windows Event Logs
Threat Hunting
Sigma-based Detection
DFIR Timeline Analysis
Security Event Investigation
Windows Security Monitoring
Cybersecurity Documentation


👨‍💻 Project Purpose

This project was created as a practical cybersecurity project to demonstrate hands-on experience with Windows event log analysis, threat hunting, and digital forensics techniques using Hayabusa.

The Windows Security Event Log was exported using:

```cmd
wevtutil epl Security C:\Hayabusa\logs\Security.evtx
