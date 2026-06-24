# SOC141 - Phishing Url Detected
This alarm indicates that an endpoint attempted to access a known malicious domain. Examination of security logs revealed that the initial outbound connection occurred before firewall rules were applied, and subsequent access attempts were blocked by network security controls.

This suggests the user may have clicked on a phishing link or been redirected to a malicious URL. Due to the success of the initial connection, a partial exposure to malware was assessed.

---
<img width="2203" height="570" alt="image" src="https://github.com/user-attachments/assets/20699885-ac57-484e-a646-6949a269fa86" />

The suspected url is phishing
<img width="2560" height="1217" alt="image" src="https://github.com/user-attachments/assets/072866a4-a1ab-43eb-922a-7f0a5a1ff1f3" />

I am looking the logs for suspected IP address and there are network traffic from some devices.
<img width="2560" height="1005" alt="image" src="https://github.com/user-attachments/assets/83692c49-3d1a-4152-a215-b5a8dc7a01f1" />

1. log. This log was successful.
<img width="1904" height="484" alt="image" src="https://github.com/user-attachments/assets/eaeb8a3d-0cc9-4fdb-a592-e1edf9444fb4" />

2. log. This log was blocked by firewall.
<img width="1871" height="468" alt="image" src="https://github.com/user-attachments/assets/da049a35-a079-4ace-ac42-42f98c5eead9" />

I need to examine the endpoint that established a successful connection. When I check the last login date, I see that it's before the date the log was generated.
<img width="2090" height="1050" alt="image" src="https://github.com/user-attachments/assets/7e47df9e-0f07-4268-8a3b-83fda0a0d722" />

This proccess and browser history looks suspicious.
<img width="1655" height="702" alt="image" src="https://github.com/user-attachments/assets/cc823cae-6d0d-425f-98c0-700998820ff2" />
<img width="1690" height="713" alt="image" src="https://github.com/user-attachments/assets/f96d63a5-27a5-402f-b678-e8b0f4a32647" />

I will quarantine the device.
<img width="1565" height="844" alt="image" src="https://github.com/user-attachments/assets/ba659093-c852-4989-b867-873a6a390e39" />

<img width="795" height="588" alt="image" src="https://github.com/user-attachments/assets/13825c7e-f0b1-4c2c-877a-ea38fde57e40" />
<img width="1799" height="456" alt="image" src="https://github.com/user-attachments/assets/9ad7f4d7-2954-49b2-b937-0f44c8d07861" />
<img width="986" height="469" alt="image" src="https://github.com/user-attachments/assets/259f0788-861d-47b8-a6ee-1144dd936708" />
<img width="1001" height="447" alt="image" src="https://github.com/user-attachments/assets/41327a28-88f5-44e2-b815-29d4656239d3" />
This is malicious
<img width="997" height="601" alt="image" src="https://github.com/user-attachments/assets/4fbfee4a-24ba-480a-a9b8-9255dc96f805" />
accessed
<img width="999" height="662" alt="image" src="https://github.com/user-attachments/assets/bae04285-451d-43c6-ac23-3caf2b53d1a5" />
<img width="997" height="468" alt="image" src="https://github.com/user-attachments/assets/96e65936-4f40-4600-9140-213b0988f5a1" />
<img width="997" height="620" alt="image" src="https://github.com/user-attachments/assets/35cd2692-c619-4046-ae78-2d8bbb16a041" />
<img width="1006" height="614" alt="image" src="https://github.com/user-attachments/assets/c954044f-bf20-4fe8-a8e3-293af6bf8c0b" />
<img width="751" height="543" alt="image" src="https://github.com/user-attachments/assets/dbac36ad-662d-4c46-b3f0-5b7c0105c8dc" />
<img width="2149" height="554" alt="image" src="https://github.com/user-attachments/assets/57d310a4-8fb4-4d55-b414-1d1d083b494c" />



