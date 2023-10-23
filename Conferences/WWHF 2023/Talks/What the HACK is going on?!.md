---
Speaker: Tim Medin
Company: Red Siege
---
An offensive look at modern breaches.

- Looking at breaches and doing case studies are the BEST way of learning what the real bad guys do. It's literally them getting caught.
- Pentesters cannot disclose their pentest reports - so we have to rely on bad guys getting caught.

## Initial access: Use of stolen credentials = 86% of breaches. Less than 10% are exploits.

Modern exploitation is HARD
- memory protections
- compiler protections
- secure software development
- managed code bases

Most of the "modern" entry points are old exploits...

For GOOD vulnerability management - look at what's actually being exploited. Stop focusing on fucking TLS.
Making dashboards and metrics better do nothing except make Carl happy. Fuck Carl - do real work.

## Social Engineering: pick the easiest way in.
Software has gotten better.
RCE is becoming more and more rare.
Time to start moving to users and phishing.

Passwords - the gift that keeps on giving.

## Phishing
- Effective pretext
- Targeted attacks
- Make it urgent

The rise of AI:
AI allows BAD phishers to write GOOD emails.
It doesn't really help GOOD phishers, but helps the BAD ones.

MORE and MORE phishing emails are making it to inboxes; even though we have better and better filtering systems.

Phishing Defenses:
- everyone is doing training, tests, filtering - obviously IT DOESN'T FUCKING WORK
- Behavior detection's and QUICK response are the less common but most important.

The reason the mean-time-to-detection is getting lower is because attackers want the money now, they don't care anymore about squeezing every penny. Ransomware a few hundred thousand and go party.

## Passwords
- Rotation, un-realistic complexity requirements - BOTH OF THESE ARE SHIT.
	- There is no practical reasoning to the 90 day.
	- NO pentester has been "got" because of rotation policies.
	- Goal is to increase entropy...
		- Replacing i's to 1's, o to 0, a to @.... EVERYONE KNOWS THESE TRICKS it doesn't increase entropy.
- Breached credentials are the gift that keeps on giving.

## Risk Focus
What is the MOST critical data to protect??

Domain admin doesn't matter as much anymore, it's about where you can get data.

## What happens after that initial breach?
Assume the breach happened.
What happens when <blank> fails? 
What can you PWN without domain admin?

When security is TOO HARD - users find ways around it.

As a defender - RUN THE FUCKING ATTACKER TOOLS ON YOUR SHIT!!! (and clean it up)

