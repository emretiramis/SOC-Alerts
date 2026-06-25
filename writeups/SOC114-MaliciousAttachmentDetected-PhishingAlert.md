# SOC114 - Malicious Attachment Detected - Phishing Alert

This alert was generated as a result of detecting a phishing email containing a malicious attachment. Investigation revealed the email contained a PowerPoint (.ppt/.pptx) file.

The file's hash value was analyzed on VirusTotal and flagged as a Trojan by several security engines. Dynamic analysis was performed in the ANY.RUN sandbox environment to observe the behavior of the malicious file.

However, because the file was password-protected, it could not be fully run in the sandbox environment, and no behavioral analysis results were obtained. Therefore, no direct malicious activity or Command and Control (C2) communication could be observed.

Due to the limitations of the sandbox analysis, an IOC (Indicator of Compromise) based investigation was conducted, and C2 indicators associated with the malicious file were investigated in the log management system. The investigation revealed outbound connections matching the relevant IOCs.

The analysis determined the endpoint with the IP address 172.16.17.45 as the source system of the connection.

---


