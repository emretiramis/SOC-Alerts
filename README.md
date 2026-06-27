# 🛡️ SOC Alerts

This repository showcases my practical experience and analytical methodology as a SOC Analyst. Modern defensive security requires continuous monitoring, deep log correlation, and rapid incident handling. This portfolio documents my structured process for triaging security alerts, analyzing host and network telemetry, and executing standard incident response workflows to protect enterprise environments from cyber threats.

---

## 📂 Investigated Cases (Writeups)

The table below outlines the investigated security incidents. Click on the link in the **Writeup Link** column to view the complete step-by-step technical analysis for each case.

| No | Case | Type | Verdict | Writeup Link |
| :--- | :--- | :--- | :--- | :--- |
| 011 | *SOC170 - Passwd Found in Requested URL - Possible LFI Attack* | Web Attacks | 🔴 True Positive | [📄 View Writeup](./writeups/SOC170-PasswdFoundinRequestedURL-PossibleLFIAttack.md) |
| 010 | *SOC166 - Javascript Code Detectedin Requested URL* | Web Attacks | 🔴 True Positive | [📄 View Writeup](./writeups/SOC166-JavascriptCodeDetectedinRequestedURL.md) |
| 009 | *SOC114 - Malicious Attachment Detected - Phishing Alert* | Exchange | 🔴 True Positive | [📄 View Writeup](./writeups/SOC114-MaliciousAttachmentDetected-PhishingAlert.md) |
| 008 | *SOC140 - Phishing Mail Detected - Suspicious Task Scheduler* | Exchange | 🔴 True Positive | [📄 View Writeup](./writeups/SOC140-PhishingMailDetected-SuspiciousTaskScheduler.md) |
| 007 | *SOC120 - Phishing Mail Detected - Internal to Internal* | Exchange | 🟢 False Positive | [📄 View Writeup](./writeups/SOC120-PhishingMailDetected-InternaltoInternal.md) |
| 006 | *SOC165 - Possible SQL Injection Payload Detected* | Web Attacks | 🔴 True Positive | [📄 View Writeup](./writeups/SOC165-PossibleSQLInjectionPayloadDetected.md) |
| 005 | *SOC141 - Phishing Url Detected* | Proxy | 🔴 True Positive | [📄 View Writeup](./writeups/SOC141-PhishingUrlDetected.md) |
| 004 | *SOC282 - Phishing Alert-Deceptive Mail Detected* | Exchange | 🔴 True Positive | [📄 View Writeup](./writeups/SOC282-PhishingAlert-DeceptiveMailDetected.md) |
| 003 | *SOC119 - Proxy - Malicious Executable File Detected* | Proxy | 🟢 False Positive | [📄 View Writeup](./writeups/SOC119-Proxy-MaliciousExecutableFileDetected.md) |
| 002 | *SOC109 - Emotet Malware Investigation* | Malware | 🔴 True Positive | [📄 View Writeup](./writeups/SOC109-EmotetMalwareDetected.md) |
| 001 | *SOC104 - Malware Detected* | Malware | 🔴 True Positive | [📄 View Writeup](./writeups/SOC104-MalwareDetected.md) |







*Note: As seen in my repository structure, all detailed incident reports are stored natively within the `writeups/` directory. This repository is updated regularly as I complete new alerts and expand my defensive security skillset.*
