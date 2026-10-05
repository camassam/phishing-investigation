# Incident Assessment

## Incident Summary

The investigation identified a suspected phishing email sent to Sarah Mitchell, followed by interaction with the embedded authentication link and unusual authentication activity from an unfamiliar IP address.

The available evidence indicates **suspected unauthorized access** and warrants further investigation and containment.

## Severity Assessment

**Severity: Medium**

The incident is assessed as Medium because there is evidence of suspicious activity that may indicate account compromise, but there is currently insufficient evidence to confirm unauthorized account takeover, data access, or data exfiltration.

The assessment is based on the following factors:

- Sarah received a suspected phishing email.
- The suspicious authentication link was accessed.
- A successful authentication occurred from an unfamiliar IP address shortly afterward.
- Additional failed authentication attempts occurred from the same IP.
- A subsequent successful authentication occurred from that IP.
- Further investigation and containment are therefore warranted.

## Key Evidence

The strongest evidence is the correlation between the phishing activity and subsequent authentication activity.

The sequence was:

1. Phishing email received at 09:15:02.
2. Suspicious authentication link accessed at 09:17:36.
3. Successful authentication from `203.0.113.45` at 09:18:11.
4. Two failed authentication attempts from the same IP.
5. Successful authentication from `203.0.113.45` at 09:20:04.

This sequence is suspicious because the unusual authentication activity occurred shortly after the phishing link was accessed.

## Immediate Response Recommendations

The following actions would be appropriate while the investigation continues:

### 1. Secure the Account

Reset Sarah's password and require reauthentication to help prevent continued unauthorized access.

If supported by the organization's identity platform, revoke active sessions and authentication tokens associated with the account.

### 2. Investigate Account Activity

Review authentication, session, mailbox, and application logs to determine whether unauthorized actions occurred after the suspicious authentication.

Particular attention should be given to:

- unusual mailbox activity
- account or security-setting changes
- unexpected application access
- suspicious file or data access
- additional unfamiliar authentication activity

### 3. Preserve Evidence

Preserve the phishing email, authentication logs, IOC information, and investigation timeline before modifying or deleting evidence.

This allows the incident to be reconstructed and reviewed later.

### 4. Investigate and Contain the Phishing Source

Review the sender and domain associated with the phishing email.

If the investigation confirms that the sender is malicious, appropriate email-security controls can be used to prevent additional messages from reaching organizational users.

## User Awareness

Sarah should receive appropriate guidance on recognizing phishing emails, particularly messages that:

- create urgency or fear,
- request credential verification,
- contain unexpected authentication links,
- use domains that do not match the organization or claimed service.

User awareness should be treated as a preventive measure and lessons-learned activity rather than as a replacement for technical containment.

## Evidence Limitations

The current evidence does not establish:

- that Sarah's credentials were definitely stolen,
- that `203.0.113.45` represents a real attacker,
- that unauthorized data was accessed,
- that data was exfiltrated,
- or that the account was permanently compromised.

The IP address used in this simulation is a documentation-only address and should not be interpreted as real malicious infrastructure.

Additional authentication, session, mailbox, application, and data-access logs would be required to determine whether unauthorized activity occurred after authentication.

## Current Assessment

**Assessment: Suspected account compromise — Medium severity**

There is sufficient evidence to justify containment and further investigation, but insufficient evidence to confirm credential theft, unauthorized data access, or data exfiltration.
