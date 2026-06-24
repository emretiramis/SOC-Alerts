# SOC140 - Phishing Mail Detected - Suspicious Task Scheduler
This alert relates to an email detected and blocked as phishing by email security systems. Further investigation revealed the email contained a PDF attachment.

The PDF file was sent to VirusTotal for analysis and classified as Trojan.PDF.Fraud.AD by various security engines. Dynamic analysis was performed in a sandbox environment to examine the file's behavior in more detail.

According to the ANY.RUN analysis results, when the PDF file is executed, it attempts to communicate with a remote Command and Control (C2) server. The identified C2 address was verified with threat intelligence sources and assessed as malicious infrastructure.

Network and security logs were examined to verify whether a potential infection occurred. The examination revealed that no systems within the corporate network connected to the relevant C2 address. This indicates that the malicious file was not executed or able to communicate.

---
Action seems blocked, there is no payload probabily but I need to analysis it.
<img width="2173" height="671" alt="image" src="https://github.com/user-attachments/assets/1141dd2b-5a4c-4039-a30a-fdb828617a80" />

Lets check the mail security. There is an attachment here.
<img width="1414" height="948" alt="image" src="https://github.com/user-attachments/assets/945a8992-5bbe-40e1-9096-c408c12a5b01" />

Lets download the attachment and analysis it.
<img width="1388" height="916" alt="image" src="https://github.com/user-attachments/assets/77483813-7996-4592-8206-57a68df42773" />

I got the md5 hash of suspicious file.
<img width="1400" height="959" alt="image" src="https://github.com/user-attachments/assets/1ab559d3-ad79-4d57-9e05-93e473f32e97" />

virustotal shows that it's a trojan.
<img width="1369" height="952" alt="image" src="https://github.com/user-attachments/assets/56994b54-5060-4b18-abbf-ab50b767e304" />

To ensure there are no security vulnerabilities on our endpoint, I will perform a dynamic analysis by running it in an any.run environment as the next step.
<img width="1418" height="971" alt="image" src="https://github.com/user-attachments/assets/366d87a8-296d-4a08-884f-e6135cee8a94" />
There is an action here. 
<img width="1423" height="931" alt="image" src="https://github.com/user-attachments/assets/adca64be-2e91-4cb2-ae02-3a029903a6e0" />

It is malicious
<img width="1409" height="963" alt="image" src="https://github.com/user-attachments/assets/a13ae656-5c3a-4ff1-8804-b8893380552e" />

When I control the logs, there is no connection from our endpoints.
<img width="1393" height="941" alt="image" src="https://github.com/user-attachments/assets/7e7385cf-4996-4f27-b3ab-d07dcab8dde7" />

<img width="1382" height="951" alt="image" src="https://github.com/user-attachments/assets/703004df-66a3-41ff-a93f-5fd1319861e1" />
<img width="1427" height="960" alt="image" src="https://github.com/user-attachments/assets/3cd83751-56b2-45f0-a034-79f2318ee2b4" />
yes
<img width="1360" height="933" alt="image" src="https://github.com/user-attachments/assets/e32766ca-62b8-4da3-b68a-0cfd99513dd8" />
malicious
<img width="1363" height="940" alt="image" src="https://github.com/user-attachments/assets/1528e1e8-843a-4e36-a41a-2d87dca10225" />
not delivered because blocked
<img width="1366" height="951" alt="image" src="https://github.com/user-attachments/assets/def27248-2659-4bc7-a2e2-2ad5149c75c4" />
<img width="1433" height="972" alt="image" src="https://github.com/user-attachments/assets/1866fd25-3dae-4992-94d2-7edf5fbba872" />
<img width="1384" height="963" alt="image" src="https://github.com/user-attachments/assets/824ad021-9f6e-4f43-a0ab-e05f84db5e8e" />
<img width="1359" height="935" alt="image" src="https://github.com/user-attachments/assets/9f18f50d-9791-49dc-aa56-504e5e30cab9" />
<img width="1355" height="934" alt="image" src="https://github.com/user-attachments/assets/c7987d2c-12db-499d-a41b-cc6c22e376d1" />









