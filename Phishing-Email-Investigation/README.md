# Phishing Email Investigation

## Overview

Hands-on investigation of a phishing email sample using email header
analysis, authentication checks, IOC identification, and threat intelligence.

## Investigation

Analyzed a public training email sample in `.eml` format and examined the
message headers, sender information, authentication results, and embedded
attachment.

## Header Analysis

Key findings included:

- Displayed sender: `support@mail.coinbase.com`
- Recipient: `noreply-KHWG3@mail.authenticatehelp.com`
- Return-Path: `mssggeauthenticl-cbspprt-325937197367@medisept.com.au`
- Message-ID domain: `medisept.com.au`
- Embedded attachment: `Coinbase -15392.docx`

## Email Authentication

Authentication results indicated:

- SPF: None
- DKIM: None
- DMARC: None
- Received-SPF: None

The sending domain did not designate permitted sender hosts.

## Threat Intelligence

Investigated the domain `medisept.com.au` using VirusTotal.

The domain had no detections at the time of investigation. A clean
reputation result alone was not treated as proof that the email was safe.

## Assessment

The email was assessed as:

**LIKELY PHISHING / SUSPICIOUS EMAIL**

The assessment was based on the combination of suspicious sender/recipient
information, authentication failures, return-path inconsistencies, and the
embedded attachment.

## MITRE ATT&CK

**T1566.001 — Phishing: Spearphishing Attachment**

## SOC Response

Recommended actions:

1. Quarantine the suspicious email.
2. Investigate the attachment in an isolated environment.
3. Search for related sender, recipient, domain, and attachment indicators.
4. Block malicious indicators where appropriate.
5. Check for additional messages containing the same indicators.
6. Document the investigation and preserve evidence.

## Key Skills

- Email Header Analysis
- SPF/DKIM/DMARC Analysis
- IOC Identification
- Threat Intelligence
- VirusTotal
- Phishing Investigation
- MITRE ATT&CK
- SOC Incident Analysis

## Conclusion

This investigation demonstrates a practical phishing-analysis workflow from
email header examination and authentication analysis through IOC identification,
threat intelligence, and final SOC assessment.
