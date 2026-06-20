# 🛡️ SOC Alerts

This repository showcases my practical experience and analytical methodology as a SOC Analyst. Modern defensive security requires continuous monitoring, deep log correlation, and rapid incident handling. This portfolio documents my structured process for triaging security alerts, analyzing host and network telemetry, and executing standard incident response workflows to protect enterprise environments from cyber threats.

---

## 🎯 Objectives

The primary goal of this repository is to showcase a structured and effective approach to Security Operations and Incident Response. The core objectives include:
* **Alert Validation & Triage:** Analyze endpoint and network logs to quickly separate True Positives (TP) from False Positives (FP) and reduce alert fatigue.
* **Identity Monitoring:** Investigate authentication logs and monitor Active Directory components (such as domain objects and security groups) to detect unauthorized access or lateral movement.
* **Web Application Defense:** Analyze proxy logs and web traffic to identify malicious activities, including automated scanning or database injection attacks.
* **Threat Intelligence & Automation:** Correlate internal alerts with external Threat Intelligence (OSINT, IoCs) and use Python to automate log parsing and data enrichment.
* **Malware & Artifact Analysis:** Use sandbox environments and endpoint logs to analyze malicious files, extract indicators, and detect Command & Control (C2) connections.
* **Incident Containment:** Execute precise response actions like host isolation or IP blocking, and provide recommendations to improve detection rules.

---

## 📂 Investigated Cases (Writeups)

The table below outlines the investigated security incidents. Click on the link in the **Writeup Link** column to view the complete step-by-step technical analysis for each case.

| Case / Alert Type | Verdict | Writeup Link |
| :--- | :--- | :--- |
| SOC104-Malware Detected | 🔴 True Positive | [📄 View Writeup](./writeups/SOC104-MalwareDetected.md) |
| SOC109-Emotet Malware Investigation | 🔴 True Positive | [📄 View Writeup](./writeups/SOC109-EmotetMalwareDetected.md) |
| SOC119 - Proxy - Malicious Executable File Detected | 🟢 False Positive | [📄 View Writeup](./writeups/SOC119-Proxy-MaliciousExecutableFileDetected.md) |

*Note: As seen in my repository structure, all detailed incident reports are stored natively within the `writeups/` directory.*
