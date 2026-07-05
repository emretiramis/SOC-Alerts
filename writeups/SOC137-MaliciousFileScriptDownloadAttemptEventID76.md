# SOC137 - Malicious File/Script Download Attempt EventID 76

On March 14th, a user attempted to download a .docm file known to be malicious.

<img width="2268" height="531" alt="image" src="https://github.com/user-attachments/assets/a6fe6941-c1db-42f9-b147-0c01613fdb16" />

The ".docm" file here is a Microsoft Word file capable of running macros.

I want to verify if the file is actually malicious. To do this, I will query the file's hash value on VirusTotal.

File seems malicious.

<img width="2560" height="1249" alt="image" src="https://github.com/user-attachments/assets/04a376ec-9e74-454b-a62b-71eecdae9a84" />

However, the fact that the file is malicious doesn't automatically mean the system has been compromised. Therefore, I will proceed to investigate whether the file was executed on the computer.

The device action already appears to be blocked, but I'll check if any process occurred on that date.

There is no log on March 14th. Examination of SIEM and endpoint logs reveals that an attempt was made to download the file, but it was blocked by the security product. In other words, the file was blocked before reaching the user. Therefore, there is no record of the file being executed.

<img width="2542" height="903" alt="image" src="https://github.com/user-attachments/assets/cad18069-4765-44d7-9514-8e31c952832d" />

<img width="599" height="448" alt="image" src="https://github.com/user-attachments/assets/e3d391e8-20be-48e3-8548-20a433526583" />

Malware quarantined from firewall

<img width="799" height="409" alt="image" src="https://github.com/user-attachments/assets/b00f353c-ca6b-4123-9ff3-99b2ad28881a" />

Virustotal investigation shows that is malicious.

<img width="795" height="465" alt="image" src="https://github.com/user-attachments/assets/fa4d74c2-ec16-4bf3-a3fa-c2d163521d57" />

Logs shows there is no C2 communication

<img width="802" height="473" alt="image" src="https://github.com/user-attachments/assets/3ffe8f1f-ec91-4b49-a6f7-f19130a6df32" />

<img width="812" height="454" alt="image" src="https://github.com/user-attachments/assets/7549adc5-5f4a-4fbe-aa83-2dd2db54c097" />

<img width="801" height="510" alt="image" src="https://github.com/user-attachments/assets/6dad3e1f-88c6-4252-9123-611b1c6d3969" />

<img width="602" height="436" alt="image" src="https://github.com/user-attachments/assets/4530e415-40c4-4cf6-a724-5496f33b9a6e" />

<img width="2256" height="473" alt="image" src="https://github.com/user-attachments/assets/813381a8-3229-4f13-8304-b8b29afda70b" />
