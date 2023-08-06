### by Brian King @ Black Hills Information Security

- "There's no such thing as advanced webapp penetration testing, only simple things you haven't seen before."
- "You don't really get a shell on webapp penetration tests, also you don't really care about 'maintaining access'."
- All the "methodologies" to pentests are crap, keep it simple!

#### What is your goal?
1. Get something of value you're **NOT** supposed to have
2. Get a shell - extremely rare
3. Getting other user's information - extremely common

#### BBKing's Methodology:
1. What is the website supposed to do?
2. What does the website *actually* do?
3. Report the differences AS YOU FIND THEM!
---
##### "Application Security is just situational awareness!"
---
- "The first puzzle is to find the other puzzles."
- Eliminate "blind spots" - it can be uncomfortable at first but will make you an incredible hacker (think about mirror blindspots on a car, proper blind spot elimination is uncomfortable at first!)

# The Web:
- HTTP - the "web"
- URL - how to navigate "the web"
- HTML - the user interface
- Javascript - functionality

### HTTP:
---
- Stateless! Meaning every single request is separate from the others.
- Always scan by "Fully Qualified Domain Name", and NOT by IPs. Servers can host a variety of things, if you're hired to do a web application penetration test, you ONLY hit the web.
- Ther server determines that it's done reading headers with 2 carriage return lines: `\r\n`
- TRACE
	- echo a request back to you
	- "who cares?" - well, if you have a WAF/ELB/ALB and it edits anything, it tells you through any changes that come back to you
- OPTION - Don't trust it... it always lies
-  304 response tells you it's checking your Cache, clear the cache or resend the request but tell it to NOT check your cache
- HTTP 2.0 - Not Text, it's Binary
	- Supports multiplexing
	- Super efficient but hardre to figure out what's going on
	- you'll never see HTTP 2.0 that is NOT over HTTPS
- HTTP 3.0 - HTTP over QUIC
	- Quick UDP Internet Connection
	- Encryption is REQUIRED
	- QUIC replaces TCP and TLS
	- Developed by Google

### HTML:
---
- TEXT
- Just another form of XML
- Contains "non-html"
	- Javascript
	- CSS
	- inline images
- Rendering HTML is crazy!!! It switches and replaces stuff EVERYWHERE

### Developer Tools!!
---
Situational Awareness!

#### Console: What's going on.
- JS doesnt have standard I/O or errors so this is as close as you can get
- The following will show you ALL the links on the page with a blue border!!
``` javascript
for (link of document.links) {
	link.style = "border: 5px solid blue"
}
```
#### Inspector: How it's put together.
- If you see "input type=password" just change it to "input type=text" and boom, `*`'s are gone!'
#### DOM: Top-Down View.
#### Storage: Little databases.
- If there is data here, then a developer CHOSE to put it there, so figure out WHY they chose to do that!
#### Network: Where it's coming from.
#### Debugger: "Do that slower next time."

- Always have developer tools turned on, even when not hacking.
- If you see logging output, that's probably where you want to test a bit more thoroughly. It's typically a tell-tell sign that it's where a developer was having a problem and they forgot to remove the output when going to production.

---
- The number 1 mistake when web application pentration testing is jumping straight into testing before you know the application.
	- ask yourself:
		- When you find something: "Did I notice this during my recon phase?"
		- "Who are it's intended users?"
		- "Does it do anything risky or expensive?"
		- "What inputs does it ask for?"
		- "Does it show user-generated content?"

### YOU ARE SMARTER THAN VULNERABILITY SCANNERS!

- Answer the question: "What does this site do?"
- Risky does NOT mean vulnerable
	-  Account recovery is more RISKY than creating an account.
- Learn an application through the eyes of a "Junior Developer"
- About 40% of the internet runs on Wordpress

---

### Angular.JS
- main.js IS the web application for Angular apps... like the whole freaking thing....
- Search main.js for `Routerlink` to find pages, don't bother directory busting.
---

### Web API's
- Web API's are rough, you can't just click around, you have to reverse engineer via I/O only (mostly)
- API's are not designed for browsers
- no UI means no "exploring" with the mouse
- It's pretty easy to proxy Python requests to Burp
---

## Don't prove you CAN break the Application.
## Prove that you can NOT break the Application!

---
- HTTP Parameter Polution - include the SAME parameter more than once,
	- Example:
		`redirect_url=http:\\GOOD_GUYS.com&redirect_url=https://BAD_GUYS.com`
- For regex validation, ALWAYS anchor regex with a `^` at the beginning and a `&` at the end.

### Idea: Cyberchef extension built into Burp Suite

- How many systems are you dealng with?
	- Understand what entity is decoding/encoding what.
		- Example:
			The webserver will decode `%2500` to `%00` which is the null-byte for the OS.
			This is GREAT for filter bypassing!

---
## "You can wear a bullet proof vest, of you can avoid getting shot. Both *can* save your life, but one is more preferable." --> WAF IS GARBAGE!!! They're temporary and do NOT fix the problem at all.
---

## Reporting:
- If you catch yourself saying any of the following, you're being offensive in your reporting:
	- "just..."
	- "simply..."
	- "quickly..."
	- "it's easy to..."
- You're telling the folks that they don't know how to do their job.
---

- JSON Web Tokens (JWT.... Not JOT... stop saying it like that)
	- Decode them!!! Tons of them have more information than is necessary
	- Support a handful of signing techinques, including just not signing.... you might be able to "craft" a JWT by hand, not signed, and pass it along.
- Always skim through RFC's, they typically have some gold in there to tell you what defaults there are and when developers probably stick with defaults.
- Don't be afraid of new things! We learned Web Socket pentesting in like 15 minutes!
- Web Application Penetration Testing == Advanced Paying Attention

---
---
For the labs, we hit up Juice Shop! :)
