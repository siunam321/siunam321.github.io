---
permalink: /ctf/Patchstack-Alliance-CTF-S02E01/index.html
description: I played Patchstack Alliance CTF S02E01 and I got 4th place. Here's my writeup for 7 challenges, including "A Nice Block", "Patchstack Scheduler Pro", "Sup3rcustomiz3r", "Cool Templates", "Blocked", "Sneaky", and "Up To You".
ogImageUrl: https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Patchstack-Alliance-CTF-S02E01/images/banner.png
---

# Patchstack Alliance CTF S02E01 Writeup

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Patchstack-Alliance-CTF-S02E01/images/banner.png)

## Writeup

1. [A Nice Block](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/A-Nice-Block/)
2. [Patchstack Scheduler Pro](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Patchstack-Scheduler-Pro/)
3. [Sup3rcustomiz3r](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Sup3rcustomiz3r/)
4. [Cool Templates](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Cool-Templates/)
5. [Blocked](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Blocked/)
6. [Sneaky](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Sneaky/)
7. [Up To You](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Up-To-You/)

## Background

- Starts: 20 Feb. 2025, 08:00 UTC
- Ends: 22 Feb. 2025, 08:00 UTC

Welcome to **WordCamp Asia Patchstack Alliance Capture the Flag** event. Challenges will be released in 3 batches on 20,21,22 Feb at 8am UTC. Competition will run for 3 full days. They won’t be easy, but we’re confident that you’ll handle them.

We’re counting on you.

## Overview

- Solves: 6/10
- Score: 3899
- Rank: 4/24
- Overall Difficulty To Me: ★★★★★☆☆☆☆☆

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Patchstack-Alliance-CTF-S02E01/images/score.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Patchstack-Alliance-CTF-S02E01/images/solves.png)

## What I've learned in this CTF

1. [A Nice Block](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/A-Nice-Block/) - Local File Inclusion (LFI)
2. [Patchstack Scheduler Pro](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Patchstack-Scheduler-Pro/) - IDOR to read arbitrary posts and decrypt AES CBC mode encrypted data using 16 characters partial key
3. [Sup3rcustomiz3r](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Sup3rcustomiz3r/) - Privilege escalation via arbitrary option update
4. [Cool Templates](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Cool-Templates/) - Dynamic function call filter bypass via upper-case characters
5. [Blocked](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Blocked/) - Parser differential between the PHP and MySQL's weird behavior and PHP `exit()` bypass via PHP filter chain
6. [Sneaky](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Sneaky/) - Arbitrary file write via PHP filter chain
7. [Up To You](https://siunam321.github.io/ctf/Patchstack-Alliance-CTF-S02E01/Up-To-You/) - Read arbitrary posts via chaining with arbitrary option update and IDOR