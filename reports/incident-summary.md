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
