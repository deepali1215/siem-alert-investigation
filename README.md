# siem-alert-investigation
Beginner SIEM investigation using Splunk to analyze authentication logs and identify repeated failed login attempts.
# SIEM Alert Investigation | Splunk Enterprise

## Overview
This project demonstrates a beginner-level Security Information and Event Management (SIEM) investigation using Splunk Enterprise. Synthetic Linux SSH authentication logs were ingested and searched to identify repeated failed login attempts, analyze source IP addresses, and compare failed and successful authentication events.

## Scenario
A security analyst is reviewing authentication activity after noticing repeated failed login attempts. The objective is to investigate the available log data, identify patterns that may indicate password guessing, and document findings without making unsupported conclusions.

## Tools Used
- Splunk Enterprise
- Search Processing Language (SPL)
- Synthetic Linux SSH authentication logs
- Windows

## Investigation Steps

1. Uploaded the sample authentication log file into Splunk Enterprise.
2. Searched indexed events to confirm successful data ingestion.
3. Filtered events containing `Failed password`.
4. Extracted source IP addresses and counted failed attempts by IP.
5. Searched for successful authentication events.
6. Extracted usernames and source IP addresses to create an authentication timeline.

## Key Findings

- **Total events analyzed:** 10
- **Failed login attempts:** 8
- **Successful login events:** 2
- **Failed attempts targeting `analyst`:** 5 from `185.220.101.42`
- **Failed attempts targeting `admin`:** 3 from `203.0.113.45`
- **Successful logins:** 2 for `analyst` from `192.168.1.25`

## Analysis
Repeated failed login attempts against two accounts may indicate password-guessing activity and warrant further investigation. The successful login events originated from a different IP address than the sources associated with the failed attempts.

The available sample data does not establish that an account was compromised or that the successful logins were related to the failed attempts. The addresses and events are part of synthetic training data and should not be treated as evidence of a real attack.

## Evidence
Screenshots documenting the investigation will be stored in the [`evidence`](./evidence/) folder.

- `alert-overview.png` — confirmation that the 10 events were indexed
- `failed-login-search.png` — filtered failed login events
- `source-ip-analysis.png` — failed attempts grouped by source IP
- `successful-logins.png` — successful authentication events
- `investigation-timeline.png` — chronological authentication events with extracted fields

## Skills Demonstrated
- SIEM data ingestion and event searching
- Basic SPL queries
- Filtering and aggregating authentication events
- Extracting fields with regular expressions
- Investigating login patterns and source IP addresses
- Evidence documentation and cautious incident analysis

## Conclusion
This exercise provided hands-on practice using Splunk Enterprise to investigate authentication logs. The findings demonstrate how a security analyst can identify repeated login failures, compare authentication activity, and document evidence while distinguishing observed facts from possible explanations.

**Note:** All logs used in this project were synthetically created for learning purposes.
