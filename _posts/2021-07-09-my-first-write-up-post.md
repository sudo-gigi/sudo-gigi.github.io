---
title: "Write-Up [THM] Agent Sudo"
date: 2021-07-09
---
Welcome to the <a href="https://www.tryhackme.com/room/agentsudoctf">Agent Sudo</a> THM exclusive CTF room. Your task is simple, capture the flags just like the other CTF room. Have Fun!

![image](https://user-images.githubusercontent.com/87175527/125082799-8b936480-e0bf-11eb-975b-2e6e219e97cf.png)

<h1>Enumerate</h1>
 We'll use nmap to scan.


-sV attempts to determine the version of the service running on port,
-F scans fast the most common ports,
-A Enables OS detection, version detection, script scanning, and traceroute.


![image](https://user-images.githubusercontent.com/87175527/125094549-437a3f00-e0cb-11eb-84c6-1151f04427bb.png)


Three ports are open namely: FTP, SSH and HTTP, put in your Machine-ip on the browser, to reveal a webpage.


![image](https://user-images.githubusercontent.com/87175527/125096366-fc8d4900-e0cc-11eb-80f9-1851640fa857.png)


Now we'll try dictionary attacks using the usernames.A hint from tryhackme says to swap the User-agent "R" to "C".


![image](https://user-images.githubusercontent.com/87175527/125099592-167c5b00-e0d0-11eb-8279-73dd241bdc1e.png)


Now we have a user-agent name we'll proceed to brute-force FTP with Hydra using the legendary rockyou.txt.


<h1>Hash cracking and Brute-force</h1>


![image](https://user-images.githubusercontent.com/87175527/125102582-5a249400-e0d3-11eb-8b19-f5bcabd75b79.png)


Since we have the password for Agent, it's time to log-in through FTP


![image](https://user-images.githubusercontent.com/87175527/125104204-0450eb80-e0d5-11eb-8018-46961a20e85b.png)


Use the ls command to look for content, there are two image files and a text file then the get command to download.


![image](https://user-images.githubusercontent.com/87175527/125106593-b4275880-e0d7-11eb-8e66-5d49677e20b4.png)


The "To_agentJ.txt" file says that the login password for the chris is stored in the fake picture.


![image](https://user-images.githubusercontent.com/87175527/125106921-1a13e000-e0d8-11eb-9b31-40216cfc4028.png)


![image](https://user-images.githubusercontent.com/87175527/125109429-3f561d80-e0db-11eb-9d4d-7decf7efb2e9.png)


We then use binwalk cutie.png. "binwalk" is a tool used for extracting the content of images, then binwalk cutie.png.


Then we use the "zip2john 8702.zip > file.txt"command to crack the zip-file for the password,


![image](https://user-images.githubusercontent.com/87175527/125113308-65ca8780-e0e0-11eb-9ae3-ddbffd3f23bf.png)


So we have the password alien, we then use the "7z x 8702.zip" command and after entering the password we see the message below.


![image](https://user-images.githubusercontent.com/87175527/125113930-3405f080-e0e1-11eb-92dd-1248654870f9.png)


![image](https://user-images.githubusercontent.com/87175527/125114117-6fa0ba80-e0e1-11eb-878e-3ae5fc1bdad3.png)


Using cyberchef we decoded QXJlYTUx to Area51 which is the steg password.


![image](https://user-images.githubusercontent.com/87175527/125114778-52202080-e0e2-11eb-8b1f-b0880accaf05.png)


Next, we'll use steghide on cute-alien.jpg


![image](https://user-images.githubusercontent.com/87175527/125115459-43863900-e0e3-11eb-8d9e-8ba4e2908a74.png)


As we see the name of the agent is james, we'll SSH into the machine using the username and password.


![image](https://user-images.githubusercontent.com/87175527/125116206-47ff2180-e0e4-11eb-9fb6-aaeb4db99c80.png)


Voila!!


![image](https://user-images.githubusercontent.com/87175527/125116465-a926f500-e0e4-11eb-91bc-6cba582198ce.png)


What is the incident of the photo called?


When i googled alien-autopsy i found the answer to be <strong>Roswell alien autopsy</strong>.


![image](https://user-images.githubusercontent.com/87175527/125117235-d7f19b00-e0e5-11eb-8d9f-a941440f79c5.png)


<h1>Privilege Escalation</h1>


For this we'll use the sudo -l command to check for sudo permissions.


![image](https://user-images.githubusercontent.com/87175527/125118073-18054d80-e0e7-11eb-9311-b588966b4c46.png)


I had to google “(ALL, !root)” and found this <a href="https://www.exploit-db.com/exploits/47502">Vulnerability</a> 


<strong>CVE-2019-14287</strong>


Next use command sudo -u#-1 /bin/bash and then ls -al /root.


![image](https://user-images.githubusercontent.com/87175527/125120104-e9d53d00-e0e9-11eb-993f-31206855c9a0.png)



I hope you enjoyed this room as much as i did.






