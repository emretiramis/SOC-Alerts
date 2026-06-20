# 🛡️ SOC Alerts

This repository serves as a professional portfolio documenting my technical methodology, analytical skills, and hands-on experience as a Security Operations Center (SOC) Analyst. It contains detailed writeups of security alert investigations, demonstrating my approach to threat triage, root cause analysis, and incident response.

The core objective of this repository is to showcase my ability to distinguish between True Positives (TP) and False Positives (FP), minimize alert fatigue, and execute precise remediation actions according to standard SOC workflows.

---

## 🛠️ Investigation Techniques & Technical Skills
Across these investigations, I apply an industry-standard analyst workflow that begins with rigorous alert triage and validation across malware, endpoint, and network telemetry to accurately evaluate threat severity and impact. To differentiate between true and false positives, I cross-check file hashes, domains, and URLs using OSINT and threat intelligence platforms like VirusTotal and Filescan.io, while deeply analyzing endpoint telemetry, system logs, process execution trees, and user browsing history. Furthermore, I leverage dynamic analysis tools such as ANY.RUN to sandbox suspicious attachments, extract Indicators of Compromise (IoCs), and correlate network and proxy logs to verify potential Command and Control (C2) communications. Ultimately, this comprehensive approach ensures the effective validation of automated remediation, precise host containment, and thorough threat eradication.

---

## 📂 Investigated Cases (Writeups)

The table below outlines the investigated security incidents. Click on the link in the **Writeup Link** column to view the complete step-by-step technical analysis for each case.

| Case / Alert Type | Verdict | Writeup Link |
| :--- | :--- | :--- | :--- |
| SOC104-Malware Detected | 🔴 True Positive | [📄 View Writeup](./writeups/SOC104-MalwareDetected.md) |
| SOC109-Emotet Malware Investigation | 🔴 True Positive | [📄 View Writeup](./writeups/SOC109-EmotetMalwareDetected.md) |
| SOC119 - Proxy - Malicious Executable File Detected | 🟢 False Positive | [📄 View Writeup](./writeups/SOC119-Proxy-MaliciousExecutableFileDetected.md) |

*Note: As seen in my repository structure shown in `image_968f81.png`, all detailed incident reports are stored natively within the `writeups/` directory.*
