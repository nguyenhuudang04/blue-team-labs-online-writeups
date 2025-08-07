**Secure Shell**

Scenario

Hey! We had a SSH service on a system and noticed unusual change in size of the log file.
Don’t panic, it was the new IT guys’ daughter who said she was able to break into the system.
I had given her permission to test some of these services. I am giving you the log file, can you solve the following queries?

Is it an internal or external attack, what is the attacker IP? 

<img width="1450" height="211" alt="image" src="https://github.com/user-attachments/assets/0de80ae2-8ecd-4150-b81e-690474d719cb" />

 Distinguish internal / external IP
Internal IP type (internal/private) IP range
192.168.x.x 192.168.0.0 – 192.168.255.255
10.x.x.x 10.0.0.0 – 10.255.255.255
172.16.x.x → 172.31.x.x 172.16.0.0 – 172.31.255.255

→ If the IP is outside the above ranges, it is external.


How many valid accounts did the attacker find, and what are the usernames?

<img width="1249" height="362" alt="image" src="https://github.com/user-attachments/assets/650abe71-0146-472f-bc94-d653dadc1fb3" />

<img width="1036" height="124" alt="image" src="https://github.com/user-attachments/assets/291dc2fc-6cfa-427b-9047-bea48a9edb1d" />


There is only 1 account, Sophia.

How many times did the attacker login to these accounts? 

<img width="1228" height="136" alt="image" src="https://github.com/user-attachments/assets/36e22eed-447b-45cb-b250-ef751dbf5968" />

we see 2 successful logins


When was the first request from the attacker recorded? 

We find the first line in the log containing this IP – this will be the attacker's first request.

<img width="972" height="120" alt="image" src="https://github.com/user-attachments/assets/acac62a3-f86d-47c9-9706-87a5bdc23b42" />

What is the log level for the log file? 


<img width="1106" height="416" alt="image" src="https://github.com/user-attachments/assets/7b72e6f4-d165-4c53-920a-9bcc7e0e0088" />

<img width="1359" height="250" alt="image" src="https://github.com/user-attachments/assets/76ae3087-569b-4005-9362-51fe3fe7b5c8" />

so the answer will be DEBUG


Where is the log file located in Windows?

<img width="1431" height="583" alt="image" src="https://github.com/user-attachments/assets/1d4f142b-6858-46dc-9e36-edc77f165adb" />

<img width="745" height="690" alt="image" src="https://github.com/user-attachments/assets/5f3feaff-d76e-48e5-a9bc-86b0b4baf479" />


so the answer will be C:\ProgramData\ssh\logs\sshd.log

