Browser Forensics - Cryptominer

Our SOC alerted that there is some traffic related to crypto mining from a PC that was just joined to the network.

The incident response team acted immediately, observed that the traffic is originating from browser applications.
After collecting all key browser data using FTK Imager, it is your job to use the ad1 file to investigate the crypto mining activity.

How many browser-profiles are present in Google Chrome?

<img width="764" height="201" alt="image" src="https://github.com/user-attachments/assets/fff40304-8908-499f-98dc-b2e6746f2324" />

<img width="433" height="461" alt="image" src="https://github.com/user-attachments/assets/5a323cf3-fe48-42d0-9f6f-9379b9f402f5" />


<img width="423" height="242" alt="image" src="https://github.com/user-attachments/assets/079bc3ab-4fde-487d-8e40-9853e84e51ed" />


 Manual method:
Go to the directory above and look for folders named:

Default → the main profile

Profile 1, Profile 2, Profile 3, ...

What is the name of the browser theme installed on Google Chrome?

<img width="1914" height="762" alt="image" src="https://github.com/user-attachments/assets/bc22acb0-9ae6-4d44-a898-92b706332243" />

We see the images in <img width="206" height="15" alt="image" src="https://github.com/user-attachments/assets/db15c479-8b2e-4960-b38d-c256a6811b66" />


<img width="1519" height="588" alt="image" src="https://github.com/user-attachments/assets/b9ac2b87-6837-4575-a268-bbd318f10edf" />

use BrowserHistoryViewer find it "Earth in Space"


Identify the Extension ID and Extension Name of the cryptominer?

<img width="1236" height="702" alt="image" src="https://github.com/user-attachments/assets/819d7397-b5d2-4f2e-b12a-9b9a01065d4e" />

We search for the keyword "Extensions" and see the extensions ID and extensions Name


What is the description text of this extension?

<img width="1908" height="1050" alt="image" src="https://github.com/user-attachments/assets/369b2717-798c-4cef-b5f5-649f1abbc4a3" />

we find extensions Name it in the FTK imager and open file manifest.jsion 
see description 


What is the name of the specific javascript web miner used in the browser extension?
<img width="1708" height="441" alt="image" src="https://github.com/user-attachments/assets/d13df7b3-cd6b-4578-9e3a-52a82a53219b" />

TO the name of the specific javascript  we open file background.js  and see the "cryptoloot"

How many hashes is the crypto miner calculating per second? 

<img width="753" height="357" alt="image" src="https://github.com/user-attachments/assets/c5d65cc7-2c41-42ef-86d2-c5e36e7a6234" />

getHashesPerSecond() is a function, likely found in a JavaScript library or application related to cryptocurrency mining, 
that returns the number of hashes computed per second by a miner.
It provides a metric for measuring the mining performance of the miner. 

What is the public key associated with this mining activity? 

<img width="765" height="373" alt="image" src="https://github.com/user-attachments/assets/9f39e2e4-9bb0-41ed-9ec6-82b8d708b3ad" />

in that code the answer is "b23efb4650150d5bc5b2de6f05267272cada06d985a0"


What is the URL of the official Twitter page of the javascript web miner?

<img width="1190" height="710" alt="image" src="https://github.com/user-attachments/assets/6a62eb54-eaa2-4a2d-bebb-c0d9f1937c8a" />

we just need to find the crypto-loot page  replace "x" with "twitter"
