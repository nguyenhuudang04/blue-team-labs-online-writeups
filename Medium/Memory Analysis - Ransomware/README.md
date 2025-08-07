**Memory Analysis - Ransomware**

Scenario
The Account Executive called the SOC earlier and sounds very frustrated and angry. 
He stated he can’t access any files on his computer and keeps receiving a pop-up stating that his files have been encrypted. 
You disconnected the computer from the network and extracted the memory dump of his machine and started analyzing it with Volatility.
Continue your investigation to uncover how the ransomware works and how to stop it!

Run “vol.py -f infected.vmem --profile=Win7SP1x86 psscan” that will list all processes. What is the name of the suspicious process? 

To solve this question we will use this option to scans for processes 
<img width="1547" height="137" alt="image" src="https://github.com/user-attachments/assets/62da280f-25c0-4de7-893c-8d2d4fa261e6" />



<img width="1210" height="182" alt="image" src="https://github.com/user-attachments/assets/003a8b06-a0de-4064-b18a-7c75ea0d0a63" />


<img width="1127" height="248" alt="image" src="https://github.com/user-attachments/assets/ec77d349-4f96-4ebb-8329-d0db64775444" />

We find this process very suspicious.

What is the parent process ID for the suspicious process? 


<img width="929" height="599" alt="image" src="https://github.com/user-attachments/assets/156f12c2-2dee-42de-9fd9-30da65c70c53" />

PID column is child PPID is parent so the anMemory Analysis - Ransomware**

Scenario
The Account Executive called the SOC earlier and sounds very frustrated and angry. 
He stated he can’t access any files on his computer and keeps receiving a pop-up stating that his files have been encrypted. 
You disconnected the computer from the network and extracted the memory dump of his machine and started analyzing it with Volatility.
Continue your investigation to uncover how the ransomware works and how to stop it!

Run “vol.py -f infected.vmem --profile=Win7SP1x86 psscan” that will list all processes. What is the name of the suspicious process? 

To solve this question we will use this option to scans for processes 
<img width="1547" height="137" alt="image" src="https://github.com/user-attachments/assets/62da280f-25c0-4de7-893c-8d2d4fa261e6" />



<img width="1210" height="182" alt="image" src="https://github.com/user-attachments/assets/003a8b06-a0de-4064-b18a-7c75ea0d0a63" />


<img width="1127" height="248" alt="image" src="https://github.com/user-attachments/assets/ec77d349-4f96-4ebb-8329-d0db64775444" />

We find this process very suspicious.

What is the parent process ID for the suspicious process? 


<img width="929" height="599" alt="image" src="https://github.com/user-attachments/assets/156f12c2-2dee-42de-9fd9-30da65c70c53" />
PID column is child PPID is parent 


<img width="1500" height="361" alt="image" src="https://github.com/user-attachments/assets/70a9502e-80e4-44b0-8f4a-5893fee93d92" />

 the answer is "2732"

What is the initial malicious executable that created this process?

 I find the file name of its parent process and it will show which file it was born from.


<img width="1131" height="583" alt="image" src="https://github.com/user-attachments/assets/8730829d-acce-4428-85e5-43319382977c" />


If you drill down on the suspicious PID (vol.py -f infected.vmem --profile=Win7SP1x86 psscan | grep (PIDhere)), find the process used to delete files 

 We will find any processes related to id "2732"

<img width="1517" height="270" alt="image" src="https://github.com/user-attachments/assets/1758d790-925d-4d8a-84a0-991bd6cbef9d" />

The process used to delete files is taskdl.exe with PID 4060, a child process of the ransomware @WanaDecryptor. 
This process started and exited instantly, which is typical behavior for file deletion or cleanup tasks.


Find the path where the malicious file was first executed ?

is to find the location of the parent file when running, so we will use the windows.cmdline option

<img width="1520" height="176" alt="image" src="https://github.com/user-attachments/assets/681d23fa-1e00-49a7-8403-8cc2f921fb97" />


Can you identify what ransomware it is? (Do your research!) 

<img width="1481" height="369" alt="image" src="https://github.com/user-attachments/assets/7b57b183-617d-4f20-8e88-415fad26dce4" />

It is quite easy to find the name of the malware.


What is the filename for the file with the ransomware public key that was used to encrypt the private key? (.eky extension)

<img width="1575" height="132" alt="image" src="https://github.com/user-attachments/assets/ce1ae826-beee-46b7-8bad-7be7624b8904" />

use option filescan to find it 

<img width="1515" height="152" alt="image" src="https://github.com/user-attachments/assets/a3216ddb-a8ce-4b9f-9558-c96b78d8e005" />





