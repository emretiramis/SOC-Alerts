# SOC145 - Ransomware Detected EventID 92

<img width="1398" height="946" alt="image" src="https://github.com/user-attachments/assets/8074803f-1cb3-47bb-bcf6-b31d3817b344" />

---

I got an alert and start to investigate it.

<img width="1408" height="943" alt="image" src="https://github.com/user-attachments/assets/3eb994b7-f4cf-4379-9ce2-21d9c72b0dd9" />

When I checked the hash, it seems malicious.

<img width="1389" height="961" alt="image" src="https://github.com/user-attachments/assets/405536c8-dfbe-4535-ad23-8ff37c88e0b5" />

I want to do dynamic analysis on the file.

<img width="1374" height="933" alt="image" src="https://github.com/user-attachments/assets/8e580bc8-05db-4f77-ac14-d11bb092d20c" />

Proccesses seems weird. wbadmin.exe is a backup tool for windows. This can delete backups.

<img width="1386" height="949" alt="image" src="https://github.com/user-attachments/assets/f7c2afd8-5e6e-47b7-bc13-e3fae0c031d5" />

ALert created at May 23 2021, but there is no log at that date.

<img width="1398" height="946" alt="image" src="https://github.com/user-attachments/assets/487e8ef0-bb06-474a-8213-510d289b3a77" />

checking endpoint. We can see wbadmin.exe and ab.exe running
<img width="1343" height="932" alt="image" src="https://github.com/user-attachments/assets/cf2d4d6f-5937-494e-a452-880979d25835" />

I will contain the machine.

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










