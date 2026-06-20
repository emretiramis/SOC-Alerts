# SOC119 - Proxy - Malicious Executable File Detected
This case demonstrates a SOC investigation of a proxy alert generated. The alert was triggered due to a suspected malicious executable download activity detected through proxy traffic. The objective of the investigation was to validate whether the downloaded file and destination URL represented a real security threat or legitimate user activity


## Alert Investigation
The investigation started by reviewing the proxy alert details and analyzing the requested URL associated with the executable download
<img width="2160" height="572" alt="image" src="https://github.com/user-attachments/assets/2518cdfd-b553-484f-abed-88bdde1ba624" />

The suspicious URL was investigated using VirusTotal to determine whether it had any known malicious reputation.

Findings:
* No malicious detections were reported.
* The URL reputation appeared clean.
* Further validation showed that the destination was the official WinRAR download page.

<img width="2560" height="1246" alt="image" src="https://github.com/user-attachments/assets/a1c5bcd1-17a3-468b-826e-c7cbec28fdb9" />
<img width="1474" height="702" alt="image" src="https://github.com/user-attachments/assets/824533cf-b92b-4b78-b05b-47d3ada4f1f4" />


The affected endpoint (172.16.17.5) was reviewed for additional suspicious activity.

Analysis results:
* No abnormal behavior detected.
* No evidence of malware execution.
* No suspicious persistence or compromise indicators identified.

<img width="1747" height="926" alt="image" src="https://github.com/user-attachments/assets/81c0e7d9-923a-44d0-a3df-d79f426148ab" />


## Final Assessment
After completing the investigation, the alert was classified as:

✅ False Positive

The activity was determined to be a legitimate software download rather than malicious behavior.
<img width="909" height="600" alt="image" src="https://github.com/user-attachments/assets/532179d6-4f47-4034-a05d-bc96d50ea69e" />
<img width="1966" height="648" alt="image" src="https://github.com/user-attachments/assets/3f1e9b31-ccf5-4787-a778-c8f115cc251c" />
<img width="990" height="456" alt="image" src="https://github.com/user-attachments/assets/642328c7-f48f-4891-bff6-f3124c5e036b" />
<img width="980" height="386" alt="image" src="https://github.com/user-attachments/assets/73c134f7-9095-4313-abde-0de583291e10" />
it is non-malicious
<img width="931" height="527" alt="image" src="https://github.com/user-attachments/assets/17aa49b8-9a3f-4954-84f6-db83da6fee55" />
<img width="990" height="511" alt="image" src="https://github.com/user-attachments/assets/60ba6374-66ff-4db2-8244-424449f72d15" />
<img width="1001" height="581" alt="image" src="https://github.com/user-attachments/assets/015a5da8-ab41-471b-93c7-d64adcad2b6b" />
<img width="733" height="538" alt="image" src="https://github.com/user-attachments/assets/09fb4ac4-20c4-44c4-9f0b-74830ad6fc20" />
<img width="2158" height="622" alt="image" src="https://github.com/user-attachments/assets/d0a37e5d-8112-4eaf-a846-4f7bc57aacc3" />


