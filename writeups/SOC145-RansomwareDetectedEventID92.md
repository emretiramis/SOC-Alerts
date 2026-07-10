# SOC145 - Ransomware Detected EventID 92

Initially, a "Ransomware Detected" alarm was triggered in the SIEM/EDR console from the MarkPRD (172.16.17.88) host. When starting Triage, the first thing I always look at is: which host, which user, which file, and when. Here, the culprit file is clear: ab.exe.

File downloaded (ab.exe) → not blocked
→ VirusTotal: malicious (ransomware)
→ ANY.RUN detonation: high-risk behavior
→ wbadmin.exe spawn → attempted to delete backup/shadow copy
→ attempted lateral movement via SMB
→ Endpoint telemetry: ab.exe + wbadmin.exe running (verified) → Network: no C2 traffic
→ Containment: host isolated
→ Verdict: True Positive
→ urgent escalation to L2/L3

<img width="1398" height="946" alt="image" src="https://github.com/user-attachments/assets/8074803f-1cb3-47bb-bcf6-b31d3817b344" />

---

I got an alert and start to investigate it.

<img width="1408" height="943" alt="image" src="https://github.com/user-attachments/assets/3eb994b7-f4cf-4379-9ce2-21d9c72b0dd9" />

Upon reviewing the logs, I saw that ab.exe was downloaded and its execution was not prevented. This points to a lack of control in the initial stages — either there was an AV/EDR exclusion rule, or the file was already allowed to run until it was detected. At this point, my priority was to verify whether the file was truly malicious.

<img width="1389" height="961" alt="image" src="https://github.com/user-attachments/assets/405536c8-dfbe-4535-ad23-8ff37c88e0b5" />

Static detection wasn't enough; I needed to see the behavior as well. I detonated the file in ANY.RUN, an isolated sandbox environment. The result showed a rather aggressive behavioral pattern — classified as malicious with a high risk score.

<img width="1374" height="933" alt="image" src="https://github.com/user-attachments/assets/8e580bc8-05db-4f77-ac14-d11bb092d20c" />

I saw in the sandbox logs that ab.exe spawned wbadmin.exe. This is a classic ransomware tactic: it tries to delete system backups/shadow copies to prevent the victim from restoring from backups. As soon as I saw this, I raised the severity of the incident to "definite ransomware, recovery blocked". As I continued my investigation, I observed lateral movement attempts across SMB shares. This means the malware is not only trying to remain on a single host but also attempting to spread to other shares/hosts on the network — a finding that makes the containment decision even more urgent.

<img width="1386" height="949" alt="image" src="https://github.com/user-attachments/assets/f7c2afd8-5e6e-47b7-bc13-e3fae0c031d5" />

When I checked the network logs, I didn't see any active C2 (Command & Control) traffic. This could be considered good news; either the malware hadn't yet progressed to the C2 stage, or this variant is an offline encryption type. However, this doesn't mean the threat is completely harmless — it simply means that no additional exfiltration/control channel was detected at the network level at that moment.

<img width="1398" height="946" alt="image" src="https://github.com/user-attachments/assets/487e8ef0-bb06-474a-8213-510d289b3a77" />

I cross-verified the sandbox findings with the real endpoint: in the EDR telemetry, I saw that both the ab.exe and wbadmin.exe processes were indeed running. This is a critical step — you shouldn't make a containment/escalation decision without confirming that the behavior seen in the sandbox also occurs in the real environment.

<img width="1343" height="932" alt="image" src="https://github.com/user-attachments/assets/cf2d4d6f-5937-494e-a452-880979d25835" />

All the evidence (malicious hash + backup deletion + lateral movement attempt + telemetry verification) combined, so I immediately isolated the host from the network. Time was critical to stop the spread and prevent the encryption process from jumping to other systems.

<img width="1384" height="947" alt="image" src="https://github.com/user-attachments/assets/f3250b2f-0fd5-4583-ac77-15f31a78bdfb" />

<img width="1371" height="990" alt="image" src="https://github.com/user-attachments/assets/bb65400b-e11a-4664-802e-b8d76a200b6b" />

Not quarantined

<img width="1369" height="956" alt="image" src="https://github.com/user-attachments/assets/96369069-a827-4090-8090-461f6054727c" />

Our analysis shows that this is malicious.

<img width="1380" height="934" alt="image" src="https://github.com/user-attachments/assets/91b4fa4e-6496-467e-afb0-dc42e0157f1c" />

logs shows there no C2 communication

<img width="1351" height="955" alt="image" src="https://github.com/user-attachments/assets/1d145a53-40c3-44d7-9b57-597397b4944d" />

<img width="1404" height="943" alt="image" src="https://github.com/user-attachments/assets/2cdadc5a-815e-41fe-be73-61d13065aef3" />

<img width="1380" height="945" alt="image" src="https://github.com/user-attachments/assets/10242070-b962-4cdf-bb79-53a4f2f056ed" />

<img width="1382" height="963" alt="image" src="https://github.com/user-attachments/assets/53297fee-de7d-4f96-88ce-b687c13ea616" />

<img width="1356" height="933" alt="image" src="https://github.com/user-attachments/assets/420ec407-07ea-433b-af7d-7f689ff05a5c" />










