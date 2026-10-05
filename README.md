# Phishing Investigation & Incident Response

## Project Overview

This project is a controlled cybersecurity investigation simulating a phishing incident within a fictional organisation.

The project demonstrates a SOC-style investigation process, including:

- Phishing email analysis
- Identification of indicators of compromise (IOCs)
- Authentication log analysis
- Incident timeline development
- Threat intelligence analysis
- MITRE ATT&CK mapping
- Incident response and remediation recommendations

## Objective

The objective of this project is to investigate whether a simulated phishing email resulted in potential account compromise and to document the investigation from initial detection through to incident response.

## Environment

This project uses fictional data and a controlled environment for educational and portfolio purposes.

Tools and technologies will be documented as the investigation develops.

## Investigation Process

The investigation will follow these stages:

1. Phishing email analysis
2. IOC identification
3. Threat intelligence investigation
4. Authentication log analysis
5. Timeline construction
6. MITRE ATT&CK mapping
7. Incident assessment
8. Incident response
9. Remediation recommendations

## Disclaimer

This project is entirely fictional and is intended for educational and portfolio purposes.

No real users, credentials, organisations, or production systems are being targeted.

## Key Findings

The investigation identified a simulated phishing email containing multiple suspicious characteristics, including:

- A sender-domain mismatch.
- Urgency and account-restriction language.
- A request to verify credentials through an external authentication URL.
- Suspicious authentication activity shortly after the link was accessed.
- Successful authentication from an unfamiliar IP address followed by additional authentication attempts.

The incident was assessed as **Medium severity**, with evidence suggesting possible account compromise.

The investigation did not establish that credentials were definitely stolen, that the unfamiliar IP represented a real attacker, or that organizational data was accessed or exfiltrated.

## Project Structure

```text
phishing-investigation/
│
├── evidence/
│   └── phishing-email.txt
│
├── analysis/
│   ├── iocs.md
│   ├── incident-timeline.md
│   ├── threat-intelligence.md
│   └── incident-assessment.md
│
├── logs/
│   └── authentication.log
│
└── reports/
    └── incident-report.md
```

### Detailed Report

The complete investigation and incident-response assessment can be found in:

`reports/incident-report.md`

## Status

✅ Completed — simulated phishing investigation and incident-response analysis
