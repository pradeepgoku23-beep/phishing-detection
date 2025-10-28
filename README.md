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

