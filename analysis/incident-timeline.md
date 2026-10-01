# Incident Timeline

## Overview

This timeline documents the sequence of events associated with the simulated phishing incident involving Sarah Mitchell.

The timeline is based on the simulated phishing email, IOC analysis, and authentication logs available in this investigation.

At this stage, the timeline indicates suspicious activity following interaction with the phishing email. It does not independently prove that credentials were stolen or that an attacker gained persistent access to the account.

## Timeline

| Time     | Event                                          | Source                               | Analyst Significance                                                                                                             |
| -------- | ---------------------------------------------- | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| 09:12:43 | Successful authentication from `198.51.100.24` | Authentication logs                  | Establishes the known/normal IP address associated with Sarah's account before the suspected phishing activity.                  |
| 09:15:02 | Phishing email received                        | Authentication logs / Email evidence | Marks the beginning of the suspected phishing sequence.                                                                          |
| 09:17:36 | Suspicious authentication link accessed        | Authentication logs                  | Indicates that the recipient interacted with the suspicious link contained in the phishing email.                                |
| 09:18:11 | Successful authentication from `203.0.113.45`  | Authentication logs                  | Unusual authentication from an IP different from Sarah's known normal IP. Occurs shortly after the suspicious link was accessed. |
| 09:19:03 | Failed authentication from `203.0.113.45`      | Authentication logs                  | Indicates continued authentication activity from the unfamiliar IP.                                                              |
| 09:19:22 | Failed authentication from `203.0.113.45`      | Authentication logs                  | A second failed authentication attempt from the same unfamiliar IP.                                                              |
| 09:20:04 | Successful authentication from `203.0.113.45`  | Authentication logs                  | Important because authentication from the unfamiliar IP ultimately succeeded after two failed attempts.                          |

## Key Observations

1. Sarah's known login activity was associated with IP address `198.51.100.24` before the suspected phishing activity.

2. Sarah received the simulated phishing email at 09:15:02.

3. The suspicious authentication link was accessed at 09:17:36, approximately two minutes and thirty-four seconds after the email was received.

4. A successful authentication from the unfamiliar IP `203.0.113.45` occurred at 09:18:11, approximately three minutes and nine seconds after the phishing email was received.

5. Two failed authentication attempts were recorded from `203.0.113.45` before another successful authentication occurred at 09:20:04.

6. The sequence of phishing email receipt, suspicious link access, and unusual successful authentication provides evidence suggesting possible account compromise.

## Current Assessment

Based on the available authentication logs, there is evidence suggesting possible account compromise.

However, the available evidence does not prove that Sarah's credentials were stolen or that the unfamiliar IP address was operated by an attacker.

Further investigation would be required to establish the source and legitimacy of `203.0.113.45` and determine whether unauthorized access occurred.
