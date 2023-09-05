# DownUnderCTF 2023 Writeup

> CTFTime event link: [https://ctftime.org/event/1954](https://ctftime.org/event/1954)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/DownUnderCTF-2023/images/banner.png)

## Writeups

- misc:
    1. [helpless](https://siunam321.github.io/ctf/DownUnderCTF-2023/misc/helpless/)
- osint:
    1. [Excellent Vista!](https://siunam321.github.io/ctf/DownUnderCTF-2023/osint/Excellent-Vista!/)
    2. [Bridget's Back!](https://siunam321.github.io/ctf/DownUnderCTF-2023/osint/Bridget's-Back!/)
    3. [Comeacroppa](https://siunam321.github.io/ctf/DownUnderCTF-2023/osint/Comeacroppa/)
- web:
    1. [proxed](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/proxed/)
    2. [static file server](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/static-file-server/)
    3. [xxd-server](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/xxd-server/)
    4. [actually-proxed](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/actually-proxed/)
    5. [grades_grades_grades](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/grades_grades_grades/)
    6. [cgi fridays](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/cgi-fridays/)

## Background

- Starts: 01 September 2023, 17:30 HKT
- Ends: 03 September 2023, 17:30 HKT

DownUnderCTF is the largest online Australian run Capture The Flag (CTF) competition with over 4100+ registered users and over 1900+ registered teams (2022). Its main goal is to try to up-skill the next generation of potential Cyber Security Professionals and increase the CTF community's size here in Australia. Prizes are only for Australian Secondary or Tertiary school students. However, our CTF is online and open for anyone to play worldwide.

**Categories:**

- crypto
- pwn
- web
- rev 
- misc
- blockchain
- osint

## Overview

- Team: [ARESx](https://ctftime.org/team/128734)
- Team Solves: 27/68
- Individual Solves: 10/68
- Score: 3075/14341
- Rank: 92/2110
- Overall Difficulty To Me: ★★★★★☆☆☆☆☆

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/DownUnderCTF-2023/images/cert.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/DownUnderCTF-2023/images/solves.png)

## What I've learned in this CTF

- misc:
    1. Python built-in function `help()` shell escape ([helpless](https://siunam321.github.io/ctf/DownUnderCTF-2023/misc/helpless/))
- osint:
    1. Extracting image's metadata via `exiftool` ([Excellent Vista!](https://siunam321.github.io/ctf/DownUnderCTF-2023/osint/Excellent-Vista!/))
    2. Reverse image search ([Bridget's Back!](https://siunam321.github.io/ctf/DownUnderCTF-2023/osint/Bridget's-Back!/), [Comeacroppa](https://siunam321.github.io/ctf/DownUnderCTF-2023/osint/Comeacroppa/))
- web:
    1. Proxying via `X-Forwarded-For` header ([proxed](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/proxed/))
    2. Exploiting path traversal vulnerability ([static file server](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/static-file-server/))
    3. Exploiting file upload vulnerability with 16 characters chunk ([xxd-server](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/xxd-server/))
    4. Double proxying via `X-Forwarded-For` header ([actually-proxed](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/actually-proxed/))
    5. Sign arbitrary JWT via flawed signing process ([grades_grades_grades](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/grades_grades_grades/))
    6. Exploiting Perl's `param()` flaw ([cgi fridays](https://siunam321.github.io/ctf/DownUnderCTF-2023/web/cgi-fridays/))