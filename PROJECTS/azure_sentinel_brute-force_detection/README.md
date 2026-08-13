# Cloud Incident Response Environment with Microsoft Sentinel
This project demonstrates the design and implementation of a cloud-based security monitoring and incident response environment using Microsoft Azure and Microsoft Sentinel. The environment was created to simulate authentication-based attacks, collect logs from Linux and Windows systems, and detect suspicious behavior using Kusto Query Language (KQL).
The project focuses on identifying brute-force and failed authentication attempts through centralized logging, pattern-based detection, and automated alert generation.

## Project Objectives
-Build a cloud-based monitoring environment in Microsoft Azure
-Simulate authentication-based attacks
-Collect and centralize logs using Azure Monitor and Log Analytics
-Detect suspicious activity using KQL queries
-Generate alerts using Microsoft Sentinel analytic rules
-Analyze authentication-based attack behavior

## Architecture Overview
<img width="331" height="851" alt="projectarchitecture1" src="https://github.com/user-attachments/assets/2721812d-f945-4896-84bb-9c9b24550b84" />

## Environment Components
<img width="658" height="268" alt="gitcopy" src="https://github.com/user-attachments/assets/1aa3cdec-b61d-4ae2-b279-1b643dfa4864" />

| Component                         | Purpose                         |
| --------------------------------- | ------------------------------- |
| Microsoft Azure                   | Cloud infrastructure platform   |
| Microsoft Sentinel                | SIEM and incident monitoring    |
| Log Analytics Workspace           | Centralized log storage         |
| Ubuntu Linux VM (`attackmachine`) | Simulated attack system         |
| Windows VM (`targetmachine`)      | Monitored target system         |
| Azure Monitor Agent (AMA)         | Log forwarding                  |
| Data Collection Rule (DCR)        | Defines log collection behavior |

## Detection Scenarios
1. Linux SSH Brute-Force Detection
The Linux detection scenario focused on identifying repeated failed SSH login attempts originating from the same IP address within a short time period.

Detection Logic
  + Analyze Linux syslog data
  + Identify repeated failed SSH login attempts
  + Group failed attempts by source IP address
  + Detect suspicious thresholds

2. Windows Failed Login Detection
The Windows detection scenario focused on identifying repeated failed authentication attempts using Windows Security Event logs.

Detection Logic
 + Analyze Event ID 4625
 + Group failed login attempts by account and system
 + Detect repeated failures within a five-minute interval
 + Identify potential credential guessing behavior

## Alert Automation
Analytic rules were configured in Microsoft Sentinel to automate detection and generate alerts when suspicious authentication patterns were identified.

Automated Detection Features
 + Threshold-based alerting
 + Real-time log monitoring
 + Pattern-based detection
 + Automated incident generation

## Key Findings
- Centralized logging improves visibility across systems
- Authentication-based attacks can be identified through pattern analysis
- KQL enables efficient detection of suspicious behavior
- Automated alert generation improves monitoring efficiency
- Public-facing systems are continuously targeted by external authentication attempts

## Skills Demonstrated
- Cloud Security
- Microsoft Azure
- Microsoft Sentinel
- Log Analysis
- Kusto Query Language (KQL)
- Detection Engineering
- Security Monitoring
- Incident Analysis
- Threat Detection

## References

- [1] Microsoft, “Kusto Query Language (KQL) overview,” Microsoft Learn, Mar. 6, 2025. [Online]. Available: https://learn.microsoft.com/en-us/kusto/query/?view=microsoft-fabric
- [2] Microsoft, “Log Analytics tutorial - Azure Monitor,” Microsoft Learn, Jul. 30, 2025. [Online]. Available: https://learn.microsoft.com/en-us/azure/azure-monitor/logs/log-analytics-tutorial
- [3] Microsoft, “KQL quick reference,” Microsoft Learn, Sep. 15, 2025. [Online]. Available: https://learn.microsoft.com/en-us/kusto/query/kql-quick-reference?view=microsoft-fabric
- [4] Microsoft Threat Intelligence Center, “Brute Force: Password Guessing, Sub-technique T1110.001,” MITRE ATT&CK®, Feb. 11, 2020. [Online]. Available: https://attack.mitre.org/techniques/T1110/001/
- [5]  Microsoft, “Microsoft Sentinel documentation,” Microsoft Learn, Apr. 22, 2026. [Online]. Available: https://learn.microsoft.com/en-us/azure/sentinel/
- [6]  P. Cichonski, T. Millar, T. Grance, and K. Scarfone, “Computer Security Incident Handling Guide,” NIST Special Publication 800-61 Rev. 2, Aug. 2012. [Online]. Available: https://doi.org/10.6028/NIST.SP.800-61r2
