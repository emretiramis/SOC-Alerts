# SOC140 - Phishing Mail Detected - Suspicious Task Scheduler
This alert relates to an email detected and blocked as phishing by email security systems. Further investigation revealed the email contained a PDF attachment.

The PDF file was sent to VirusTotal for analysis and classified as Trojan.PDF.Fraud.AD by various security engines. Dynamic analysis was performed in a sandbox environment to examine the file's behavior in more detail.

According to the ANY.RUN analysis results, when the PDF file is executed, it attempts to communicate with a remote Command and Control (C2) server. The identified C2 address was verified with threat intelligence sources and assessed as malicious infrastructure.

Network and security logs were examined to verify whether a potential infection occurred. The examination revealed that no systems within the corporate network connected to the relevant C2 address. This indicates that the malicious file was not executed or able to communicate.

---

<img width="2173" height="671" alt="image" src="https://github.com/user-attachments/assets/1141dd2b-5a4c-4039-a30a-fdb828617a80" />

