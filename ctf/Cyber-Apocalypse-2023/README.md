# Cyber Apocalypse 2023 Writeups

> CTFtime event link: [https://ctftime.org/event/1889](https://ctftime.org/event/1889)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Cyber-Apocalypse-2023/images/banner.jpg)

## Writeups

- Web:
	1. [Trapped Source](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Trapped-Source/)
	2. [Gunhead](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Gunhead/)
	3. [Drobots](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Drobots/)
	4. [Passman](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Passman/)
	5. [Orbital](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Orbital/)
	6. [Didactic Octo Paddles](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Didactic-Octo-Paddles/)
	7. [SpyBug](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/SpyBug/) ***(Unsolved)***

- Pwn:
	1. [Initialise Connection](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Pwn/Initialise-Connection/)
	2. [Questionnaire](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Pwn/Questionnaire/)
	3. [Getting Started](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Pwn/Getting-Started/)

- Misc:
	1. [Persistence](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Misc/Persistence/)
	2. [Restricted](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Misc/Restricted/)
	3. [Hijack](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Misc/Hijack/)

- Reversing:
	1. [Needle in a Haystack](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Reversing/Needle-in-a-Haystack/)
	2. [Hunting License](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Reversing/Hunting-License/)

## Background

- Starts: 18 March 2023, 21:00 HKT
- Ends: 23 March 2023, 20:59 HKT

Cyber Apocalypse is back!

Ready for a mission through space and time? This is your chance to join the biggest hacking competition of the year, powered by Hack The Box.

66 Million Years Ago…
All started million years ago in a distant plannet, home to a parasitic alien species. Their plannet was threatened by a black hole and were searching solutions to survive. Therefore the aliens sent out organized missions, containing their offspring that would travel in space until hitting a planet suitable for them. Once they land on one, they would drill underground and hibernate until they were awakened. One of these vessels hit and established itself on Earth. However the hit was so massive it caused an extinction event that wiped out the dinosaurs.

Thousands of Years Ago…
In one of those missions, In 3000 B.C., a spaceship crashed into Earth. The surviving crew was outnumbered and defeated by the tribes of ancient Egypt. Only one alien member managed to ran away wcith a very powerful treasure. This treasure is holding the power to awaken their kind, and infinite capabilities to anyone holding it. Despite that, the alien never made it to the spaceship and died in the desert. Generations later, the son of a Pharaoh stumbles on a strange skeleton, holding on to a piece of alien technology. He found a way to harness some of the immense power of this relic. He grew mad with power, oppressed his people and conquered neighboring nations. The people detested their leader, and when he died, he was buried along with the artifact in an underground city and was never spoken of again.

In the Distant Future…
The Intergalactic Ministry of Spies has captured and decoded communications channels hinting that the aliens have already made it again to Earth and are trying to find information regarding the relic. The ministry contacted Pandora, a famous archaeologist hacker, to help them get to the powerful artifact before the aliens. She will have to race against time and navigate treacherous ancient tombs and underground cities to locate the relic. She will face rival treasure hunters and possible lifeforms of unknown origin. Will she be the first to find the artifact and save humanity?

Join, compete, meet, and learn from the best hackers in the world. Prizes for a total worth value of $50,000 are waiting for the top teams!

**Categories:**

- Warmups
- Pwn
- Web
- Blockchain
- Hardware
- Reversing
- ML
- Misc
- Forensics
- Crypto

## Overview

- Team: BlackOps
- Team Member: hewozuoai, siunam
- Team Solved: 30/74
- My Solved: 12/74
- Points: 8725
- Rank: 423/6482
- Overall Difficulty To Me: ★★★★★★★★☆☆

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Cyber-Apocalypse-2023/images/cert.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Cyber-Apocalypse-2023/images/score.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Cyber-Apocalypse-2023/images/solves1.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Cyber-Apocalypse-2023/images/solves2.png)

## What I've learned in this CTF

- Web:
	1. Viewing Source Page ([Trapped Source](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Trapped-Source/))
	2. OS Command Injection ([Gunhead](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Gunhead/))
	3. Authentication Bypass Via SQL Injection ([Drobots](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Drobots/))
	4. Leveraging GraphQL To Update Arbitrary User's Password ([Passman](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Passman/))
	5. Exploiting Error-Based/Time-Based SQL Injection ([Orbital](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Orbital/))
	6. JWT Header's `"alg": "NONE"` Authentication Bypass & RCE Via JsRender SSTI ([Didactic Octo Paddles](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/Didactic-Octo-Paddles/))
	7. [SpyBug](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Web/SpyBug/) ***(Unsolved)***

- Pwn:
	1. How To Use `nc` (NetCat) ([Initialise Connection](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Pwn/Initialise-Connection/))
	2. Basic Binary Exploitation Concept ([Questionnaire](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Pwn/Questionnaire/))
	3. Basic Stack Buffer Overflow ([Getting Started](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Pwn/Getting-Started/))

- Misc:
	1. Writing A Python Script To Send HTTP Request ([Persistence](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Misc/Persistence/))
	2. RBash escape ([Restricted](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Misc/Restricted/))
	3. Insecure Deserialization In Python's YAML Library ([Hijack](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Misc/Hijack/))

- Reversing:
	1. Listing Strings In A File Via `strings` ([Needle in a Haystack](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Reversing/Needle-in-a-Haystack/))
	2. Basic Reverse Engineering ([Hunting License](https://siunam321.github.io/ctf/Cyber-Apocalypse-2023/Reversing/Hunting-License/))