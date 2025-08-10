**Malicious PowerShell Analysis**


Recently the networks of a large company named GothamLegend were compromised after an employee opened a phishing email containing malware. 
The damage caused was critical and resulted in business-wide disruption. 
GothamLegend had to reach out to a third-party incident response team to assist with the investigation.
You are a member of the IR team - all you have is an encoded Powershell script.
Can you decode it and identify what malware is responsible for this attack?


Challenge Submission

What security protocol is being used for the communication with a malicious domain?
we see it encode by powershell 
<img width="1163" height="167" alt="image" src="https://github.com/user-attachments/assets/b6b7c837-686b-49c4-baa3-0a047b4f79c5" />

we find deconde by powershell 

<img width="1448" height="426" alt="image" src="https://github.com/user-attachments/assets/63f716be-8a60-49b1-b26d-0b838aa40fb6" />

After deobfuscation we will get code like this

<img width="1378" height="696" alt="image" src="https://github.com/user-attachments/assets/1117016c-ecee-4c2b-8c25-0d4d94e815d7" />

we see security protocol is TLS 1.2

<img width="680" height="140" alt="image" src="https://github.com/user-attachments/assets/20b96f53-c582-4ee9-a652-3fe05515e388" />


What directory does the obfuscated PowerShell create? (Starting from \HOME\)

<img width="808" height="147" alt="image" src="https://github.com/user-attachments/assets/c83ee946-f7e1-425a-ba3b-10c26577c1e3" />
.Value::CreateDirectory() calls the static method CreateDirectory to create the directory.

("{0}Db_bh30{0}Yf5be5g{0}" -f [char]92):

This is a format string where {0} will be replaced by [char]92.

[char]92 is the ASCII character number 92, equivalent to the backslash \ on Windows.

The formatted string will be:
\Db_bh30\Yf5be5g\

What file is being downloaded (full name)?

<img width="737" height="60" alt="image" src="https://github.com/user-attachments/assets/fbe2967f-0a9e-4659-a70f-e46830834418" />

$Swrp6tc = "A69S":
The variable $Swrp6tc contains the string "A69S", which is the file name without the extension.

The string "UOHDb_bh30UOHHYf5be5gUOH":

In which, "UOH" is replaced by the character [char]92 (backslash \).

After replacement, the string becomes: "\Db_bh30\Yf5be5g\"

$Imd1yck = $HOME + (above string) + $Swrp6tc + ".dll":

$HOME is the current user directory, for example: C:\Users\DELL

Adding them together, we have:
C:\Users\DELL\Db_bh30\Yf5be5g\A69S.dll


What is used to execute the downloaded file? 

<img width="689" height="255" alt="image" src="https://github.com/user-attachments/assets/8caec18f-c3f8-434c-9ecf-d51045099408" />
The downloaded file is executed using:

Specifically, the command:
rundll32 $Imd1yck, "Control_RunDLL"
rundll32.exe is a legitimate Windows utility used to run functions exported from DLLs.

Here, it runs the downloaded DLL ($Imd1yck) by calling the "Control_RunDLL" entry point.


What is the domain name of the URI ending in ‘/6F2gd/’ 

<img width="806" height="83" alt="image" src="https://github.com/user-attachments/assets/e506e3e0-b3c8-48c8-b2b6-76b5cde8069a" />

so easy to see the answer is wm.mcdevelop.net


Based on the analysis of the obfuscated code, what is the name of the malware?

we will file it on google "A69S.dll"


<img width="1716" height="521" alt="image" src="https://github.com/user-attachments/assets/3cd3457d-f0a5-4b4b-b6ab-bb5c2b94626a" />










