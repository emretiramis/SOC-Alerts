# SOC119 - Proxy - Malicious Executable File Detected
This case demonstrates a SOC investigation of a proxy alert generated. The alert was triggered due to a suspected malicious executable download activity detected through proxy traffic. The objective of the investigation was to validate whether the downloaded file and destination URL represented a real security threat or legitimate user activity


## Alert Investigation
The investigation started by reviewing the proxy alert details and analyzing the requested URL associated with the executable download
<img width="2560" height="655" alt="image" src="https://github.com/user-attachments/assets/f6379e2a-1494-42f0-a141-aef5c03530cd" />


The suspicious URL was investigated using VirusTotal to determine whether it had any known malicious reputation.

Findings:
* No malicious detections were reported.
* The URL reputation appeared clean.
* Further validation showed that the destination was the official WinRAR download page.

<img width="2560" height="1238" alt="image" src="https://github.com/user-attachments/assets/038a5fe8-22a4-4ea1-8bcf-9dbea38701d1" />

<img width="1812" height="869" alt="image" src="https://github.com/user-attachments/assets/23817333-3ef1-4c7a-bdd5-f7851e3a620e" />



The affected endpoint (172.16.17.5) was reviewed for additional suspicious activity.

Analysis results:
* No abnormal behavior detected.
* No evidence of malware execution.
* No suspicious persistence or compromise indicators identified.

<img width="2152" height="1138" alt="image" src="https://github.com/user-attachments/assets/5bccb259-0cee-407b-9ac9-a5831fbf02fc" />



## Final Assessment
After completing the investigation, the alert was classified as:

✅ False Positive

The activity was determined to be a legitimate software download rather than malicious behavior.
<img width="1041" height="741" alt="image" src="https://github.com/user-attachments/assets/666ccc33-9894-4487-a02b-9318268f51bf" />
<img width="2189" height="640" alt="image" src="https://github.com/user-attachments/assets/71f66af6-6419-4da4-a89f-25230a247897" />
<img width="1204" height="551" alt="image" src="https://github.com/user-attachments/assets/c99eca0f-9981-4854-be67-574a961240a3" />
<img width="1156" height="448" alt="image" src="https://github.com/user-attachments/assets/666f2b5f-e8cd-47ae-be9a-b8d438f4ab2c" />

it is non-malicious
<img width="1147" height="620" alt="image" src="https://github.com/user-attachments/assets/679b856c-1d5c-4c7a-b73a-8c2ba0af0d11" />
<img width="1223" height="599" alt="image" src="https://github.com/user-attachments/assets/4e3031dc-b535-422e-aaf2-8a9d8c97a82c" />
<img width="1235" height="684" alt="image" src="https://github.com/user-attachments/assets/eecd8c5c-ada9-4701-a689-52aaad394bfb" />
<img width="914" height="669" alt="image" src="https://github.com/user-attachments/assets/568dfb79-1f3a-41d5-9814-6649d759bd0a" />
<img width="2158" height="622" alt="image" src="https://github.com/user-attachments/assets/d0a37e5d-8112-4eaf-a846-4f7bc57aacc3" />


