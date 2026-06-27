# SOC167 - LS Command Detected in Requested URL

When I activated the alarm, the first thing that caught my attention was the direction of the traffic: a request from the internal network to the internet. Usually, "LS command" triggers are meaningful in reconnaissance/command injection attempts from an external source to the internal system; here, the direction was the opposite, which initially lowered my level of suspicion a bit, but I still followed the standard procedure.

  ---

<img width="2560" height="660" alt="image" src="https://github.com/user-attachments/assets/b3ea20d4-0980-4e90-a1fb-781fe80488d4" />

My first step is always to examine the source. When I queried this IP address, I saw that a total of 7 events were triggered from the same source. I wanted to see if it was a recurring behavioral pattern rather than a one-off anomaly, so I looked at each of the 7 events individually.

<img width="2560" height="902" alt="image" src="https://github.com/user-attachments/assets/f2464328-754d-467e-bfc5-e91a2288e5c7" />

This is where the crucial part begins. The "LS command" signature is usually triggered when shell command patterns like `ls` or `ls -la` are searched for within a URL. When I opened and read the URLs of the 7 requests, I realized they all contained normal, harmless content.

Here's the trick: the word "skills" in the URLs contains the substring "ls". So the rule-making engine is likely searching for the "ls" pattern at the string-matching level and mistakes the "ls" within "skills" for a command injection. Once I realized this, I understood why the alarm was triggered — it's a classic example of a substring false positive.

<img width="1222" height="404" alt="image" src="https://github.com/user-attachments/assets/2c87c476-d480-438d-9394-adc91127fc0b" />
<img width="1249" height="422" alt="image" src="https://github.com/user-attachments/assets/96de0a2c-c48f-494d-b07b-52bd82d17d88" />
<img width="1281" height="462" alt="image" src="https://github.com/user-attachments/assets/0342657d-e8ce-4199-8eb2-50a918c49c80" />
<img width="1291" height="457" alt="image" src="https://github.com/user-attachments/assets/30d1376c-0267-4242-838d-1d37974b583b" />
<img width="1330" height="467" alt="image" src="https://github.com/user-attachments/assets/da56cd0c-45e0-4df0-ac25-de0c92c6924a" />
<img width="1398" height="468" alt="image" src="https://github.com/user-attachments/assets/0246029b-6235-4318-b9b6-aebef8bb7d49" />
<img width="1256" height="458" alt="image" src="https://github.com/user-attachments/assets/71b3d210-1af7-455c-b49d-87bca5c61af4" />

<img width="684" height="480" alt="image" src="https://github.com/user-attachments/assets/aa7eed5f-9ed7-4a10-ab64-2f58ee6fe206" />
<img width="848" height="539" alt="image" src="https://github.com/user-attachments/assets/83a8e474-5799-439f-aa56-c5fb4dbd87c3" />
<img width="794" height="536" alt="image" src="https://github.com/user-attachments/assets/e1432843-d6e6-41ce-a5e8-1e4e55da8bf8" />
<img width="811" height="646" alt="image" src="https://github.com/user-attachments/assets/eebbb1ec-b7a8-495e-9e76-d8918805c3cf" />

After evaluating the URL content, source-destination relationship, and recurring pattern together, I concluded that the traffic was non-malicious. There was no actual command execution, parameter injection, or suspicious encoding in any of the requests — it was simply noise resulting from the signature rule working on a string basis ("ls" substring) rather than a word basis.

<img width="799" height="420" alt="image" src="https://github.com/user-attachments/assets/87abca72-de0f-459b-92be-39d94c08e9a7" />

yes but not malicious.

<img width="855" height="474" alt="image" src="https://github.com/user-attachments/assets/ecf79135-6993-484a-af82-7433e5bbc797" />
<img width="837" height="373" alt="image" src="https://github.com/user-attachments/assets/561be004-43cd-445d-b9ab-5fe2f7316b9b" />

non malicious

<img width="802" height="395" alt="image" src="https://github.com/user-attachments/assets/c4f55efe-a20e-4303-9891-aefb78a8c3da" />
<img width="848" height="454" alt="image" src="https://github.com/user-attachments/assets/3637304f-bf0c-4f89-90ae-98263556321d" />

I disabled the alarm as a False Positive. The root cause: The WAF/IDS signature searches for "ls" using a substring match instead of a full word boundary; legitimate words like "skills" are therefore being triggered by mistake.

<img width="621" height="461" alt="image" src="https://github.com/user-attachments/assets/efeda01b-da5a-407b-88cd-a095107635fb" />
<img width="1998" height="539" alt="image" src="https://github.com/user-attachments/assets/ce6fbf9b-8144-47e0-9d47-414a91089e01" />
