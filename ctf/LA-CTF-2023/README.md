# LA CTF 2023 Writeups

> CTFtime event link: [https://ctftime.org/event/1732](https://ctftime.org/event/1732)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/LA-CTF-2023/images/banner.gif)

## Writeups

- Web:
	- [college-tour](https://siunam321.github.io/ctf/LA-CTF-2023/Web/college-tour/)
	- [metaverse](https://siunam321.github.io/ctf/LA-CTF-2023/Web/metaverse/)
	- [uuid hell](https://siunam321.github.io/ctf/LA-CTF-2023/Web/uuid-hell/)
	- [my-chemical-romance](https://siunam321.github.io/ctf/LA-CTF-2023/Web/my-chemical-romance/)
	- [california-state-police](https://siunam321.github.io/ctf/LA-CTF-2023/Web/california-state-police/) ***(Unsolved)***
- Misc:
	- [CATS!](https://siunam321.github.io/ctf/LA-CTF-2023/Misc/CATS!/)
	- [EBE](https://siunam321.github.io/ctf/LA-CTF-2023/Misc/EBE/)
- Rev:
	- [string-cheese](https://siunam321.github.io/ctf/LA-CTF-2023/Rev/string-cheese/)
	- [caterpillar](https://siunam321.github.io/ctf/LA-CTF-2023/Rev/caterpillar/)
- Pwn:
	- [gatekeep](https://siunam321.github.io/ctf/LA-CTF-2023/Pwn/gatekeep/)

## Background

LA CTF is an annual Capture the Flag (CTF) cybersecurity competition hosted by ACM Cyber at UCLA & Psi Beta Rho. LA CTF is open to all skill levels of cybersecurity! Whether you are tackling your first exploit or have professional experience, there will be challenges just right for you! There will be a variety of events ranging from the competition containing jeopardy-style cybersecurity challenges to talks from UCLA professors to fun events such as typing competitions!

- Start: 11 Feb. 2023, 04:00 UTC
- End: 12 Feb. 2023, 22:00 UTC

**Categories:**

- Crypto
- Misc
- Pwn
- Rev
- Web

## Overview

- Solved: 8 (Excluding 10 points challenges)
- Points: 1487
- Rank: 397/980
- Overall Difficulty To Me: ★★★★★★☆☆☆☆

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/LA-CTF-2023/images/score.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/LA-CTF-2023/images/solves.png)

## What I've learned in this CTF

- Web:
1. Information Gathering Via View Source Page ([college-tour](https://siunam321.github.io/ctf/LA-CTF-2023/Web/college-tour/))
2. Leveraging Stored XSS To Perform CSRF attack ([metaverse](https://siunam321.github.io/ctf/LA-CTF-2023/Web/metaverse/))
3. Predicting UUID Version 1 Via Known Nodes & Clock Sequence ([uuid hell](https://siunam321.github.io/ctf/LA-CTF-2023/Web/uuid-hell/))
4. Leaking Mercurial SCM Repository In An Web Application ([my-chemical-romance](https://siunam321.github.io/ctf/LA-CTF-2023/Web/my-chemical-romance/))
5. [california-state-police](https://siunam321.github.io/ctf/LA-CTF-2023/Web/california-state-police/) ***(Unsolved)***
- Misc:
1. View Image Metadata Via `exiftool` ([CATS!](https://siunam321.github.io/ctf/LA-CTF-2023/Misc/CATS!/))
2. Extracting Evil Bit's Hidden Data ([EBE](https://siunam321.github.io/ctf/LA-CTF-2023/Misc/EBE/))
- Rev:
1. Using `strings` & `ltrace` To Extract Hidden String ([string-cheese](https://siunam321.github.io/ctf/LA-CTF-2023/Rev/string-cheese/))
2. Reversing Obfuscated JavaScript Code ([caterpillar](https://siunam321.github.io/ctf/LA-CTF-2023/Rev/caterpillar/))
- Pwn:
1. Buffer Overflow Via Dangerous `gets()` Function ([gatekeep](https://siunam321.github.io/ctf/LA-CTF-2023/Pwn/gatekeep/))