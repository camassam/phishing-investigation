# Executive Summary

A simulated phishing incident was investigated involving Sarah Mitchell, an employee of Northstar Finance Ltd.

The investigation identified a phishing email that used urgency and a threat of account restriction to encourage the recipient to verify their credentials through an external authentication link. The email contained a sender-domain mismatch and a suspicious authentication URL.

The investigation found that the suspicious authentication link was accessed at 09:17:36, approximately two minutes and thirty-four seconds after the phishing email was received. At 09:18:11, a successful authentication was recorded from `203.0.113.45`, an IP address different from Sarah's known normal IP address of `198.51.100.24`. Two further failed authentication attempts were recorded from the unfamiliar IP, followed by another successful authentication at 09:20:04.

The sequence of phishing email receipt, suspicious link access, and unusual authentication activity provides evidence suggesting possible account compromise.

The incident was assessed as **Medium severity**. Containment and further investigation are recommended; however, the available evidence does not prove that Sarah's credentials were stolen, that unauthorized data was accessed, or that data was exfiltrated.

The IP address `203.0.113.45` was identified as a documentation-only address used within the simulated investigation and should not be interpreted as real malicious infrastructure.

Further investigation would require additional authentication, session, mailbox, application, and data-access logs to determine whether unauthorized activity occurred following the suspicious authentication.
