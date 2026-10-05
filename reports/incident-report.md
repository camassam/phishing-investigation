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

## Findings and Analysis

### Finding 1 — Phishing Characteristics

The email contains several characteristics associated with phishing.

The sender claims to represent Microsoft 365 but uses the domain `northstar-security.example`. The message also creates urgency by stating that the user's session has expired and warning of temporary account restrictions.

The recipient is instructed to verify credentials through an external authentication URL.

These characteristics provide sufficient reason to treat the email as suspicious and investigate it further.

### Finding 2 — User Interaction with the Suspicious Link

The authentication logs record that the suspicious authentication link was accessed at **09:17:36**.

The phishing email was received at **09:15:02**, meaning the link was accessed approximately **2 minutes and 34 seconds** after the email was received.

This establishes a temporal relationship between receipt of the phishing email and interaction with the suspicious authentication page.

### Finding 3 — Unusual Authentication Activity

A successful authentication occurred at **09:18:11** from `203.0.113.45`.

This differs from Sarah's known successful authentication source of `198.51.100.24`.

The timing is significant because the unusual authentication occurred approximately **3 minutes and 9 seconds** after the phishing email was received and shortly after the suspicious link was accessed.

### Finding 4 — Repeated Authentication Attempts

Following the successful authentication at 09:18:11, two failed authentication attempts were recorded from the same unfamiliar IP address:

- **09:19:03 — FAILED**
- **09:19:22 — FAILED**

A further successful authentication then occurred at:

- **09:20:04 — SUCCESS**

The sequence of successful and failed authentication attempts increases concern because authentication from the unfamiliar IP ultimately succeeded again.

### Finding 5 — IP Address Assessment

The IP address `203.0.113.45` belongs to a documentation-only address range used within the simulated investigation.

Therefore, the IP address itself cannot be treated as evidence of known malicious infrastructure.

The significance of the address comes from its **difference from Sarah's known authentication source and its timing within the phishing sequence**, rather than from an external malicious-IP reputation.

### Overall Analysis

Taken together, the evidence shows a sequence of events consistent with possible account compromise:

**Phishing email received → suspicious link accessed → unusual successful authentication → failed authentication attempts → subsequent successful authentication**

This correlation provides sufficient evidence to justify containment and further investigation.

However, the available evidence does not establish that Sarah's credentials were stolen, that an attacker controlled the unfamiliar IP, or that organizational data was accessed or exfiltrated.

## Incident Response and Containment

Based on the current evidence, the incident should be treated as a suspected account compromise requiring containment and further investigation.

### Immediate Containment

The following actions are recommended:

1. **Reset Sarah's account password**

   Reset the affected user's password to reduce the risk of continued unauthorized authentication.

2. **Revoke active sessions**

   Where supported by the organization's identity platform, revoke active sessions and authentication tokens associated with the account.

3. **Review authentication activity**

   Investigate authentication and session logs for additional unfamiliar IP addresses, locations, devices, or unusual login patterns.

4. **Review account and mailbox activity**

   Examine available logs for suspicious account changes, mailbox activity, unexpected application access, or other actions that occurred following the unusual authentication.

5. **Preserve evidence**

   Preserve the phishing email, authentication logs, IOC analysis, timeline, and other relevant investigation data before making changes that could affect the evidence.

### Phishing Containment

The suspected phishing source should be investigated before applying broader email-security controls.

If the sender or domain is confirmed to be malicious, appropriate controls could be used to prevent similar messages from reaching other users.

The original phishing email should be retained as evidence before removing or blocking messages.

### User Awareness

Sarah should receive appropriate security guidance regarding phishing indicators, including:

- Unexpected requests to verify credentials.
- Messages that create urgency or fear.
- Links leading to unfamiliar authentication domains.
- Sender addresses that do not match the service being referenced.

User education should form part of the prevention and lessons-learned process rather than replacing technical containment.

### Further Investigation

Additional investigation should focus on determining whether unauthorized activity occurred after the suspicious authentication.

Recommended evidence to review includes:

- Authentication and session logs.
- Identity-provider activity.
- Mailbox audit logs.
- Application access logs.
- Account and security-setting changes.
- File or data-access logs.
- Evidence of additional authentication activity.

The objective is to determine whether the account was accessed by an unauthorized party and whether any organizational data was accessed or exfiltrated.

### Response Priority

The response should prioritize:

**Contain → Preserve → Investigate → Remediate → Educate**

Containment reduces the potential for continued unauthorized access, while evidence preservation ensures that the investigation can continue without unnecessarily altering relevant evidence.

## Conclusion and Recommendations

### Conclusion

The investigation identified a simulated phishing email containing multiple characteristics associated with phishing, including a sender-domain mismatch, urgency, a threat of account restriction, and a request to verify credentials through an external authentication URL.

The evidence shows that the suspicious authentication link was accessed and that unusual authentication activity subsequently occurred from `203.0.113.45`.

The sequence of events provides evidence suggesting possible account compromise and justifies containment and further investigation.

The incident is therefore assessed as **Medium severity**.

However, the investigation does not establish that Sarah's credentials were definitely stolen, that the unfamiliar IP represents a real attacker, or that organizational data was accessed or exfiltrated.

### Recommendations

The following actions are recommended:

1. **Secure the affected account**
   - Reset Sarah's password.
   - Revoke active sessions and authentication tokens where supported.

2. **Continue investigation**
   - Review authentication and session activity.
   - Examine mailbox and application audit logs.
   - Review account and security-setting changes.
   - Investigate potential data-access activity.

3. **Preserve evidence**
   - Retain the original phishing email.
   - Preserve authentication logs and investigation records.
   - Maintain the incident timeline and IOC documentation.

4. **Strengthen phishing defenses**
   - Investigate the sender and associated domain.
   - Apply appropriate email-security controls if malicious activity is confirmed.
   - Consider additional phishing detection and awareness measures.

5. **Improve user awareness**
   - Provide targeted guidance to the affected user.
   - Reinforce awareness of suspicious authentication requests, urgent messages, and unfamiliar domains.

### Final Assessment

**Incident classification:** Suspected account compromise  
**Severity:** Medium  
**Confidence:** Moderate

The available evidence is sufficient to justify containment and additional investigation, but further evidence is required before confirming credential theft, unauthorized data access, or data exfiltration.
