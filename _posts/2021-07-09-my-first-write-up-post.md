---
title: "Write-Up [THM] Agent Sudo"
date: 2021-07-09
---
Welcome to the <a href="https://www.tryhackme.com/room/agentsudoctf">Agent Sudo</a> THM exclusive CTF room. Your task is simple, capture the flags just like the other CTF room. Have Fun!

![image](https://user-images.githubusercontent.com/87175527/125082799-8b936480-e0bf-11eb-975b-2e6e219e97cf.png)

<h1>Enumerate</h1>
We'll use nmap to scan.

-sV attempts to determine the version of the service running on port
-F scans fast the most common ports
-A Enables OS detection, version detection, script scanning, and traceroute

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











