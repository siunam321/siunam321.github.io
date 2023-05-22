# Grey Cat The Flag 2023 Qualifiers Writeup

> CTFTime event link: [https://ctftime.org/event/1938](https://ctftime.org/event/1938)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Grey-Cat-The-Flag-2023-Qualifiers/images/banner.png)

## Writeups

- Web:
    1. [Fetus Web](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Fetus-Web/README.md)
    2. [Login Bot](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Login-Bot/README.md)
    3. [Microservices](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Microservices/README.md)
    4. [Microservices Revenge](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Microservices-Revenge/README.md)
    5. [100 Questions](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/100-Questions/README.md)
    6. [Baby Web](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Baby-Web/README.md)
    7. [View My Albums](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/View-My-Albums/README.md)
    8. [Sort It Out](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Sort-It-Out/README.md) ***(Unsolved)***
- Misc:
    1. [CrashPython](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Misc/CrashPython/README.md)
    2. [Gotcha](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Misc/Gotcha/README.md)

## Background

- Starts: 19 May 2023, 22:00 SGT
- Ends: 21 May 2023, 22:00 SGT

Grey Cat The Flag is a jeopardy-style CTF organized by NUS Greyhats ([https://nusgreyhats.org/](https://nusgreyhats.org/)) and National Cybersecurity R&D Labs ([https://ncl.sg/](https://ncl.sg/)).

We will host the onsite finals at the National University of Singapore (NUS), to which the top 5 international teams and the top 10 Singapore teams from the qualifiers will be invited. Each team may send up to 6 people for the finals, and accommodation in Singapore will be provided for the international teams.

**Categories:**

- Rev
- Web
- Misc
- Pwn
- Crypto

## Overview

- Team: JHDiscord
- Team Member: @siunam, @7777777, @awesome10billion, @oldschool125, @goldenturtle, @moreoflore, @Peace, @sdj04, @pho3nix, @fire
- Team Solves: 15/34
- Individual Solves: 6/34
- Score: 980
- Rank: 60/454
- Overall Difficulty To Me: ★★★★★☆☆☆☆☆

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Grey-Cat-The-Flag-2023-Qualifiers/images/score.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Grey-Cat-The-Flag-2023-Qualifiers/images/solves1.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Grey-Cat-The-Flag-2023-Qualifiers/images/solves2.png)

## What I've learned in this CTF

- Web:
    1. Inspecting Source Page ([Fetus Web](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Fetus-Web/README.md))
    2. Exploiting Open Redirect Vulnerability To Leak Credentials ([Login Bot](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Login-Bot/README.md))
    3. Exploiting HTTP Parameter Pollution In Flask & FastAPI To Bypass Validation ([Microservices](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Microservices/README.md))
    4. Exploiting RCE Via SSTI With Filter Bypass ([Microservices Revenge](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Microservices-Revenge/README.md))
    5. Exploiting Blind SQL Injection With Conditional Responses ([100 Questions](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/100-Questions/README.md))
    6. Leaking Cookies Via Reflected XSS ([Baby Web](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Baby-Web/README.md))
    7. Exploiting PHP Insecure Deserialization With Custom Gadget Chain ([View My Albums](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/View-My-Albums/README.md))
    8. [Sort It Out](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Web/Sort-It-Out/README.md) ***(Unsolved)***
- Misc:
    1. Crashing Python With Segmentation Fault Via `ctypes` Library ([CrashPython](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Misc/CrashPython/README.md))
    2. Writing A Script To Solve Captcha With OCR ([Gotcha](https://siunam321.github.io/ctf/Grey-Cat-The-Flag-2023-Qualifiers/Misc/Gotcha/README.md))