# SOC138 - Detected Suspicious Xls File

The alarm told me that a suspicious .xls file had been opened/downloaded by a user. My first step is always the same: get the file hash and do a reputation check. The reason is simple — the hash tells me if the file has been seen elsewhere, if it belongs to a known malware family; this determines my next steps (whether to proceed to containment or check for false positives). I entered the hash into VirusTotal and the result came back malicious — multiple AV engines had detected this file. At this point, I dropped the "suspicious" label and started treating the case as a potential real threat.

---

<img width="2196" height="443" alt="image" src="https://github.com/user-attachments/assets/8b9d711a-6f10-4d12-a580-2ff0e33d81f6" />

When I investigate the file hash, it seems malicious.
<img width="2558" height="1255" alt="image" src="https://github.com/user-attachments/assets/85241242-d29d-4c41-bee7-c36cbd7d9f37" />

Alert is created at 	Mar, 13, 2021, 08:20 PM, I will look logs on this date for source IP. There are 3 events and 2 of them in this date. 
<img width="2560" height="856" alt="image" src="https://github.com/user-attachments/assets/41c196b3-3040-41cb-94f1-c58e0acb1f2e" />

Destination IP = 177.53.143.89. I isolated the target IP from the logs: 177.53.143.89. My goal in doing this was to clarify whether this IP was a legitimate service or a known malicious infrastructure — because understanding the behavior of the XLS file requires knowing "where it was trying to go" even more critical than knowing "what it did".

<img width="1833" height="445" alt="image" src="https://github.com/user-attachments/assets/805658fc-e3c4-4bc4-86b2-9143d8fb66e4" />
<img width="1854" height="451" alt="image" src="https://github.com/user-attachments/assets/e4504f83-a56e-426b-a9ed-d3d246912342" />

I went to the "relations" tab of the hash I found earlier on VirusTotal and looked at the IP addresses associated with that hash. My reason for doing this was to see the file's entire known network behavior instead of just checking one IP, and to verify if the IP in my logs was within that set. The result was positive — 177.53.143.89 was one of the known C2 (Command & Control) addresses of this malware family. This allowed me to definitively classify the event as "malware landed on the host and attempted to connect to C2."

<img width="1119" height="470" alt="image" src="https://github.com/user-attachments/assets/11ac08bf-0e8e-4c14-8c6c-c7ab7574543a" />

<img width="670" height="459" alt="image" src="https://github.com/user-attachments/assets/e22c2745-b7a2-44ac-b3b7-b086b386f3d4" />
<img width="857" height="333" alt="image" src="https://github.com/user-attachments/assets/fea31e97-ba50-4885-8522-eb4393b21d32" />

not quarantined

<img width="844" height="409" alt="image" src="https://github.com/user-attachments/assets/db5d610c-8cfc-442b-b06c-55bd9f33ae99" />

virustotal results shows it is Malicious

<img width="840" height="432" alt="image" src="https://github.com/user-attachments/assets/2c071470-f6b7-4291-9f94-8ccc12f87fee" />

logs shows accessed the C2 address

<img width="841" height="488" alt="image" src="https://github.com/user-attachments/assets/97f80e9d-d0d8-4550-bc64-55f178220824" />

lets contain the source machine

<img width="805" height="422" alt="image" src="https://github.com/user-attachments/assets/ee881c23-8915-4345-90ab-2f8e929ed855" />
<img width="1749" height="846" alt="image" src="https://github.com/user-attachments/assets/07613c54-6019-4d29-bb1c-2954f4315b5e" />

<img width="841" height="474" alt="image" src="https://github.com/user-attachments/assets/bebcc4c6-ec3b-4ba9-bc03-8dcaab27789e" />
<img width="893" height="474" alt="image" src="https://github.com/user-attachments/assets/690c03d4-5668-43fd-90aa-b4f567f21415" />
<img width="2249" height="610" alt="image" src="https://github.com/user-attachments/assets/ad7bbadc-ae2d-4805-a6fa-d8ccc1bf30df" />
