**Network Analysis - Ransomware**



Scenario
ABC Industries worked day and night for a month to prepare a tender document for a prestigious project that would secure the company’s financial future. 
The company was hit by ransomware, believed to be conducted by a competitor,
and the final version of the tender document was encrypted. Right now they are in need of an expert who can decrypt this critical document.
All we have is the network traffic, the ransom note, and the encrypted ender document. Do your thing Defender!

What is the operating system of the host from which the network traffic was captured? (Look at Capture File Properties, copy the details exactly) 

To see the OS use  wireshark 
Statistics -> capture the file properties 
<img width="857" height="706" alt="image" src="https://github.com/user-attachments/assets/f5aec3af-79bd-44b5-aa8f-b4f3ffce47e0" />


What is the full URL from which the ransomware executable was downloaded?

We filter HTTP -> follow -> http stream 

<img width="1554" height="560" alt="image" src="https://github.com/user-attachments/assets/c42df7de-09a5-4437-8dc3-2082304a602d" />

we will se host, port and name file , Just write according to the answer format.



Name the ransomware executable file?

<img width="1549" height="481" alt="image" src="https://github.com/user-attachments/assets/279fb871-8fce-484e-bbeb-f52d0e7a5769" />

We see the user sends a GET request to download the file.


What is the MD5 hash of the ransomware?

To do this we will download the file and hash it.

<img width="499" height="554" alt="image" src="https://github.com/user-attachments/assets/438a0938-6065-406e-b463-0fa3d964daa6" />


<img width="548" height="89" alt="image" src="https://github.com/user-attachments/assets/10cbca99-6762-455f-83e8-b2b3fd35d6b4" />

What is the name of the ransomware?

Upload the .exe file to virustotal for analysis.

<img width="1842" height="847" alt="image" src="https://github.com/user-attachments/assets/b3c3f21f-6e57-40e9-9e3c-c1a671cba7d1" />

<img width="1642" height="700" alt="image" src="https://github.com/user-attachments/assets/8eae8d76-36da-4fb4-ac9a-1a270f79ccb1" />
we see the ransomeware is "TeslaCrypt"

What is the encryption algorithm used by the ransomware, according to the ransom note?


<img width="1352" height="155" alt="image" src="https://github.com/user-attachments/assets/4f0a1ef5-02e7-42f0-a77e-a34c6230f2ce" />

We see in the file that it says it is encrypted with RSA-4096


What is the domain beginning with ‘d’ that is related to ransomware traffic?


We go to the Contacted Domains section in virustotal and find the domain that starts with the letter "d"



<img width="1351" height="442" alt="image" src="https://github.com/user-attachments/assets/9c1bf520-25ec-4d04-91c3-d3ad03f3e733" />


Decrypt the Tender document and submit the flag?

To decrypt the file Tender.pdf.micro, we have determined the encryption method is "TeslaCrypt", so we will find a tool to decrypt it.

https://success.trendmicro.com/en-US/solution/KA-0006362

use this tool to slove 

<img width="832" height="889" alt="image" src="https://github.com/user-attachments/assets/5e4b0cc4-64b9-4bbc-a611-681dd9a4761d" />

<img width="569" height="538" alt="image" src="https://github.com/user-attachments/assets/06b8d7d2-b4fb-477f-9efb-1aff9050b8bc" />

<img width="1590" height="865" alt="image" src="https://github.com/user-attachments/assets/84fd131f-88b0-4fa4-9c16-6e29d5019139" />

we will find the flag 


