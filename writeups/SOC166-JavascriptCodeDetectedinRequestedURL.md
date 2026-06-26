# SOC166 - Javascript Code Detected in Requested URL
<img width="2160" height="589" alt="image" src="https://github.com/user-attachments/assets/b00549ee-200f-454e-8b4e-8aa19d8d9507" />

---

The Device Action: Allowed setting increases the alarm's significance because the WAF/IPS has passed this request.

Let's decode and break down the URL:
```
q=<$script>javascript:$alert(1)<$/script>
```
If you normalize this, you'll see a classic XSS test payload:

```
<script>javascript:alert(1)</script>
```
The $ signs here were probably added during the platform's logging/encoding or are a WAF bypass attempt (some attackers add characters to bypass filters). The use of alert(1) is a classic indication that this is a "probe"/test payload and not a real attack — real attackers usually test whether XSS works with alert(1), then move on to more sophisticated payloads for cookie/session theft (e.g., document.cookie exfiltration).


I check the logs and see some similar other events.
<img width="1761" height="970" alt="image" src="https://github.com/user-attachments/assets/89bf0a9c-46fa-41de-92f1-25c924aea08a" />

<img width="987" height="636" alt="image" src="https://github.com/user-attachments/assets/fe339106-9589-485e-b5f3-0f3e088e4fce" />
<img width="917" height="553" alt="image" src="https://github.com/user-attachments/assets/81e2d3dd-2109-4fad-83c8-b7ac294df14b" />
<img width="907" height="657" alt="image" src="https://github.com/user-attachments/assets/5969be3e-be34-404d-b54f-6fb684970351" />
this traffic is malicious
<img width="918" height="461" alt="image" src="https://github.com/user-attachments/assets/5701cb7e-6c86-4e53-8c75-da5916615edc" />
the payload shows that is XSS
<img width="904" height="381" alt="image" src="https://github.com/user-attachments/assets/b2f8f5b4-94b9-40f7-80fe-924f96d4d351" />
not planned
<img width="896" height="532" alt="image" src="https://github.com/user-attachments/assets/240e09c8-efcb-4187-9a3d-e2da780ae9a6" />
The attack coming from internet to internal network
<img width="903" height="391" alt="image" src="https://github.com/user-attachments/assets/68af5023-d409-4ba3-9339-dba50f217385" />
Attack isnt successful because logs says it was 302 redirect
<img width="919" height="699" alt="image" src="https://github.com/user-attachments/assets/d1204f5a-444c-49a8-a986-b118be23df44" />
<img width="888" height="336" alt="image" src="https://github.com/user-attachments/assets/97809568-0bbd-4c08-8b04-73e6b7743209" />
<img width="925" height="527" alt="image" src="https://github.com/user-attachments/assets/86af7ad8-7e96-4d6f-b9ff-76c311e5b145" />
no need to escalate to tier 2
<img width="913" height="673" alt="image" src="https://github.com/user-attachments/assets/540548ac-695f-413e-b4b4-e637e4285df9" />
<img width="981" height="552" alt="image" src="https://github.com/user-attachments/assets/4c3b55b3-14ac-42ac-beee-fc088327ad49" />
