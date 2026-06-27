# SOC169 - Possible IDOR Attack Detected
First, I activated the SOC169 – Possible IDOR Attack Detected alarm on the SIEM. By examining the alarm details, I checked the source IP address, the destination IP address, the HTTP method used, the endpoint to which the request was made, and how the security device reacted to the request.

---
Next, I examined which detection rule generated the alarm. The fact that the alarm was named "Possible IDOR Attack" indicated that a user might have attempted to access unauthorized data by trying different user IDs. Therefore, I focused my research specifically on IDOR indicators.

<img width="2560" height="624" alt="image" src="https://github.com/user-attachments/assets/ca936fd3-1c33-4c07-a10b-b032b9453da5" />

Since the alarm summary information was insufficient, I switched to the Log Management screen and applied filtering based on source and target IPs. This allowed me to view all HTTP requests made by the attacker and confirmed that the incident was not limited to a single request.

<img width="2555" height="895" alt="image" src="https://github.com/user-attachments/assets/df6b88ea-7c2f-468f-bb15-c4555c3723e6" />

I examined the logs I collected, analyzing each POST request sent to the same endpoint. I noticed that the user_id values ​​in the POST parameters were constantly being changed. For example, one request sent user_id=2, the next sent user_id=3, and then user_id=4. Since trying consecutive user IDs on the same endpoint is a common behavior in IDOR attacks, I considered this a significant finding.
I then examined not only the requests but also the server's responses to those requests. I noticed that the response size values ​​were different for each request. If the application had denied access or returned the same error message for all requests, the response sizes would have been largely the same. However, the different response sizes suggested that the application was returning different user data, leading me to conclude that the attack may have been successful.
<img width="942" height="447" alt="image" src="https://github.com/user-attachments/assets/f7d4bebe-2469-4b47-8d8c-e306e873bad5" />
<img width="960" height="440" alt="image" src="https://github.com/user-attachments/assets/006a555e-fd0d-4d44-b7f9-177afb087948" />
<img width="1080" height="450" alt="image" src="https://github.com/user-attachments/assets/1bdf521f-2f41-4f5c-a30f-8999789f67d0" />
<img width="1147" height="441" alt="image" src="https://github.com/user-attachments/assets/8f84409c-75fb-455c-9d68-56702820e7a2" />
<img width="1280" height="468" alt="image" src="https://github.com/user-attachments/assets/efcffebb-36e8-4c91-82d1-643f179244f3" /> <br>

Suspected IP is malicious, there are reports.<br>
<img width="915" height="679" alt="image" src="https://github.com/user-attachments/assets/34191073-addf-41a2-a841-62fd26aacb87" />
<img width="1746" height="1079" alt="image" src="https://github.com/user-attachments/assets/7a991d52-7489-4f41-983f-33db18e22614" /><br>

After evaluating all the findings I obtained at the end of the research, I concluded that the repeated requests sent to the same endpoint, the systematic change of user IDs, the server returning different content, and the unblocked requests, when considered together, indicated that this was not merely suspicious behavior but a genuine IDOR attack.<br>
<img width="894" height="559" alt="image" src="https://github.com/user-attachments/assets/ec961888-1288-4ad1-9f75-e2a06a5a8d11" />
<img width="896" height="563" alt="image" src="https://github.com/user-attachments/assets/60e0a7e4-3c6d-44d3-a770-45671772a7d5" />
<img width="888" height="614" alt="image" src="https://github.com/user-attachments/assets/66d85517-2a34-4f91-8bc4-03066fdcb458" /><br>
it is a malicious traffic.<br>
<img width="894" height="412" alt="image" src="https://github.com/user-attachments/assets/c1b32b20-ed51-4314-8d2b-e687350bdcd0" /><br>
This is an example of IDOR<br>
<img width="905" height="400" alt="image" src="https://github.com/user-attachments/assets/50d3bf54-dba9-43a5-94a2-f56abec441ed" /><br>
Not planned<br>
<img width="906" height="583" alt="image" src="https://github.com/user-attachments/assets/4532bb87-0ad3-4192-ac06-7b79a171f862" /><br>
Internet to company network<br>
<img width="902" height="471" alt="image" src="https://github.com/user-attachments/assets/7f38f96c-f4dc-433a-86a7-7d5a82e355a9" /><br>
Attack is successfull bc response code is 200.<br>
<img width="895" height="728" alt="image" src="https://github.com/user-attachments/assets/4724e678-49c6-4cf1-9992-0df006e98e4f" /><br>
lets contain the machine<br>
<img width="858" height="607" alt="image" src="https://github.com/user-attachments/assets/63c40205-2611-454a-a10b-5d10ab8b0e59" />
<img width="2228" height="1074" alt="image" src="https://github.com/user-attachments/assets/ff63b4a9-5f91-4b85-b310-7b037a27771b" />
<img width="905" height="494" alt="image" src="https://github.com/user-attachments/assets/49d6da19-8422-472b-8081-e5ecc797954c" /><br>
Yes, escalate to tier 2<br>
<img width="895" height="688" alt="image" src="https://github.com/user-attachments/assets/3ec4a93c-926a-4b7c-a9d4-e51affbc41d4" />
<img width="897" height="492" alt="image" src="https://github.com/user-attachments/assets/5cc45a26-7f57-4a02-8949-e92b0c0a549f" />
<img width="2206" height="552" alt="image" src="https://github.com/user-attachments/assets/d44ca7fc-c4ce-450a-bff2-96be724961e2" />
