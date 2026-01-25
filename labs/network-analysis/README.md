# 🌐 Network Traffic Analysis Lab (Wireshark)

## 🎯 Objective
Analyze network traffic using Wireshark to identify suspicious activity and potential security threats.

---

## 🧪 Scenario
Unusual outbound network traffic was detected from an internal host.  
The SOC team requested packet-level analysis to determine whether the activity is benign or malicious.

---

## 🛠 Tools Used
- Wireshark
- PCAP Traffic Analysis
- TCP/IP, DNS, HTTP Protocols
- SOC Investigation Methodology

---

## 🔍 Investigation Details

- **PCAP Size:** 48 MB  
- **Total Packets Analyzed:** 18,462  
- **Time Range:** 12 minutes  
- **Internal Host IP:** 192.168.1.23  
- **Suspicious External IP:** 185.203.116.45  

---

## 📊 Key Findings

- High volume of DNS queries to a single external domain
- Repeated HTTP POST requests to unknown server
- Beaconing behavior observed every 60 seconds
- Destination IP flagged as suspicious via threat intel

---

## 🧠 Analysis Steps

1. Applied display filters:
   - `ip.addr == 185.203.116.45`
   - `dns`
   - `http.request`
2. Identified abnormal DNS request frequency
3. Inspected HTTP payload sizes
4. Correlated traffic timing patterns

---

## 🧬 MITRE ATT&CK Mapping

| Tactic | Technique ID | Technique Name |
|------|-------------|----------------|
| Command and Control | T1071 | Application Layer Protocol |
| Exfiltration | T1041 | Exfiltration Over C2 Channel |

---

## 🖼 Evidence Screenshots

- Wireshark traffic overview  
- Suspicious external IP communication  
- DNS beaconing pattern  

(See `/screenshots` directory)

---

## ✅ Verdict
**True Positive** – Suspicious outbound communication consistent with command-and-control activity.

---

## 🚨 Recommended Actions
- Isolate affected host
- Block destination IP at firewall
- Perform endpoint malware scan
- Escalate to Incident Response team

---

## 🖥 Interactive HTML Report

➡️ Open the report using HTMLPreview: 
https://htmlpreview.github.io/?https://raw.githubusercontent.com/pombasta/SOC-ANALYST-LABS/main/labs/network-analysis/report.html

https://htmlpreview.github.io/?https://github.com/pombasta/SOC-ANALYST-LABS/blob/main/labs/network-analysis/report.html

