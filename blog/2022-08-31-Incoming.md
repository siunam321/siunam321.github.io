---
layout: post
title: "OSCP First Attempt Failled"
author: siunam
date: 2022-08-31
---

# Background

In around May 27 2022, I bought the PWK and OSCP exam ($1499), and started the PWK course at Jun 6 2022. You may surprised why I pick OSCP after learning ethical hacking for just 2 months. This reason why for that is I wanna learn more stuff about cybersecurity, so I googled "Certificate for cybersecurity", and I saw a couples of well-known certicicates, such as OSCP, PNPT, CEH, etc. Based on what I've seen in online, OSCP is the most famous certicicate for pentesters. Hence, I bought the PWK course and OSCP exam.

# Pre-Exam (Jun 6, 2022 to Aug 27, 2022)

As the time progress, I finished the PWK course in 26 days, average 1 module each day (I spent much more time on Active Directory), and rooted all 70 + 5 lab machines in 33 days, average rooted 3 machines each day. Also, since I finished PWK course and lab machines, I went to [Offensive Security's Proving Ground Play](https://portal.offensive-security.com/labs/play) to prepare much more for OSCP exam, rooted 18 machines, average rooted 1 machine each day.

# Exam (Aug 28, 2022)

This day is the exam day, and I woke up at 5:00 AM, ate a normal breakfast and get ready for the exam at 8:00 AM. I joined the proctoring software around 7:40 AM, every thing works perfectly and successfully started the exam at 8:00AM with no issue.

- During the exam:

Off course, for the sake of disclosure, I can't talk too much of the details in here. :)

But, I ended up only rooted 1 machine - Buffer overflow. Except the buffer overflow machine, all other 3 machines were insanely difficult in the initial foothold, and it wasn't what I expected in the exam! I've spent more than around 10 hours with no progress whatsoever except the buffer overflow one. I tried to enumerate every single thing but still, no dice.

Total points: 20/30 points

About the proctoring, all the proctors are very nice and I almost forgot them during the exam! Since they wouldn't interfere you unless your webcam or the proctoring software has some issues.

- After the exam:

I spent around an hour to finish the exam report, as I already documenting a lot during the exam. Finally, I bundled up the exam report and the humongous lab report (643 pages lul) into a 7zip file.

If you asked me which report template that I'm using and how I generate a report, I use a report template from [norja](https://github.com/noraj/OSCP-Exam-Report-Template-Markdown), and generated via [pandoc](https://pandoc.org/). This would allow me to turn markdown file into PDF.

# Post-Exam

After finished the exam and uploaded the report, I leanred a lesson and started to review my weaknesses:

- Too rely on walkthroughs and hints

I understand that there is no shame to read others walkthroughs and hints, but I was way too rely on those things. To address this issue, I'll not reading otherse walkthroughs and hints, unless I'm really really stucked, like when I enumerated everything, researched everything, but no progress at all.

- Weak in Windows privilege escalation

Although I managed to escalated to administration level in the buffer overflow machine, I still quite unfamiliar with Windows privilege escalation. It's seems to me that this is because I played too many Linux machines compare to Windows machines. Also, many Windows machines that I've played, when you gained an initial foothold on the machine, you instantly became administrator or system, which is not gonna happen in OSCP exam, as it requires local and proof flag. To solve this issue, I'll try to play more Windows machines in TryHackMe, HackTheBox, and Vulnhub.

# Conclusion

During the PWK course and OSCP exam, there are a lot of joy, thrill and pain, as well as learned tons of new stuff that I've never seen before. And yeah, I'll definitely retake the OSCP exam next year! I'll not give up!

Anyways, I hoped you guys enjoyed this blog! See ya next time!