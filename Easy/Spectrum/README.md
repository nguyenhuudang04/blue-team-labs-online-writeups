**Spectrum**

Scotland yard have intercepted information about one of the biggest drug deals to go down in the city of London. 
Can you find out where and when the deal is expected to go down?

We will use Autopsy tool to analyze .dd file

<img width="1912" height="486" alt="image" src="https://github.com/user-attachments/assets/a0357a20-39d3-46bd-82e1-b684918af9ea" />
we see there are 3 image files and 1 .zip file <img width="1165" height="182" alt="image" src="https://github.com/user-attachments/assets/88906a11-b19c-4ef0-b531-97c125c48276" />

Let's try unzip the .zip file to see what's inside.

<img width="562" height="108" alt="image" src="https://github.com/user-attachments/assets/b5a712b2-f13e-4fd1-af3e-38e97c6c8f9c" />

But it requires password to decrypt the file

We will use fcrackzip tool to crack the password of that zip file.

<img width="620" height="100" alt="image" src="https://github.com/user-attachments/assets/7cf89518-f3e0-4e5a-86dd-6efe332809d7" />

ok.. password found "garfield" decrypt zip file

<img width="431" height="192" alt="image" src="https://github.com/user-attachments/assets/015b217c-507d-4950-b240-67ef6c669a70" />

There are some audio files.

we saw that steghide can also be used for hiding data in audio files and has the password analyzed in the image above

<img width="914" height="309" alt="image" src="https://github.com/user-attachments/assets/014d335a-f443-40df-a232-68a0ee50b76e" />

we found a piece of encrypted data it looks like it is encoded with base58

<img width="1885" height="706" alt="image" src="https://github.com/user-attachments/assets/008d1ab3-5e9a-4aed-91e9-1946d87a3f91" />

we see that there is time but looking closely at the word "emit" 
it looks like the word time is written backwards let's try to change the time backwards 15:01:00" we get "00:10:51"

the correct answer is it <img width="925" height="144" alt="image" src="https://github.com/user-attachments/assets/3cb672cf-ffdd-4c97-bc5f-e9bf03116ad1" />

What are the supposed coordinates for the deal?

Let's try to analyze the audio file to see if we can find anything more from it and start with the white.wav file.

<img width="1117" height="601" alt="image" src="https://github.com/user-attachments/assets/98289194-9c43-45fe-910e-2a212a038dac" />

and try to analyze the Spectrogram of the test sound <img width="1840" height="545" alt="image" src="https://github.com/user-attachments/assets/d5e70478-bca8-468c-9b33-5410e1c762cd" />

<img width="1111" height="499" alt="image" src="https://github.com/user-attachments/assets/0e1226f2-53f2-47e7-91b4-16bfb86121e3" />

we have found the coordinates

Looking into these coordinates, what is the name of this location? 

we use https://www.gps-coordinates.net/ to view the location.   


<img width="1829" height="738" alt="image" src="https://github.com/user-attachments/assets/2d894e7d-815e-43e6-a28a-567d2eddca80" />

We found the address to be "London City Airport"
