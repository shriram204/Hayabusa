Windows Threat Hunting and Security Event Analysis Using Hayabusa
📌 Project Overview

This project demonstrates Windows security event log analysis and threat hunting using Hayabusa, a Sigma-based Windows event log analysis tool.

The project analyzes the Windows Security Event Log to identify suspicious or security-relevant activities such as local administrator group changes, password reset attempts, successful logons, and credential-related events.

The analysis generates a DFIR timeline, CSV results, and an HTML security report for investigation.

🎯 Objectives
Analyze Windows Security Event Logs.
Perform threat hunting using Hayabusa.
Detect security-relevant Windows events.
Generate a DFIR timeline from .evtx logs.
Identify high, medium, low, and informational alerts.
Investigate important Windows Event IDs.
Generate an HTML security report.
Organize evidence for further investigation.
Document the complete analysis process.
🛠️ Technologies Used
Windows 10
Hayabusa 4.0.0
Windows Event Viewer
Windows Security Event Logs
Sigma Detection Rules
CSV
HTML
Command Prompt
Oracle VirtualBox
GitHub
💻 Environment Setup
Windows 10 Virtual Machine

The analysis was performed inside a Windows 10 virtual machine using Oracle VirtualBox.

The Windows Security Event Log was used as the primary data source for the investigation.

🔧 Hayabusa Setup
Step 1 — Download Hayabusa

Hayabusa Windows x64 version was downloaded and extracted inside:

C:\Hayabusa
Step 2 — Verify Hayabusa

The Hayabusa executable was:

Hayabusa-4.0.0-win-x64.exe

The help and version commands were used to verify the tool.

📁 Windows Security Event Log Collection

The Windows Security Event Log was exported using:

wevtutil epl Security C:\Hayabusa\logs\Security.evtx

The exported log was stored inside the logs directory.

🔍 Security Event Log Analysis

Hayabusa was used to analyze the exported Security Event Log.

DFIR Timeline Generation
Hayabusa-4.0.0-win-x64.exe dfir-timeline -f C:\Hayabusa\logs\Security.evtx -w -o C:\Hayabusa\results\security-timeline.csv

The command generated a CSV-based DFIR timeline containing detected security events.

📊 HTML Security Report

An HTML report was generated for easier investigation:

Hayabusa-4.0.0-win-x64.exe dfir-timeline -f C:\Hayabusa\logs\Security.evtx -w -o C:\Hayabusa\results\security-timeline.csv -H C:\Hayabusa\results\security-report.html

The HTML report provides a summarized view of the detected events and their severity.

🚨 Key Findings

The analysis identified several security-relevant detections.

🔴 High Severity

User Added To Local Admin Grp

Alerts: 2
Indicates activity involving addition of a user to a local administrator/security-enabled group.
Requires investigation to determine whether the activity was authorized.
🟠 Medium Severity

Password Reset By Admin

Alerts: 4
Indicates password reset activity.
Requires investigation to determine whether the action was legitimate.
🟡 Low Severity

Credential Manager Enumerated

Alerts: 11
🔵 Informational

Proc Exec

Alerts: 34

Detection severity indicates that an event should be investigated; it does not by itself prove that malware or an attack occurred.

🔑 Important Windows Event IDs
Event ID	Description
4624	Successful logon
4732	User added to a security-enabled local group
4724	Password reset attempt

These Event IDs were used as important investigation points during the analysis.

📄 Generated Output Files

The project generated the following files:

results.csv
security-timeline-final.csv
security-report.html
README.txt
📂 Project Structure
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
🖼️ Screenshots

Screenshots of the following stages are included in the project:

Windows Security Event Viewer
Hayabusa execution
DFIR timeline generation
HTML security report
High and medium severity detections
Project output files
🔐 Security Considerations

The original Windows Security Event Log may contain sensitive system and user information.

Therefore:

Raw .evtx files should not be uploaded to a public repository.
Sensitive logs should be excluded using .gitignore.
Only sanitized results, screenshots, documentation, and reports should be shared publicly.
📝 Conclusion

Hayabusa was successfully used to analyze Windows Security Event Logs and generate a DFIR timeline and HTML security report.

The project identified high, medium, low, and informational security events that can be further investigated by a security analyst.

This project demonstrates practical knowledge of Windows Event Logs, threat hunting, Sigma-based detection, DFIR timelines, security event investigation, and cybersecurity documentation.
