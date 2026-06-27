# 	SOC170 - Passwd Found in Requested URL - Possible LFI Attack

The alarm was triggered by the detection of the keyword "passwd" in the URL. This keyword is a common indicator used in Local File Inclusion (LFI) attacks. The attacker attempted to perform a path traversal using the file parameter with the request ?file=../../../../etc/passwd and gain access to the sensitive system file /etc/passwd. This technique is a frequently used LFI exploit when file inclusion mechanisms on web servers are not adequately validated.

---
Take note of the details provided, especially the source IP, the requested URL, and the alert trigger reason.

<img width="2543" height="590" alt="image" src="https://github.com/user-attachments/assets/2ae28e1c-3e4b-4435-958b-09588ccc2d97" />

Next, in Log Management, we filter logs by Source IP: 106.55.45.162 to view traffic from the attacker.

<img width="2550" height="804" alt="image" src="https://github.com/user-attachments/assets/e7e6e9e1-36ef-4b75-a433-cb181a578cda" />

Request: GET /?file=../../../../etc/passwd HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1; .NET CLR 1.1.4322)

Response: HTTP/1.1 500 Internal Server Error
Content-Length: 0

A 500 Internal Server Error response tells us the request failed and the attack was not successful.

<img width="2235" height="745" alt="image" src="https://github.com/user-attachments/assets/0f1c70bd-ae5f-44ef-ab63-9091013a58a4" />

Investigating IP address, this is malicious. <br>
<img width="933" height="675" alt="image" src="https://github.com/user-attachments/assets/960c22a6-cc19-4904-9770-59560d414c96" />
<img width="1721" height="1126" alt="image" src="https://github.com/user-attachments/assets/2c5b44e6-21bb-402c-82ba-8768926fcdd8" />
<img width="885" height="542" alt="image" src="https://github.com/user-attachments/assets/220cf7cf-6f2c-4f1e-923d-2dd7b51ba5ed" />
<img width="891" height="567" alt="image" src="https://github.com/user-attachments/assets/8c6278d8-1909-4d42-8716-f1998938ddce" />
<img width="888" height="628" alt="image" src="https://github.com/user-attachments/assets/b734c669-cbc2-4696-b5e0-2c7dabad8a12" /><br>
This is malicious event even not successful. The traffic includes a classic path traversal LFI attack targeting /etc/passwd.<br>
<img width="890" height="448" alt="image" src="https://github.com/user-attachments/assets/ad7148f1-e9e3-4e7e-86a3-7559b150e24e" /><br>
LFI. Although similar techniques are used in RFI (Remote File Inclusion), this is clearly an LFI attempt.<br>
<img width="891" height="390" alt="image" src="https://github.com/user-attachments/assets/8c83e7ef-74a1-4050-a098-8d962bab69d6" /><br>
not planned<br>
<img width="894" height="540" alt="image" src="https://github.com/user-attachments/assets/07408d96-fb36-43a7-89f8-76f6fa5045c3" /><br>
internet to company network<br>
<img width="899" height="450" alt="image" src="https://github.com/user-attachments/assets/0e70b94f-6bb8-4ba8-90cc-2aa692b3c825" /><br>
not successful<br>
<img width="891" height="677" alt="image" src="https://github.com/user-attachments/assets/ec134027-3ce0-446f-b505-c39f2878caad" />
<img width="890" height="374" alt="image" src="https://github.com/user-attachments/assets/3554df4f-c066-4700-9fbd-a1150e09aaec" />
<img width="895" height="477" alt="image" src="https://github.com/user-attachments/assets/1cd771e1-051e-45af-913c-795b1be0ea8f" /><br>
no. Since the attack was not successful and came from the internet, escalation is not necessary.<br>
<img width="901" height="667" alt="image" src="https://github.com/user-attachments/assets/59a84f2b-d474-4695-bce3-255fbd08f71c" />
<img width="896" height="501" alt="image" src="https://github.com/user-attachments/assets/b93be703-695e-48e1-bfc2-e9822f429fe1" />
<img width="2160" height="476" alt="image" src="https://github.com/user-attachments/assets/92315c7b-8215-474b-a140-e8e6de76e98e" />
