By Dennis Pelton @ Foghorn

- Killchain: Identify the structure of an attack

Beacon Frames: "Hey, I'm Starbux!"
PNL: Preferred Network List - "Yo, I know `Starbux`, you close by?"

ID the Target: Recon (wardriving)
	- need to have permiscuous mode
	- can do it with basically anything such as a raspberry pi

Dispatch Forces to target

## Karma Attack
- Takes PNL's and says "yeah, I am that"
- Client connects and you control their traffic now
- Only works if there is NO Authentication
- "What if they're already connected thought??? ... (see next attack)"

## DeAuth Attack
- If a client gets a deAuth packet, the client WILL disconnect
- if your rogue access point has a higher signal strength, then they'll connect to you instead (for Karma attacks)
- 802.11w prevents this, but, both AP and client have to support it
- WPA3 prevents this too, but only 0.03% of the population uses WPA3

## Half-Handshake Attack
1. AP sends anonce
	- AP sends auth # to client
2. Client creates PTK
	- Auth # from the AP
	- Suppliment # from client (random)
	- MAC Address
	- Auth Stuff (creds)
3. AP creates its own PTK
	- Checks PTK made by client
	- validates both PTK's match
4. Client confirms and it's good to go.

The attack is to get the client PTK then brute force step 3 with Auth Stuff until they match. Once they match, you have their auth stuff!

## KRack Attack
- The client doesn't complete step 4, the AP will resend the GTK

---

Destruction of target
- Rogue DNS
- Rogue Web Servers

How to secure WIFI?
- Common sense
	- Best defense is knowledge of offense
- disable auto-connect
- "ask mode" for connecting to APs
- use Guest networks - doesnt get rid of risk, but lowers it.
- Rogue AP detection
- Strong passwords and updates!
