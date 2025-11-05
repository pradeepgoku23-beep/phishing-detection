Phishing Email Detection Lab in Splunk (Hands-On SOC Analyst Project)

Objective

Detect phishing email patterns by ingesting and analyzing sample email headers in Splunk, extracting important fields, and building a SOC investigation dashboard.


---

Environment Setup

Windows 11 VM — Splunk host and analysis machine

Splunk Enterprise — Installed and running locally (free trial mode)

Sysmon — Installed previously (not required for this lab)

Sample Email Logs — Manually uploaded raw email text files (no mail server integration)



---

Project Summary

This project simulates email-based phishing detection in a SOC environment by manually uploading raw email logs into Splunk and extracting key fields such as From, To, and Subject. The goal is to demonstrate log ingestion, field extraction, SPL query writing, and dashboard creation for SOC monitoring.


---

Data Source

Sample raw email logs with header-like lines, for example:

From: suspicious@phishattack.com
To: user@victim.com
Subject: URGENT – Password Reset Required Immediately

Logs were uploaded manually to Splunk as a text sourcetype.


---

Steps Performed

1) Add Raw Email Logs to Splunk

Uploaded sample email text file into Splunk via Add Data (File upload).

Assigned a sourcetype (e.g., email_raw).


2) Extract Key Fields

Used rex to parse and extract header fields from raw events:

| rex field=_raw "From:\s(?<from>.*)"
| rex field=_raw "To:\s(?<to>.*)"
| rex field=_raw "Subject:\s(?<subject>.*)"

3) Create SPL Queries

Top phishing senders

index=<your_index> sourcetype=email_raw
| rex field=_raw "From:\s(?<from>.*)"
| stats count by from
| sort - count

Top suspicious subject keywords

index=<your_index> sourcetype=email_raw
| rex field=_raw "Subject:\s(?<subject>.*)"
| search subject="*password*" OR subject="*verify*" OR subject="*urgent*" OR subject="*reset*"
| stats count by subject
| sort - count

4) Build Dashboard

Created a simple dashboard with the following panels:

Phishing Email Overview — raw events summary/timechart

Top Email Senders — stats count by from

Top Suspicious Subjects — keyword-based stats


> Note: Alerting was not enabled due to Splunk Free/Trial limitations; dashboards were used for monitoring.




---

Results

Successfully ingested sample email data

Parsed and extracted important header fields

Built a dashboard to monitor phishing indicators

Identified suspicious senders and subject trends



---

Evidence / Screenshots

Screenshots are stored in the screenshots/ folder and include:

data_ingest.png — Splunk Add Data confirmation

field_extraction.png — rex extraction working on sample events

sender_stats.png — Top sender results

dashboard.png — Dashboard view with panels



---

Limitations

No real email server integration (manual ingestion only)

Header-only analysis (no attachment or URL analysis in this iteration)

Alerting disabled/not available due to trial limitations



---
