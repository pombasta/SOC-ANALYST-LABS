# Phishing Incident Investigation Report

## Incident Overview
- **Incident Type:** Phishing Email
- **Severity:** Medium
- **Status:** Closed
- **Date Identified:** YYYY-MM-DD
- **Reported By:** User / Automated Alert
- **Analyst:** Your Name

---

## Executive Summary
A suspected phishing email was reported to the Security Operations Center (SOC).  
The investigation involved analyzing email headers, sender reputation, embedded URLs, and potential Indicators of Compromise (IOCs).  
The email was confirmed to be **malicious** and appropriate remediation actions were taken.

---

## Email Details
- **Sender Address:** example@malicious-domain.com
- **Sender IP:** XXX.XXX.XXX.XXX
- **Recipient:** user@company.com
- **Subject Line:** Urgent Action Required
- **Attachment / URL:** Yes (Malicious URL)

---

## Investigation Steps

### 1. Email Header Analysis
- Reviewed `Received` fields to trace message origin
- Identified mismatched sender domain and sending IP
- SPF/DKIM/DMARC validation failed

**Findings:**
- Email originated from an untrusted mail server
- Spoofed sender domain detected

---

### 2. URL and Attachment Analysis
- Extracted embedded URLs
- Checked URLs against:
  - VirusTotal
  - URLScan.io
  - Google Safe Browsing

**Findings:**
- URL flagged for credential harvesting
- Domain recently registered (high risk indicator)

---

### 3. Indicator of Compromise (IOCs)
| Type | Value |
|----|----|
| IP Address | XXX.XXX.XXX.XXX |
| Domain | malicious-domain.com |
| URL | hxxp://malicious-domain[.]com/login |
| Email | example@malicious-domain.com |

---

### 4. User Impact Assessment
- User **did not** click the link
- No credentials entered
- No signs of account compromise

---

## MITRE ATT&CK Mapping
- **T1566.001** – Phishing: Spearphishing Attachment
- **T1566.002** – Phishing: Spearphishing Link

---

## Remediation Actions
- Blocked sender domain and IP at email gateway
- Added malicious URL to web filtering blacklist
- Educated user on phishing indicators
- Monitored affected user account for suspicious activity

---

## Lessons Learned
- Importance of user awareness training
- Need for improved email filtering rules
- Early reporting prevented credential compromise

---

## Final Verdict
✅ **Confirmed Phishing Attempt**  
No further action required at this time.

---

## Analyst Notes
This incident highlights common phishing techniques including domain spoofing and credential harvesting links. Rapid user reporting significantly reduced risk.

---
