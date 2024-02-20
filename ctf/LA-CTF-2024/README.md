# LA CTF 2024 Writeup

> CTFTime event link: [https://ctftime.org/event/2102](https://ctftime.org/event/2102)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/LA-CTF-2024/images/banner.gif)

## Writeup

- web:
    - [terms-and-conditions](https://siunam321.github.io/ctf/LA-CTF-2024/web/terms-and-conditions/)
    - [flaglang](https://siunam321.github.io/ctf/LA-CTF-2024/web/flaglang/)
    - [la housing portal](https://siunam321.github.io/ctf/LA-CTF-2024/web/la-housing-portal/)
    - [new-housing-portal](https://siunam321.github.io/ctf/LA-CTF-2024/web/new-housing-portal/)
    - [pogn](https://siunam321.github.io/ctf/LA-CTF-2024/web/pogn/)
    - [penguin-login](https://siunam321.github.io/ctf/LA-CTF-2024/web/penguin-login/)
    - [jason-web-token](https://siunam321.github.io/ctf/LA-CTF-2024/web/jason-web-token/)

## Background

- Starts: 17 February 2024, 04:00 UTC
- Ends: 18 February 2024, 22:00 UTC

LA CTF is an annual Capture the Flag (CTF) cybersecurity competition hosted by ACM Cyber at UCLA & Psi Beta Rho. LA CTF is open to all skill levels of cybersecurity! Whether you are tackling your first exploit or have professional experience, there will be challenges just right for you! There will be a variety of events ranging from the competition containing jeopardy-style cybersecurity challenges to talks from UCLA professors to fun events such as typing competitions! If you are interested in attending, join the Discord to stay up to date with the latest information about LA CTF!

**Categories:**

- crypto
- misc
- pwn
- rev
- web
- welcome

## Overview

- Team: [ARESx](https://ctftime.org/team/128734)
- Team Solves: 34/53
- Individual Solves: 2/53
- Score: 11030
- Global Rank: 26/1074
- Overall Difficulty To Me: ★★★★☆☆☆☆☆☆

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/LA-CTF-2024/images/score.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/LA-CTF-2024/images/solves.png)

## What I've learned in this CTF

- web:
    1. Debugging via browser console ([terms-and-conditions](https://siunam321.github.io/ctf/LA-CTF-2024/web/terms-and-conditions/))
    2. Bypassing restriction with no cookies ([flaglang](https://siunam321.github.io/ctf/LA-CTF-2024/web/flaglang/))
    3. SQLite Union-based SQL injection with filter bypass ([la housing portal](https://siunam321.github.io/ctf/LA-CTF-2024/web/la-housing-portal/))
    4. Stored XSS chained with CSRF ([new-housing-portal](https://siunam321.github.io/ctf/LA-CTF-2024/web/new-housing-portal/))
    5. Exploiting WebSocket ([pogn](https://siunam321.github.io/ctf/LA-CTF-2024/web/pogn/))
    6. PostgreSQL Blind-based SQL injection with conditional responses and filter bypass ([penguin-login](https://siunam321.github.io/ctf/LA-CTF-2024/web/penguin-login/))
    7. Floating point confusion ([jason-web-token](https://siunam321.github.io/ctf/LA-CTF-2024/web/jason-web-token/))