# Network Traffic Analysis – HTTP Investigation Using Wireshark

## Lab Overview
- **Analysis Type:** Network Traffic Analysis
- **Protocol:** HTTP
- **Tool Used:** Wireshark
- **Objective:** Identify suspicious HTTP activity and extract Indicators of Compromise (IOCs)

---

## Scenario
The SOC received an alert indicating potential malicious network activity involving unencrypted HTTP traffic.  
A packet capture (PCAP) file was provided for analysis to determine whether sensitive data or malicious communication occurred.

---

## Investigation Objectives
- Identify HTTP traffic within the capture
- Analyze HTTP requests and responses
- Detect suspicious URLs, downloads, or credential exposure
- Extract relevant IOCs

---

## Environment & Tools
- **Wireshark Version:** X.X.X
- **Operating System:** Windows / Linux
- **PCAP Source:** Simulated lab traffic

---

## Analysis Process

### 1. Filtering HTTP Traffic
Applied the following Wireshark display filter:


This filter isolates all HTTP traffic for focused analysis.

---

### 2. Identifying Suspicious HTTP Requests
Reviewed HTTP `GET` and `POST` requests for:
- Unusual domains
- IP-based URLs
- Suspicious file downloads
- Login or credential submission attempts

**Example Filter Used:**

**Findings:**
- Multiple HTTP requests sent to unknown external IP addresses
- Requests observed without TLS encryption

---

### 3. HTTP POST & Credential Analysis
Applied filter to identify POST requests:


**Observations:**
- POST requests containing form data
- Potential transmission of credentials in cleartext

⚠️ **Security Risk:** HTTP traffic is unencrypted, allowing attackers to intercept sensitive information.

---

### 4. File Download Detection
Filtered for suspicious file transfers:


**Findings:**
- Download of executable file (`.exe`)
- File delivered over HTTP instead of HTTPS

---

### 5. Follow HTTP Stream
Used **Follow → HTTP Stream** to reconstruct sessions.

**Results:**
- Complete visibility of client-server communication
- Identified malicious payload delivery
- Extracted URLs and User-Agent strings

---

## Indicators of Compromise (IOCs)

| Type | Value |
|----|----|
| Source IP | 192.168.X.X |
| Destination IP | XXX.XXX.XXX.XXX |
| Malicious URL | hxxp://malicious-site[.]com/payload.exe |
| User-Agent | SuspiciousUserAgent/1.0 |

---

## MITRE ATT&CK Mapping
- **T1040** – Network Sniffing
- **T1071.001** – Application Layer Protocol: Web Protocols
- **T1105** – Ingress Tool Transfer

---

## Security Impact
- Cleartext HTTP traffic exposes sensitive data
- Malicious payload delivered without encryption
- Increased risk of man-in-the-middle (MITM) attacks

---

## Remediation Recommendations
- Enforce HTTPS across all web traffic
- Block malicious IPs and domains at firewall
- Deploy IDS/IPS for network traffic inspection
- Educate users on risks of unsecured websites

---

## Conclusion
The analysis confirmed **suspicious HTTP activity**, including cleartext credential transmission and malicious file download.  
This highlights the importance of encrypted communications and proactive network monitoring.

---

## Analyst Notes
Wireshark is a powerful tool for network-level visibility. HTTP traffic should always be treated as high-risk due to lack of encryption.

---

**Findings:**
- Download of executable file (`.exe`)
- File delivered over HTTP instead of HTTPS

---

### 5. Follow HTTP Stream
Used **Follow → HTTP Stream** to reconstruct sessions.

**Results:**
- Complete visibility of client-server communication
- Identified malicious payload delivery
- Extracted URLs and User-Agent strings

---

## Indicators of Compromise (IOCs)

| Type | Value |
|----|----|
| Source IP | 192.168.X.X |
| Destination IP | XXX.XXX.XXX.XXX |
| Malicious URL | hxxp://malicious-site[.]com/payload.exe |
| User-Agent | SuspiciousUserAgent/1.0 |

---

## MITRE ATT&CK Mapping
- **T1040** – Network Sniffing
- **T1071.001** – Application Layer Protocol: Web Protocols
- **T1105** – Ingress Tool Transfer

---

## Security Impact
- Cleartext HTTP traffic exposes sensitive data
- Malicious payload delivered without encryption
- Increased risk of man-in-the-middle (MITM) attacks

---

## Remediation Recommendations
- Enforce HTTPS across all web traffic
- Block malicious IPs and domains at firewall
- Deploy IDS/IPS for network traffic inspection
- Educate users on risks of unsecured websites

---

## Conclusion
The analysis confirmed **suspicious HTTP activity**, including cleartext credential transmission and malicious file download.  
This highlights the importance of encrypted communications and proactive network monitoring.

---

## Analyst Notes
Wireshark is a powerful tool for network-level visibility. HTTP traffic should always be treated as high-risk due to lack of encryption.

---
