# Windows SOC Incident Response Lab

## Overview

Hands-on Windows SOC investigation lab focused on security event analysis,
endpoint telemetry, SIEM investigation, and incident response.

## Environment

- Windows 10 virtual machine
- Wazuh SIEM
- Sysmon
- Windows Event Viewer
- PowerShell
- Windows Task Scheduler
- VirtualBox isolated lab environment

## Investigations

### Incident 001 — Failed Logon

Generated controlled failed authentication attempts for a test account and
investigated Windows Security Event ID 4625.

**Evidence:**
- Event ID 4625
- Failed authentication details
- Account: SOCtest
- Logon Type: 2
- Source IP: 127.0.0.1
- Wazuh Rule ID: 60122

**Assessment:** Benign, intentionally generated lab activity.

### Incident 002 — PowerShell Process Investigation

Generated and investigated controlled PowerShell activity and analyzed
Sysmon Event ID 1 process telemetry.

**MITRE ATT&CK:** T1059.001 — PowerShell

**Assessment:** Benign, intentionally generated lab activity.

### Incident 003 — Scheduled Task Investigation

Created a controlled scheduled task and investigated the corresponding
Windows Task Scheduler telemetry.

**MITRE ATT&CK:** T1053.005 — Scheduled Task/Job: Scheduled Task

**Assessment:** Benign, intentionally generated lab activity.

## SIEM Investigation

Integrated the Windows endpoint with Wazuh and investigated centralized
Windows telemetry.

The lab demonstrated:
- Windows event collection
- Wazuh alert investigation
- Sysmon process telemetry
- Scheduled task telemetry
- Evidence collection
- MITRE ATT&CK mapping
- Incident assessment

## Key Skills

- Windows Event Logs
- Wazuh SIEM
- Sysmon
- PowerShell
- Task Scheduler
- Log Analysis
- Incident Response
- MITRE ATT&CK
- Security Monitoring

## Conclusion

This project demonstrates a practical SOC investigation workflow from
event generation and telemetry collection through investigation, evidence
analysis, MITRE ATT&CK mapping, and incident assessment.
