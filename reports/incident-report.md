# Executive Summary

A simulated phishing incident was investigated involving Sarah Mitchell, an employee of Northstar Finance Ltd.

The investigation identified a phishing email that used urgency and a threat of account restriction to encourage the recipient to verify their credentials through an external authentication link. The email contained a sender-domain mismatch and a suspicious authentication URL.

The investigation found that the suspicious authentication link was accessed at 09:17:36, approximately two minutes and thirty-four seconds after the phishing email was received. At 09:18:11, a successful authentication was recorded from `203.0.113.45`, an IP address different from Sarah's known normal IP address of `198.51.100.24`. Two further failed authentication attempts were recorded from the unfamiliar IP, followed by another successful authentication at 09:20:04.

The sequence of phishing email receipt, suspicious link access, and unusual authentication activity provides evidence suggesting possible account compromise.

The incident was assessed as **Medium severity**. Containment and further investigation are recommended; however, the available evidence does not prove that Sarah's credentials were stolen, that unauthorized data was accessed, or that data was exfiltrated.

The IP address `203.0.113.45` was identified as a documentation-only address used within the simulated investigation and should not be interpreted as real malicious infrastructure.

Further investigation would require additional authentication, session, mailbox, application, and data-access logs to determine whether unauthorized activity occurred following the suspicious authentication.


## Incident Overview

### Background

The incident began with a simulated phishing email sent to Sarah Mitchell at Northstar Finance Ltd.

The email claimed that Sarah's Microsoft 365 session had expired and instructed her to verify her credentials through an external authentication URL. The message used urgency and the threat of temporary account restriction to encourage immediate action.

The sender address used the domain `northstar-security.example` rather than a Microsoft domain, while the authentication link directed the recipient to `login-northstar-security.example/verify`.

These characteristics resulted in the email being identified as suspicious and prompted further investigation.

### Investigation Objectives

The investigation was conducted to:

1. Identify indicators associated with the suspected phishing email.
2. Determine whether the recipient interacted with the suspicious authentication link.
3. Review authentication activity following the phishing event.
4. Identify unusual authentication sources or patterns.
5. Assess whether the available evidence indicated possible account compromise.
6. Determine appropriate containment and follow-up actions.

### Scope

The investigation focused on the simulated phishing email, identified indicators, authentication activity associated with Sarah Mitchell's account, the incident timeline, and the simulated threat-intelligence assessment of the suspicious IP address.

The available evidence was sufficient to identify suspicious activity and support a Medium severity assessment, but it was not sufficient to confirm credential theft, unauthorized data access, or data exfiltration.


## Evidence Examined

The investigation examined the following evidence sources within the simulated environment.

### 1. Phishing Email

**File:** `evidence/phishing-email.txt`

The simulated email was reviewed for suspicious characteristics including:

- Sender identity and domain
- Subject and message content
- Use of urgency and account-restriction language
- Credential-verification request
- Destination URL

The email contained multiple characteristics associated with phishing and warranted further investigation.

### 2. Indicator of Compromise Analysis

**File:** `analysis/iocs.md`

The IOC analysis identified the following indicators:

| Indicator Type | Indicator | Significance |
|---|---|---|
| Email address | `security@northstar-security.example` | Sender claims to represent Microsoft 365 but uses a different domain |
| Domain | `login-northstar-security.example` | Appears designed to resemble an authentication service |
| URL | `https://login-northstar-security.example/verify` | Directs the recipient to an external authentication page |
| Targeted user | `sarah.mitchell@northstar-finance.example` | Recipient of the suspected phishing email |

These indicators supported the decision to investigate the email further.

### 3. Authentication Logs

**File:** `logs/authentication.log`

The authentication logs were reviewed to identify normal and unusual authentication activity associated with Sarah's account.

The logs established:

- A known successful authentication from `198.51.100.24`.
- Access to the suspicious authentication link at 09:17:36.
- A successful authentication from `203.0.113.45` at 09:18:11.
- Two failed authentication attempts from `203.0.113.45`.
- A subsequent successful authentication from `203.0.113.45` at 09:20:04.

This sequence provided evidence suggesting possible account compromise.

### 4. Incident Timeline

**File:** `analysis/incident-timeline.md`

The timeline was constructed to establish the chronological relationship between the phishing email, link access, and subsequent authentication activity.

The timeline showed that the unusual authentication activity occurred shortly after interaction with the suspicious authentication link.

### 5. Threat Intelligence Assessment

**File:** `analysis/threat-intelligence.md`

The suspicious IP address `203.0.113.45` was assessed within the context of the simulated environment.

The address belongs to a documentation-only IP range and therefore should not be treated as real malicious infrastructure.

The investigation consequently relied on the **context and timing of the authentication activity**, rather than assigning maliciousness to the IP based on reputation.

### Evidence Limitations

The available evidence did not include sufficient information to establish:

- Whether Sarah's credentials were actually captured.
- Whether the successful authentication was performed by an unauthorized individual.
- Whether data was accessed.
- Whether data was exfiltrated.
- Whether the account was used for additional malicious activity.

Additional authentication, session, mailbox, application, and data-access logs would be required to investigate these questions further.
