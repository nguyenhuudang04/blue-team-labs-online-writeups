**Squid Game**

Will you survive the Squid Games?

Challenge Submission
What is the phone number on the invitation card in Squid Game? (Research this online!) 

We will search the question on google

<img width="966" height="918" alt="image" src="https://github.com/user-attachments/assets/24b955f1-fec7-4d10-8aca-f527a917d219" />

we see phone number

Can you extract something from the invitation card file? What is the name of the file? 
Use the steghide tool to check for hidden data in the Invitation Card.jpg image file.

Enter passphrase we will try with phone number
<img width="623" height="83" alt="image" src="https://github.com/user-attachments/assets/1f8c9e03-d6b2-4fa1-8f6e-f150ee1e3268" />

<img width="721" height="141" alt="image" src="https://github.com/user-attachments/assets/3ef4f65b-aab1-404f-b854-00d45fceeaf9" />

We have exported the Dalgona.png file.

3. What hint text can be discovered in the final file? (5 points)

Open StegSolve using the above command
Go to menu File > Open, select file

Use filters and tools in StegSolve to check:

Color channels (RGB)

Bit planes
<img width="1314" height="636" alt="image" src="https://github.com/user-attachments/assets/74fb6c46-b774-4f0f-956a-890025f74cae" />

see the hint text is "red pixel"


What is the final flag?

with it hint text 

Focus on the red pixels as suggested, extract the red channel value (R) from the image.

Convert this number sequence to a character string or encode and decode it with a tool like dcode.fr.

Reverse the resulting string to get a standard flag in the required format.

go to this link to select  https://pixspy.com/

<img width="1897" height="888" alt="image" src="https://github.com/user-attachments/assets/f2313915-936d-4400-a7c8-61cf65d5e1e3" />

Take the red value (R) in each row separately.
123, 102, 124, 173, 123, 64, 166, 63, 137, 115, 171, 64, 156, 155, 64, 162, 137, 107, 165, 171, 65, 175


go to this page to decode and submit flags  https://www.dcode.fr/ascii-code

<img width="1533" height="919" alt="image" src="https://github.com/user-attachments/assets/c36315fb-3940-4f9d-a49d-dd96e361ad38" />


