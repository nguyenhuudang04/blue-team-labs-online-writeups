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
