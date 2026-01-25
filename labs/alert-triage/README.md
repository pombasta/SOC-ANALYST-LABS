# Alert Triage Lab 🚨

## Overview
This lab simulates a SOC Level 1 alert triage scenario where a security analyst investigates a suspicious login alert and determines whether it is a true positive or a false positive.

## Scenario
An alert was triggered due to multiple failed login attempts followed by a successful login from an unfamiliar IP address. The objective is to analyze the alert, review logs, and assess potential security risks.

## Objectives
- Analyze security alerts
- Review authentication logs
- Identify suspicious behavior
- Determine alert severity
- Decide on escalation or closure

## Tools Used
- SIEM (simulated logs)
- Log analysis
- IP reputation checks
- Basic threat intelligence concepts

## Investigation Steps
1. Review the alert details
2. Analyze login attempt patterns
3. Identify source IP address
4. Correlate timestamps and user behavior
5. Determine if activity is malicious

## Findings
- Multiple failed login attempts detected
- Successful login from external IP
- No prior history of this IP for the user
- Behavior indicates possible brute-force attempt

## Conclusion
The alert was classified as a **True Positive**. The incident requires escalation to Tier 2 for further investigation and potential containment actions.

## Skills Demonstrated
- Alert triage
- Log analysis
- Critical thinking
- Incident classification
- SOC Level 1 workflow
