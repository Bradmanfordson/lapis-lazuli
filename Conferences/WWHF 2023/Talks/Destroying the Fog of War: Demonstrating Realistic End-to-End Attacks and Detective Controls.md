---
Speaker: Jeff McJunkin
Company: Rogue Valley Information Security
---
## Defenders Three Tasks and How to Start Improving

Attackers want your data. period.

Don't let your shit be public facing....
if you attackers can get your data with wget and curl, then fucking move it

Only 5 ways in:
- phishing
- exploiting public facing services
- authentication via public facing services
- inserting rouge devices
- supply chain attacks
Way way more attacks once your INSIDE

Defenders Objectives: To prevent successful breaches, they need to DETECT and RESPOND to attackers who gain access BEFORE they accomplish their goal.

1. Reduce the number of ways attackers gain initial access - focus on protecting the 75-90%, something is better than nothing.
	1. consolidate to one method for remote support
	2. minimize external attack surface
	3. lock down as many methods of code execution as possible from user endpoints
2. lower the time to detect AND respond to an attacker
	1. you cannot respond to actors that you do not know are there
	2. alert on suspicious activity as soon as possible
	3. train and test your response capabilities - given an infected machine, can you find the compromised user(s) and computer(s) that the attacker ALSO compromised?
	4. your attackers ALWAYS get a head start when they get code execution (think Mario kart and you just get to sit while they do the first lap)
3. increase the time for an attacker for accomplish their goal
	1. when doing GOOD penetration tests and red teams, hack the shit THEN figure out what it takes to get caught. get noisier and noisier, you need to figure out where the company succeeds so you can know how to assist them. how mature are they?
"Out of our last 100 penetration tests, just TWO required exploitation to accomplish the goals." - John Strand

Read The DFIR Report breaches to find out what ACTUALLY happens.

RDP - ransomware deployment protocol

If an attacker can get in EASILY and gain access to the jewels QUICKLY then no amount of detective controls will matter.

If attackers can get in and win in an hour, you're just screwed.

"The most important step a person can take is always the next one." - Oathbringer book

https://bit.ly/killfog
https://calendly.com/rogueinfosec/mock-interview

