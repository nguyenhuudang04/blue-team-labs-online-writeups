**Suspicious USB Stick**

Scenario
One of our clients informed us they recently suffered an employee data breach. As a startup company,
they had a constrained budget allocated for security and employee training.
I visited them and spoke with the relevant stakeholders.
I also collected some suspicious emails and a USB drive an employee found on their premises.
While I am analyzing the suspicious emails, can you check the contents on the USB drive?

Reading Material:
https://zeltser.com/analyzing-malicious-documents/
https://en.wikipedia.org/wiki/List_of_file_signatures
https://eternal-todo.com/tools/peepdf-pdf-analysis-tool.****

What file is the autorun.inf running?

<img width="1346" height="429" alt="image" src="https://github.com/user-attachments/assets/e4e6420f-ddb7-46a2-be5e-20329f200a2e" />

We use the HxD tool to analyze decoded text and notice that this file, when run, will open the README.pdf file.

Does the pdf file pass virustotal scan? (No malicious results returned) 

<img width="1912" height="1014" alt="image" src="https://github.com/user-attachments/assets/214fcb08-406c-4aad-aa84-10547f75d58d" />

It's easy to see that the .pdf file failed the virustotal scan.

Does the file have the correct magic number? 

This question is asking if the header of the .pdf file is correct.

<img width="1563" height="903" alt="image" src="https://github.com/user-attachments/assets/c16ba99b-88c8-4f01-ab3b-f79a3f6cf8a2" />

<img width="1860" height="762" alt="image" src="https://github.com/user-attachments/assets/5506c582-ddf3-4da4-8c5e-762c70559db8" />

so they are the same so the answer is True

What OS type can the file exploit? (Linux, MacOS, Windows, etc)

<img width="983" height="498" alt="image" src="https://github.com/user-attachments/assets/57e252ef-2257-4fe9-8090-c92e1c18102c" />

Use Peepdf to analyze .pdf file  

<img width="526" height="336" alt="image" src="https://github.com/user-attachments/assets/b9b79f7b-715d-4f0b-89cc-5f272b959d0c" />


We see that 

Suspicious elements:

/OpenAction (1): [1]
/AA (1): [3]
/JS (1): [27]
/JavaScript (1): [27]
/Launch (1): [28]
These are all clear signs of a malicious PDF document:

Component Malicious Function
/OpenAction Automatically executes an action when opening a PDF document
/Launch Requests execution of an external file – usually an .exe – only works on Windows
/JavaScript Contains JS code that can navigate, download files, or exploit vulnerabilities
/AA Additional Actions – may be associated with page open, print, or focus events

The file exploits the Windows operating system. This is evident because it contains the /Launch action, which is used to execute external files such as .exe.
The ability to automatically launch .exe files via /Launch is a feature specific to Windows. 
Other operating systems like Linux and MacOS do not support this behavior in the same way, making Windows the only viable target for exploitation in this case.

A Windows executable is mentioned in the pdf file, what is it? 

<img width="1122" height="145" alt="image" src="https://github.com/user-attachments/assets/2030b423-e7d8-487c-943d-578ebc2b96d4" />

We use Strings to search for .exe file.

How many suspicious /OpenAction elements does the file have? 

<img width="1117" height="379" alt="image" src="https://github.com/user-attachments/assets/ded3cca1-7b68-4238-9caf-0f3322911afd" />

We use Peepdf tool to analyze it.
