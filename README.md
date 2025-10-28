\# Phishing Email Detection \& Analysis — Splunk Home Lab



\*\*Author:\*\* Pradeep Kumar  

\*\*Project Type:\*\* SOC Analyst Home Lab  

\*\*Tools:\*\* Splunk, Windows VM, Sysmon, Sample Email Logs  

\*\*Date:\*\* 2025



---



\## 📌 Project Overview

In this lab, I simulated phishing email detection using Splunk.  

I ingested sample email logs, extracted key fields (From, To, Subject), and built a dashboard to visualize suspicious email activity.



This project demonstrates skills in:

\- Log ingestion

\- Field extraction (regex)

\- Email header analysis

\- Dashboard creation

\- Threat detection concepts



---



\## ✅ Objectives

\- Ingest `.eml`-style email logs into Splunk

\- Extract important email fields

\- Visualize trends \& suspicious senders

\- Perform basic phishing investigation

\- Build a reusable SOC dashboard



---



\## 🛠️ Steps Performed

1\. Installed \& configured Splunk in Windows VM  

2\. Uploaded phishing-sample email logs  

3\. Applied sourcetype `generic\_email`  

4\. Extracted fields using `rex` (From, To, Subject)  

5\. Built dashboard:  

&nbsp;  - Phishing Email Overview (Table)  

&nbsp;  - Top Senders (Bar Chart)  

&nbsp;  - Top Suspicious Subjects (Pie Chart)  

6\. Verified extracted fields on events  

7\. Saved searches for alert simulation



---



\## 📊 Dashboard Preview

Screenshots are in `/screenshots/`:



\- `dashboard\_full.png` — full phishing dashboard  

\- `email\_event\_detail.png` — raw event with extracted fields



---



\## 🔎 Key SPL Queries

All queries are stored in `spl/queries.txt`.



Example field extraction: 

Phishing Email Detection - Project Summary

Project Objective

Simulated phishing email detection using Splunk as part of SOC analyst home lab setup.

Tasks Performed

Ingested sample phishing email logs into Splunk

Extracted key email fields (From, To, Subject) using regex (rex SPL command)

Created dashboards to visualize suspicious email patterns

Built detection logic to identify phishing indicators

Created alerts to notify on suspicious senders or subjects


Key Skills Demonstrated

Log ingestion and parsing

Regex-based field extraction in Splunk

Dashboard and visualization creation

Alert rule creation

Threat analysis and phishing investigation


Techniques Used

Splunk search queries

rex command for field extraction

Statistical functions and table formatting

Dashboard XML UI builder

Suspicious pattern identification


Files Included

File/Folder	Description

queries.txt	All Splunk search queries used for detection and dashboarding
screenshots/	Dashboard output and field extraction proof screenshots
.gitignore	Ignore OS/editor logs and temporary files


Result

Successfully built a phishing detection dashboard in Splunk that highlights:

Suspicious sender accounts

Frequent phishing subjects

Email traffic patterns related to phishing


