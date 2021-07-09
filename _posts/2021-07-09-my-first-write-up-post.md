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

Using cyberchef we decoded QXJlYTUx to Area51












