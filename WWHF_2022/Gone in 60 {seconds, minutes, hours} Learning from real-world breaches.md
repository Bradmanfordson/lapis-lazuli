by Jeff McJunkin @ Rogue Valley Information Security

## First Breach
---
- Google dork s3 buckets with "ssn"
- he literally just downloaded xls files and got PII including SSNs!

#### *Attackers want data... anyway they get that data is a breach!*

## Second Breach
---
- Proxy-not-shell vulnerability
- Ran an nmap scan searching any IP address with explicitly the proxy-not-shell vuln
- Found targets, got into them with Proxy-not-shell and replaced their boot-loader with MEMZ

Better way to do vulnerability management:
1. New Vulnerability is released
2. Does it get me a shell?
	1. No? Then I don't care!!!
	2. Yes? Oh shit.... fix it....

#### *Most Vulnerabilities will NEVER be exploited*

There are 5 ways into a system:
1. Phishing
2. Exploiting a public-facing service
3. Authentication.... like literally just login
4. Rogue Devices
5. Supply Chain Attacks

#### Third Breach
---
- The worlds most popular C2 is..... Teamviewer :(
- Demo:
	- Social Engineer someone to run Quick Assist on their computer
	- Done? I mean it's pretty simple
- SOCKS5 Proxy locally so I can maintain better persistance
- Proxychains tool! any tool that's proxy-aware can browse as our client.

#### *The most important step you can ever take in your life... the next one.*

- Checkout DFIR Reports
