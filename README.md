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

The Windows Security Event Log was exported using:

```cmd
wevtutil epl Security C:\Hayabusa\logs\Security.evtx
