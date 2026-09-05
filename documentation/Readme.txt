HAYABUSA WINDOWS EVENT LOG ANALAYSIS

Tool:
Hayabusa 4.0.0

Operational System:
Windows 10

Log Analyzed:
Windows Security.evtx

Detection Rules:
Core rules

Key Findings:
1. User Added To Local Admin Grp - High Alert - 2 events
2. Password Reset By Admin - Medium Alert - 4 events 

Important Event IDs:
4732 - User added to a security-enabled local group 
4724 - Password reset attempted 

Output Files:
security-report.html
security-timeline-final.csv
results.csv

Conclusion:
Hayabusa successfully analyzed the Windows Security event log and identified high and medium severity security events for further investigation.