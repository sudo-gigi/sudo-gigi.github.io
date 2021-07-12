---
layout: post
title: Write-Up [THM] Pre Security Path
categories: [Write-Ups]
categories: [Write-Ups, TryHackMe]
tags: [TryHackMe, Pre Security]
featured-image:  ![image](https://user-images.githubusercontent.com/87175527/125160406-96f49780-e174-11eb-8319-212c534ed894.png)
featured-image-alt: Pre Security Path
---

![image](https://user-images.githubusercontent.com/87175527/125160406-96f49780-e174-11eb-8319-212c534ed894.png)


It's a write-up about the path : [Try Hack Me - Path : Pre Security](https://tryhackme.com/paths)

We'll begin with the Learning CyberSecurity room  : [Try Hack Me - Room : Learning CyberSecurity](https://tryhackme.com/room/beginnerpathintro)

This is a free room, which means anyone can deploy virtual machines in the room (without being subscribed)! 



# [Task 1] Web Application Security


![Task 1](https://user-images.githubusercontent.com/87175527/125160923-4e8aa900-e177-11eb-844d-cb282975a0a7.png)


So we're going to be hacking <strong>BookFace</strong>, TryHackMe's vulnerable social media site.


![image](https://user-images.githubusercontent.com/87175527/125161076-22bbf300-e178-11eb-9a00-b190eca6b608.png))


lets begin!


![image](https://user-images.githubusercontent.com/87175527/125163838-ee9bfe80-e186-11eb-83e7-4a6f6db2ffc0.png)


We can see the username on there


Next we'll type in the username and click reset password


![image](https://user-images.githubusercontent.com/87175527/125163891-2c992280-e187-11eb-936b-9b53466c0659.png)


A code has been sent, but we don't have access to that code


![image](https://user-images.githubusercontent.com/87175527/125163936-76820880-e187-11eb-8459-952e1d1d46e3.png)


We'll try inputting any random code


![image](https://user-images.githubusercontent.com/87175527/125163982-a8936a80-e187-11eb-941e-e270546e7347.png)



![image](https://user-images.githubusercontent.com/87175527/125164070-40915400-e188-11eb-9a05-227ca14fd600.png)



Scroll down to find the web request repeater and input 1 and 10000 as seen below then click bruteforce



![image](https://user-images.githubusercontent.com/87175527/125164132-9cf47380-e188-11eb-800e-7a29b529fada.png)



![image](https://user-images.githubusercontent.com/87175527/125164204-f9579300-e188-11eb-8a59-339206bfd26c.png)



Voila!!


![image](https://user-images.githubusercontent.com/87175527/125164273-463b6980-e189-11eb-8273-472c0f8ecb07.png)







# [Task 2] Network Security


![image](https://user-images.githubusercontent.com/87175527/125164569-df1eb480-e18a-11eb-849a-59bbac4ebc27.png)


![image](https://user-images.githubusercontent.com/87175527/125164582-f2318480-e18a-11eb-9286-794cdaea8f0c.png)



![image](https://user-images.githubusercontent.com/87175527/125164550-c4e4d680-e18a-11eb-8e79-a9cc104dcf2d.png)


![image](https://user-images.githubusercontent.com/87175527/125257553-70aa3580-e2f5-11eb-8670-426760f88a08.png)




# [Task 3] Learning Roadmap


![image](https://user-images.githubusercontent.com/87175527/125258356-2c6b6500-e2f6-11eb-9944-351295c2c786.png)


There's really nothing to do here, just read the above and click on `correct answer`.


![image](https://user-images.githubusercontent.com/87175527/125258605-6c324c80-e2f6-11eb-91a2-6c4a7447a790.png)


That concludes the <strong>Learning Cyber Security</strong> room in the <strong>Pre Security</strong> path.
