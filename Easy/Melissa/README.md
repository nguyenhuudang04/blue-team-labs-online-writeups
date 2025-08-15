**Melissa**


Melissa aka W97M.Melissa.A (Symantec) or Virus:W32/Melissa (F-Secure) is a macro virus dates back to March 26, 1999.

This challenge should be completed in a virtual machine as it contains real malware.

we can dowmload oledump tool this link [link](https://blog.didierstevens.com/programs/oledump-py/)

On that page there are also instructions for use.


Submit the stream number that contains the Melissa macro in the LIST.DOC file?

<img width="628" height="310" alt="image" src="https://github.com/user-attachments/assets/01323ccd-8e28-4381-b68a-53dedacfeab8" />


python oledump.py LIST.DOC
→ Stream containing Melissa macro is: 7


After identifying which version of word, Melissa will enable all macros from registry ?

<img width="642" height="164" alt="image" src="https://github.com/user-attachments/assets/d27971e6-a797-45dc-9f44-5a3c08dedfab" />


python oledump.py -s 7 -v LIST.DOC
Command Meaning
oledump.py → tool to analyze OLE files (Word, Excel, etc.) and VBA macros.

-s 7 → select stream number 7, which contains Melissa macro.

-v → decompress and display VBA content in readable form.

LIST.DOC → Word file being analyzed.

<img width="1095" height="389" alt="image" src="https://github.com/user-attachments/assets/3c5dd376-59f1-4c3e-b59d-7aa35861d633" />

9.0 → Word 2000

Comment in macro: 'Works in both Word 2000 and Word 97
→ Target Word version: Word 97 and Word 2000 


What is the email service targeted by Melissa ? 



<img width="1024" height="401" alt="image" src="https://github.com/user-attachments/assets/08452a10-46ae-471c-a7d7-127c5988b22e" />

Set UngaDasOutlook = CreateObject("Outlook.Application")
Set DasMapiName = UngaDasOutlook.GetNameSpace("MAPI")
→ Email service: Outlook


How many number of email addresses were collected 

<img width="969" height="308" alt="image" src="https://github.com/user-attachments/assets/28c74121-a214-44e0-8c82-093a6d1d52f4" />


If x > 50 Then oo = AddyBook.AddressEntries.Count
The macro only sends emails to a maximum of 50 addresses at a time.
→ Number of email addresses collected: 50 

What is the string used by melissa to identify whether a PC is infected or not and decide whether to collect email addresses or not?

<img width="1138" height="160" alt="image" src="https://github.com/user-attachments/assets/81bd7843-21cc-40f9-8625-631d620848d6" />

System.PrivateProfileString("", "HKEY_CURRENT_USER\Software\Microsoft\Office\", "Melissa?") = "... by Kwyjibo"
The macro uses this string to check if the PC is infected.
→ String: ... by Kwyjibo 


What is the variable responsible for identifying the email username of the infected PC ?


<img width="987" height="442" alt="image" src="https://github.com/user-attachments/assets/f9df0116-e03a-439b-88c4-9175403d25a9" />

BreakUmOffASlice.Subject = "Important Message From " & Application.UserName
The Application.UserName variable is used to get the username on the infected PC.

What is the text in email body used for spreading melissa ?

<img width="990" height="462" alt="image" src="https://github.com/user-attachments/assets/792a1baf-16e5-44cd-9968-23820c35734f" />

BreakUmOffASlice.Body = "Here is that document you asked for ... don't show anyone else ;-)"
This is the email content that is intended to trick the recipient into opening the document.


What is the text that is inserted by Melissa in an open word document?

<img width="1639" height="236" alt="image" src="https://github.com/user-attachments/assets/e63f8e9e-a165-40dd-8ff5-6ade7336198d" />


election.TypeText "Twenty-two points, plus triple-word-score, plus fifty points for using all my letters. Game's over. I'm outta here."
The macro inserts this text into the open Word document



















