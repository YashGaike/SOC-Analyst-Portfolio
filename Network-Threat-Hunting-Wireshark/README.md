# Network Threat Hunting & PCAP Analysis

## Overview

Hands-on network threat-hunting investigation using Wireshark and a public
training PCAP to identify suspicious network activity and investigate an
executable transfer.

## Environment

- Wireshark
- Windows 10 virtual machine
- Public training PCAP
- Isolated lab environment

## Investigation

Analyzed a 42,497-packet network capture and investigated DNS, TCP, HTTP,
and TLS traffic to identify suspicious external communications.

## Confirmed Finding

Internal workstation:

`10.10.1.128`

connected to external host:

`107.175.82.242`

over:

`TCP/9000`

The workstation made the following HTTP request:

`GET /wilow/runner_ilove.exe HTTP/1.1`

The server returned the executable with:

- HTTP status: `200 OK`
- Content-Length: `1646592`
- Content-Type: `application/octet-stream`

The response began with the `MZ` signature, indicating a Windows PE
executable.

## Malware Detection

The executable was exported from the HTTP stream using Wireshark.

Windows Defender subsequently quarantined the file and identified it as:

`Trojan:Win64/Zusy.ARAX!MTB`

## Indicators of Compromise

- IP: `107.175.82.242`
- Filename: `runner_ilove.exe`
- URL path: `/wilow/runner_ilove.exe`
- Destination port: `9000`

## MITRE ATT&CK

**T1105 — Ingress Tool Transfer**

## C2 Assessment

The training exercise referenced `195.64.128.106` as a potential C2
indicator. Direct filtering for this IP in Wireshark returned no packets.

Therefore, communication with this address was not independently confirmed
from the captured traffic and was excluded from the confirmed findings.

## SOC Response

1. Isolate the affected workstation.
2. Preserve PCAP and endpoint evidence.
3. Investigate the identified external IP.
4. Search endpoint telemetry for execution of the downloaded file.
5. Review for persistence and follow-on activity.
6. Monitor for additional connections to the identified IOC.

## Key Skills

- Wireshark
- PCAP Analysis
- Network Threat Hunting
- HTTP Traffic Analysis
- IOC Identification
- Executable Extraction
- Malware Detection
- MITRE ATT&CK
- SOC Investigation

## Conclusion

This investigation demonstrates a practical network threat-hunting workflow
using packet analysis, suspicious HTTP traffic identification, executable
extraction, IOC identification, and endpoint malware detection.
