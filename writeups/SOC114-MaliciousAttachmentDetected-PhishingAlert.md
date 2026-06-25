# SOC114 - Malicious Attachment Detected - Phishing Alert

This alert was generated as a result of detecting a phishing email containing a malicious attachment. Investigation revealed the email contained a PowerPoint (.ppt/.pptx) file.

The file's hash value was analyzed on VirusTotal and flagged as a Trojan by several security engines. Dynamic analysis was performed in the ANY.RUN sandbox environment to observe the behavior of the malicious file.

However, because the file was password-protected, it could not be fully run in the sandbox environment, and no behavioral analysis results were obtained. Therefore, no direct malicious activity or Command and Control (C2) communication could be observed.

Due to the limitations of the sandbox analysis, an IOC (Indicator of Compromise) based investigation was conducted, and C2 indicators associated with the malicious file were investigated in the log management system. The investigation revealed outbound connections matching the relevant IOCs.

The analysis determined the endpoint with the IP address 172.16.17.45 as the source system of the connection.

---
Phishing alarm was created.
<img width="1384" height="952" alt="image" src="https://github.com/user-attachments/assets/44fe27ff-90e6-4bb2-9178-fd685cca1c75" />
Lets check the email.
<img width="1401" height="953" alt="image" src="https://github.com/user-attachments/assets/a008064d-b4a4-4799-a72a-f95f5c9b35a2" />

There is an attachment here.
<img width="1387" height="964" alt="image" src="https://github.com/user-attachments/assets/cc134953-228e-4f38-8971-27b6ce6063fe" />
<img width="1367" height="942" alt="image" src="https://github.com/user-attachments/assets/bc0c56a8-0a47-4bdd-aca9-badb79e9d7bb" />

it seems like a trojan.
<img width="1401" height="962" alt="image" src="https://github.com/user-attachments/assets/6d7f6cc5-01c2-4e5d-8216-fc6842c1f6a8" />

I want to do dynamic analysis on this file. So we can see if there is an C2 communication.
<img width="1447" height="990" alt="image" src="https://github.com/user-attachments/assets/ed023a6a-b3a7-4a62-b0d4-23d9aedbbfa0" />

The file is password protected. I tried "infected" but no result. So file couldnt create any process or C2 communcation. We couldnt find anything but this is not mean this file is benign. I will continiue to my analysis.
<img width="1367" height="945" alt="image" src="https://github.com/user-attachments/assets/3401a336-a3ed-48db-a043-0cbb85cab045" />


While checking these IP adresses, I found a log.
<img width="1414" height="982" alt="image" src="https://github.com/user-attachments/assets/db0a7611-cbb8-4f26-a8e5-73d728d432d6" />

<img width="1453" height="960" alt="image" src="https://github.com/user-attachments/assets/98055b36-9ec0-481d-a213-c661ba87e976" />

<img width="1369" height="907" alt="image" src="https://github.com/user-attachments/assets/76efb2ea-ab7e-4e4b-ac19-94f16f8cc98d" />











