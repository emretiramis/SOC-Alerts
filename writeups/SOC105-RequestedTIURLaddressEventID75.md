# 	SOC105 - Requested T.I. URL address EventID 75

This alert was triggered due to a connection attempt to the URL bit[.]ly/TAPSCAN, which redirected traffic through the IP address 67[.]199[.]248[.]10. The investigation focused on identifying any indicators of compromise (IOC) related to the destination IP, URL, and endpoint activity.

---

<img width="2278" height="444" alt="image" src="https://github.com/user-attachments/assets/e89ff5c4-7f54-47fa-8bd4-2a490a420b09" />

Investigated the destination IP address (67[.]199[.]248[.]10) using threat intelligence sources.

<img width="900" height="587" alt="image" src="https://github.com/user-attachments/assets/9f99b177-783a-4918-8f71-95174a1cdd5e" />

<img width="2560" height="1080" alt="image" src="https://github.com/user-attachments/assets/32c37c52-275b-494e-9645-2148092a89dd" />

Analyzed the shortened URL (bit[.]ly/TAPSCAN) for malicious reputation or known phishing/malware associations.

<img width="2560" height="1093" alt="image" src="https://github.com/user-attachments/assets/2fb90bea-1177-4bea-b96a-85b5f02f4286" />

Reviewed endpoint security logs generated on the date of the alert.

<img width="1438" height="465" alt="image" src="https://github.com/user-attachments/assets/6de0fd38-4142-4836-b59b-33757d980c75" />

Checked for persistence mechanisms, suspicious child processes, privilege escalation attempts, or malware-related artifacts.

<img width="1404" height="380" alt="image" src="https://github.com/user-attachments/assets/4648f457-82a3-4953-89d2-6b95a9462f06" />

<img width="1137" height="411" alt="image" src="https://github.com/user-attachments/assets/53159658-e98d-4d0b-b034-196a00364848" />

No malicious reputation or confirmed threat intelligence was associated with the destination IP or URL.

<img width="803" height="496" alt="image" src="https://github.com/user-attachments/assets/1a643a8f-8235-405c-9c75-f210e07f8f7a" />

<img width="796" height="501" alt="image" src="https://github.com/user-attachments/assets/309c1534-2acc-44ef-9897-6cd811f8c3d0" />

<img width="800" height="482" alt="image" src="https://github.com/user-attachments/assets/6cc31580-c304-47b9-8d79-0f271bfbc34c" />

<img width="617" height="434" alt="image" src="https://github.com/user-attachments/assets/80f1521a-02e5-4d01-b7cf-d38082f9afb0" />

Based on the available endpoint telemetry and threat intelligence, no malicious activity was identified. The alert was assessed as a benign event and was closed after confirming the absence of suspicious behavior.
