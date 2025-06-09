---
layout: post
author: siunam
date: 2025-06-09
title: I Earned OSWE on My First Try!
description: Back in November 2024, me and my university CTF team NuttyShell placed champion on PwC's Darklab Hack A Day CTF competition. One of the champion prizes is "Sponsorship of Offensive Security Certified Professional (OSCP) PEN-200 certification (90-day lab access)". Since I already earned OSCP back in 2023, and having a strong interest in web security, I requested the organizer to switch it to OffSec Web Expert (OSWE), which they happily did so! Eventually, I earned OSWE on June 2nd, 2025!
ogImageUrl: /assets/images/oswe_cert.png
---

<details class="toc"><summary markdown="span"><strong>Table of Contents</strong></summary>

- [What is OSWE?](#what-is-oswe)
- [Before Taking the Course](#before-taking-the-course)
- [Going Through the Course Materials](#going-through-the-course-materials)
- [Challenge Labs Go Brrrr](#challenge-labs-go-brrrr)
- [During the Exam](#during-the-exam)
	- [The First Day](#the-first-day)
	- [The Second Day](#the-second-day)
- [Some Feedbacks to OffSec](#some-feedbacks-to-offsec)
- [Takeaways](#takeaways)
- [What's Next?](#whats-next)

</details>

# I Earned OSWE on My First Try!

Back in November 2024, me and my university CTF team [NuttyShell](https://polyuctf.com/) placed champion on [PwC's Darklab Hack A Day CTF competition](https://www.pwchk.com/en/issues/cybersecurity-and-privacy/hack-a-day/competitions-2024.html). One of the champion prizes is "Sponsorship of Offensive Security Certified Professional (OSCP) PEN-200 certification (90-day lab access)". Since [I already earned OSCP](https://credentials.offsec.com/a191a6a5-1a16-426e-b6a6-726ba540cfb6#acc.KgkJy98U) back in 2023, and having a strong interest in web security, I requested the organizer to switch it to [OffSec Web Expert (OSWE)](https://www.offsec.com/courses/web-300/), which they happily did so! Eventually, I earned OSWE on June 2nd, 2025!

![](/assets/images/oswe_cert.png)

## What is OSWE?

Basically OSWE and its course, Advanced Web Attacks and Exploitation (WEB-300), is mainly focused on white-box web application penetration testing and source code analysis. If you have played CTFs and solving web challenges before, this certification is like solving different web challenges but with a larger scope, usually the application has at least 2,000 Lines of Code (LoC). From what I observed in different CTFs, the average CTF web challenges are around 300 - 700 LoC. So, if you want to get some feeling on real-world applications' code base, this certification might help you.

## Before Taking the Course

Before May 10th, 2025, when I started to go through the course materials, I already have tons of experiences on solving different CTF web challenges and found some real-world vulnerabilities on WordPress plugins (See [my writeups on those vulnerabilities](https://siunam321.github.io/ctf/#bug-bounty) if you are interested). So, at this point I'm already very, very familiar with source code analysis. However, I actually never learn how to do debugging on other programming languages besides using PHP's [Xdebug](https://xdebug.org/). With this in mind, I would love to learn how can I debug on other languages, as this knowledge could help me during CTFs and finding real-world vulnerabilities.

## Going Through the Course Materials

Starting from May 10th, I started to going through all modules one by one. In the first one, it talks about methodology on source code analysis, such as the sources and sinks model, or sometimes known as taint analysis. I think this methodology is super important when you're doing source code analysis, most of my real-world vulnerabilities finding are based on it. Whenever people ask me something like: "How did you find all these vulnerabilities?", I always reference [this LiveOverflow video](https://www.youtube.com/watch?v=ZaOtY4i5w_U) about the detailed explanation of this methodology.

The next one is about debugging. In there, I learned what is remote debugging and how to set it up. Throughout the course, I learned remote debugging on Java, .NET, JavaScript (Node.js), Python, and PHP. I have tons of fun learning those things!

From here onwards, every module will have a lab to solve. Since I want to kind of simulate the exam environment, I tried to solve them all without reading the module's materials. If I really stuck, I can read the part that I'm stuck with and continue to solve the lab. During those modules and labs, I learned how to turn PostgreSQL SQL injection into a full-blown RCE. The [PostgreSQL injection cheat sheet on PayloadsAllTheThing](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/PostgreSQL%20Injection.md) definitely helped me a lot.

In the next module, I learned .NET insecure deserialization and how to escalate it to RCE. Since I have very few encounters on .NET web application (I think I only analyze .NET code once in SekaiCTF 2024, Web/[Intruder](https://siunam321.github.io/ctf/SekaiCTF-2024/Web/Intruder/)), I really love to get some hands-on experience in analyzing .NET code. After finishing this module and the lab, I learned that .NET ViewState deserialization is quite well-known, I'm curious why this module didn't talk about it.

The rest of the modules are quite easy to me, as I have experience on those vulnerabilities, especially Prototype Pollution (PP). I even research [potential class pollution on PHP](https://siunam321.github.io/research/attempted-research-in-php-class-pollution), which deepen my knowledge on PP. 

## Challenge Labs Go Brrrr

After finishing all module labs on May 20th, I naturally started to solve all challenge labs. As of this blog post, there are 6 challenge labs, all of them will have a suffix word "Application". Each of those challenge labs will have 2 machines: Target VM and Debug VM. If you are trying those labs from a CTF player point of view, Target VM is the remote instance, and the Debug VM is your local testing environment. Inside the Debug VM, it'll have an in-browser VS Code, called [code-server](https://github.com/coder/code-server). It also set up debugging configuration, so you basically don't have to figure out how to do all the remote debugging configuration.

For me, I was able to solve all labs on average 4 hours, including writing fully automated Proof of Concept (PoC) scripts. Of course, those applications that are written in Java and .NET will have a harder time for me, as I don't have much experience on them. But I was able to solve all of them without banging my head against the wall on 28th May.

Oh btw, due to [OffSec's academic policy](https://www.offsec.com/legal-docs/#academic-policy), I cannot disclose how challenge labs are similar to the exam environment. Sorry!

## During the Exam

During halfway through solving those challenge labs, I scheduled the exam at 8:00 a.m. (HKT) 31st May. Unfortunately, there's no other time slot that I can pick, I don't want to start the exam at 4:00 a.m. So, the exam will have a conflict with [Grey Cat The Flag 2025](https://ctftime.org/event/2765) :(

### The First Day

Anyway, on the exam day, 7:30 a.m., I started the verification process with the proctor and completed 15 minutes later. At exactly 8:00 a.m., I received the VPN connection pack and the exam details. In the exam control panel, it says there are 2 machines, the first one is written in Java, and the second one is PHP. I immediately jumped on the second one, as PHP is my second most familiar language. Unfortunately, I had some trouble with the Debug VM. Not only the RDP connection is slow (On average ~5 FPS), but I also can't get `rdesktop` work on my external monitor, which means I have to use my 13-inch laptop monitor. This struggle wasted me for around an hour :(

After setting up the Debug VM, I was able to identify the authentication bypass just within 45 minutes. However, for some stupid reason, I didn't think the vulnerability was possible, so I didn't even *try* to think what could go wrong. After reading the rest of the source code for around 1 hour and 30 minutes, I decided to investigate the vulnerability again, because there's no other way to do authentication bypass. This time, however, I was able to exploit the vulnerability and got the first local flag at HKT 11:49 a.m (3 hours and 49 minutes in).

After that, I quickly identified the potential RCE vulnerability just under 5 minutes. However, I tried to exploit it and I later deemed it wasn't possible to escalate to RCE. After having my lunch and banging my head against the wall for the next 3 hours or so, I decided to try the first machine.

In the first machine, I was able to chain different vulnerabilities and successfully take over the administrator account at HKT 5:25 p.m. (9 hours and 25 minutes in). After finishing my dinner, I was able to identify and exploited the vulnerability to gain RCE at HKT 7:42 p.m. (11 hours and 42 minutes in). From this point onwards, I feel extremely relaxed, because I already passed the exam (2 authentication bypass + 1 RCE)! In short, I passed the exam with just 11 hours and 42 minutes!

I then decided to come back to the second machine's RCE, but still, no luck. Since I already felt a little bit tired, I went to bed at 11:00 HKT p.m. and continue at 1st June 8:45 a.m.

### The Second Day

After having a good sleep last night, I try to gain RCE again on the second exam, but again, no luck. After trying this RCE for at least 10 hours in total and reading the entire source code 5 times, I had suffered enough and gave up on the RCE. I also went back the authentication bypasses and the RCE to make sure I didn't miss any screenshots and end the exam early.

As soon as I end the exam early, I started to work on the report. Just like my previous OSCP exam, I used "[Offensive Security Exam Report Template in Markdown](https://github.com/noraj/OSCP-Exam-Report-Template-Markdown)" GitHub repository by [noraj](https://github.com/noraj) to finish up my report. The report writing process is again very straight forward, just like how I write writeups for different CTF challenges, but change the words to be more professional and formal. Eventually, I submitted the report at HKT 9:41 p.m.

After exactly 24 hours later, I received an email from OffSec, saying that I passed and earned OSWE!

![](/assets/images/Pasted%20image%2020250603165939.png)

## Some Feedbacks to OffSec

Of course not everything is perfect, there are definitely have some rooms for improvements.

- Beyond XSS

There are many more advanced client-side vulnerabilities that are worth learning. For instance, cookie tossing, cache poisoning, cache deception, cross-site WebSocket hijacking, and many more. However, it doesn't have to be *too* advanced, such as XS-Leak. (Web-400? 👀)

- No more black-box module

Since this certificate and the course is focused on white-box approach, I don't think the black-box module is suitable. In my opinion, it should be changed to finding those vulnerabilities in a white-box approach.

- More examples of the sources and sinks model

Since the sources and sinks model is important during source code analysis, I would like to see some common sources and sinks in some languages. For example, in PHP, some common sources include `$_GET`, `$_POST`, `$_FILES`, and common sinks are `file_get_contents`, `readfile`, `eval`, `exec`, and more.

## Takeaways

After earning the certificate, I can share some tips and tricks for people who want to earn the OSWE certificate. For the learning materials, I would suggest you to try to solve different CTF web challenges. Nowadays, most web challenges are white-box approach, so you can practice source code analysis by solving them. If you are stuck, you can search for different writeups online.

Another tips is about slow RDP connection to the Debug VM. Although I didn't solve this issue during the exam, I saw this message on the [OffSec Discord server](https://discord.com/invite/offsec) after submitting my report:

![](/assets/images/Pasted%20image%2020250603173228.png)

I didn't have time to test this, but it seems like [NoMachine](https://www.nomachine.com/) is much smoother than `rdesktop` or [Remmina](https://remmina.org/).

## What's Next?

After earning OSWE, I'll again continue to learn different things. However, recently I decided to put less focus on certificates and focus more on doing security research, bug bounty hunting, CTFs, and more. I feel like those would have a much greater learning value for me.

Here's the quote from [my previous blog post](https://siunam321.github.io/blog/2023-09-21-I-earned-OSCP-on-my-second-attempt):

> "It's worth noting that I'm **not** pursuing the certificate itself, but the knowledge of the course and its journey."

Thank you for reading. See you in the next time!